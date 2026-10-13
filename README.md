<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Parasite</title>
<style>
  html,body{margin:0;height:100%;background:#05050a;overflow:hidden;cursor:none}
  canvas{display:block;width:100%;height:100%}
  .hint{position:fixed;left:50%;bottom:18px;transform:translateX(-50%);
    font:12px/1 ui-monospace,monospace;color:#6b7280;letter-spacing:.15em;pointer-events:none}
</style>
</head>
<body>
<canvas id="c"></canvas>
<div class="hint">MOVE · CLICK TO MAKE IT LASH</div>
<script>
const cv = document.getElementById('c');
const ctx = cv.getContext('2d');
let W, H, DPR;
function resize(){
  DPR = Math.min(window.devicePixelRatio || 1, 2);
  W = innerWidth; H = innerHeight;
  cv.width = W * DPR; cv.height = H * DPR;
  ctx.setTransform(DPR,0,0,DPR,0,0);
  ctx.fillStyle = '#05050a'; ctx.fillRect(0,0,W,H);
}
addEventListener('resize', resize); resize();

const mouse = {x: W/2, y: H/2, active:false, last:performance.now()};
addEventListener('pointermove', e => { mouse.x=e.clientX; mouse.y=e.clientY; mouse.active=true; mouse.last=performance.now(); });
let burst = 0;
addEventListener('pointerdown', () => burst = 1);

const body = {x: W/2, y: H/2, vx:0, vy:0};
const N = 16;      // tentacles
const tentacles = [];
for (let i=0;i<N;i++){
  const n = 22 + (Math.random()*14|0);
  const seg = 9 + Math.random()*7;
  const pts = Array.from({length:n}, () => ({x:body.x, y:body.y}));
  tentacles.push({
    n, seg, pts,
    root: (i/N)*Math.PI*2,
    ph: Math.random()*Math.PI*2,
    sp: .4 + Math.random()*.9,
    rad: 25 + Math.random()*70,
    hue: 160 + (i/N)*180,
    hairs: Math.random() < .7
  });
}

function norm(dx,dy){ const d=Math.hypot(dx,dy)||1e-6; return [dx/d, dy/d, d]; }

function frame(now){
  const t = now/1000;

  // idle wander if the cursor hasn't moved for a while
  let tx = mouse.x, ty = mouse.y;
  if (now - mouse.last > 2500){
    tx = W/2 + Math.cos(t*.7)*W*.3;
    ty = H/2 + Math.sin(t*1.1)*H*.28;
  }

  // body chases target with spring + drag
  body.vx += (tx - body.x)*.012; body.vy += (ty - body.y)*.012;
  body.vx *= .86; body.vy *= .86;
  body.x += body.vx; body.y += body.vy;

  burst *= .94;

  // fade trail
  ctx.globalCompositeOperation = 'source-over';
  ctx.fillStyle = 'rgba(5,5,10,.22)';
  ctx.fillRect(0,0,W,H);
  ctx.globalCompositeOperation = 'lighter';
  ctx.lineCap = 'round'; ctx.lineJoin = 'round';

  for (const T of tentacles){
    const {pts, n, seg} = T;
    const reach = seg*(n-1);

    // where this tentacle wants its tip
    const a = T.root + t*T.sp*.8 + T.ph;
    const r = (T.rad + 30*Math.sin(t*1.7+T.ph)) * (1 + burst*2.2);
    let gx = tx + Math.cos(a)*r;
    let gy = ty + Math.sin(a)*r;
    let [dx,dy,d] = norm(gx-body.x, gy-body.y);
    if (d > reach*.97){ gx = body.x + dx*reach*.97; gy = body.y + dy*reach*.97; }

    // FABRIK: tip -> root, then root -> tip
    pts[n-1].x = gx; pts[n-1].y = gy;
    for (let j=n-2;j>=0;j--){
      const [ux,uy] = norm(pts[j].x-pts[j+1].x, pts[j].y-pts[j+1].y);
      pts[j].x = pts[j+1].x + ux*seg; pts[j].y = pts[j+1].y + uy*seg;
    }
    pts[0].x = body.x + Math.cos(T.root+t*.5)*10;
    pts[0].y = body.y + Math.sin(T.root+t*.5)*10;
    for (let j=1;j<n;j++){
      const [ux,uy] = norm(pts[j].x-pts[j-1].x, pts[j].y-pts[j-1].y);
      pts[j].x = pts[j-1].x + ux*seg; pts[j].y = pts[j-1].y + uy*seg;
    }

    // draw with writhing wobble, tapered width
    const wob = (j) => {
      const p = pts[j], q = pts[Math.min(j+1,n-1)];
      const [ux,uy] = norm(q.x-p.x, q.y-p.y);
      const k = Math.sin(j*.55 - t*5 + T.ph) * (2 + j*.35) * (1 + burst*2);
      return [p.x - uy*k, p.y + ux*k];
    };
    for (let j=0;j<n-1;j++){
      const [x1,y1] = wob(j), [x2,y2] = wob(j+1);
      const f = j/(n-1);
      ctx.strokeStyle = `hsla(${T.hue + f*50 + t*20},100%,${55+f*20}%,${.35+f*.55})`;
      ctx.lineWidth = 3.2*(1-f) + .6;
      ctx.beginPath(); ctx.moveTo(x1,y1); ctx.lineTo(x2,y2); ctx.stroke();

      // little hairs / spines
      if (T.hairs && j%2===0 && j>2){
        const [ux,uy] = norm(x2-x1, y2-y1);
        const L = 7 + 9*f + burst*10;
        ctx.lineWidth = .8;
        ctx.beginPath();
        ctx.moveTo(x1,y1); ctx.lineTo(x1 - uy*L, y1 + ux*L);
        ctx.moveTo(x1,y1); ctx.lineTo(x1 + uy*L, y1 - ux*L);
        ctx.stroke();
      }
    }
    // glowing tip
    const [ex,ey] = wob(n-1);
    ctx.fillStyle = `hsla(${T.hue+60},100%,75%,.9)`;
    ctx.beginPath(); ctx.arc(ex,ey,2.2+burst*2,0,7); ctx.fill();
  }

  // body: pulsing jittery rings
  const pulse = 1 + Math.sin(t*6)*.12 + burst*.5;
  for (let k=0;k<3;k++){
    ctx.strokeStyle = `hsla(${300+k*30+t*40},100%,${60+k*10}%,${.7-k*.15})`;
    ctx.lineWidth = 1.4;
    ctx.beginPath();
    const P = 28;
    for (let i=0;i<=P;i++){
      const ang = i/P*Math.PI*2;
      const rr = (13 + k*7) * pulse + Math.sin(ang*5 + t*4 + k)*(2.5+k*1.5);
      const x = body.x + Math.cos(ang)*rr, y = body.y + Math.sin(ang)*rr;
      i ? ctx.lineTo(x,y) : ctx.moveTo(x,y);
    }
    ctx.stroke();
  }
  // eye that tracks the cursor
  const [ex2,ey2] = norm(mouse.x-body.x, mouse.y-body.y);
  ctx.fillStyle = '#fff';
  ctx.beginPath(); ctx.arc(body.x+ex2*4, body.y+ey2*4, 3.2, 0, 7); ctx.fill();

  // cursor reticle
  ctx.strokeStyle = 'rgba(255,255,255,.5)'; ctx.lineWidth = 1;
  ctx.beginPath(); ctx.arc(mouse.x, mouse.y, 6 + burst*14, 0, 7); ctx.stroke();

  requestAnimationFrame(frame);
}
requestAnimationFrame(frame);
</script>
</body>
</html>
