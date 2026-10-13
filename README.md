<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 360" width="800" height="360" font-family="ui-monospace, SFMono-Regular, Menlo, Consolas, 'DejaVu Sans Mono', monospace">
<defs>
  <radialGradient id="heat" cx="50%" cy="62%" r="55%"><stop offset="0" stop-color="#ff4a12" stop-opacity=".45"/><stop offset=".55" stop-color="#7a1205" stop-opacity=".18"/><stop offset="1" stop-color="#08070c" stop-opacity="0"/></radialGradient>
  <linearGradient id="floor" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#ff5a1a" stop-opacity=".35"/><stop offset="1" stop-color="#ff5a1a" stop-opacity="0"/></linearGradient>
  
  <filter id="f1" filterUnits="userSpaceOnUse" primitiveUnits="userSpaceOnUse" x="0" y="-100" width="800" height="800" color-interpolation-filters="sRGB">
    <feTurbulence type="fractalNoise" baseFrequency="0.011 0.034" numOctaves="2" seed="3" stitchTiles="stitch" x="0" y="-100" width="256" height="256" result="n"/>
    <feTile in="n" result="t"/>
    <feOffset in="t" dx="0" dy="0" result="o"><animate attributeName="dy" from="0" to="-256" dur="2.2s" repeatCount="indefinite"/></feOffset>
    <feColorMatrix in="o" type="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 0 1" result="m"/>
    <feDisplacementMap in="SourceGraphic" in2="m" scale="70" xChannelSelector="R" yChannelSelector="G" result="d"/>
    <feGaussianBlur in="d" stdDeviation="5"/>
  </filter>
  
  <filter id="f2" filterUnits="userSpaceOnUse" primitiveUnits="userSpaceOnUse" x="0" y="-100" width="800" height="800" color-interpolation-filters="sRGB">
    <feTurbulence type="fractalNoise" baseFrequency="0.014 0.045" numOctaves="2" seed="8" stitchTiles="stitch" x="0" y="-100" width="256" height="256" result="n"/>
    <feTile in="n" result="t"/>
    <feOffset in="t" dx="0" dy="0" result="o"><animate attributeName="dy" from="0" to="-256" dur="1.6s" repeatCount="indefinite"/></feOffset>
    <feColorMatrix in="o" type="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 0 1" result="m"/>
    <feDisplacementMap in="SourceGraphic" in2="m" scale="46" xChannelSelector="R" yChannelSelector="G" result="d"/>
    <feGaussianBlur in="d" stdDeviation="3.2"/>
  </filter>
  
  <filter id="f3" filterUnits="userSpaceOnUse" primitiveUnits="userSpaceOnUse" x="0" y="-100" width="800" height="800" color-interpolation-filters="sRGB">
    <feTurbulence type="fractalNoise" baseFrequency="0.018 0.06" numOctaves="2" seed="5" stitchTiles="stitch" x="0" y="-100" width="256" height="256" result="n"/>
    <feTile in="n" result="t"/>
    <feOffset in="t" dx="0" dy="0" result="o"><animate attributeName="dy" from="0" to="-256" dur="1.2s" repeatCount="indefinite"/></feOffset>
    <feColorMatrix in="o" type="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 0 1" result="m"/>
    <feDisplacementMap in="SourceGraphic" in2="m" scale="28" xChannelSelector="R" yChannelSelector="G" result="d"/>
    <feGaussianBlur in="d" stdDeviation="1.8"/>
  </filter>
  <filter id="soft"><feGaussianBlur stdDeviation="1.4"/></filter>
</defs>
<rect width="800" height="360" rx="18" fill="#08070c"/>
<rect width="800" height="360" rx="18" fill="url(#heat)">
  <animate attributeName="opacity" values="1;.78;1;.9;1" dur="1.7s" repeatCount="indefinite"/>
</rect>
<g transform="translate(25 0)">
  <g filter="url(#f1)" fill="none" stroke="#d41a00" stroke-width="50" stroke-linecap="round" stroke-linejoin="round" opacity="0.9">
  <path d="M100 110 L160 195 L220 110 M160 195 L160 270"/>
  <ellipse cx="320" cy="190" rx="58" ry="80"/>
  <path d="M538 150 C528 122 500 110 480 110 C440 110 420 146 420 190 C420 234 445 270 485 270 C522 270 540 246 540 205 L488 205"/>
  <path d="M610 110 L610 270"/></g>
  <g filter="url(#f2)" fill="none" stroke="#ff6a00" stroke-width="38" stroke-linecap="round" stroke-linejoin="round" opacity="1">
  <path d="M100 110 L160 195 L220 110 M160 195 L160 270"/>
  <ellipse cx="320" cy="190" rx="58" ry="80"/>
  <path d="M538 150 C528 122 500 110 480 110 C440 110 420 146 420 190 C420 234 445 270 485 270 C522 270 540 246 540 205 L488 205"/>
  <path d="M610 110 L610 270"/></g>
  <g filter="url(#f3)" fill="none" stroke="#ffc21a" stroke-width="24" stroke-linecap="round" stroke-linejoin="round" opacity="1">
  <path d="M100 110 L160 195 L220 110 M160 195 L160 270"/>
  <ellipse cx="320" cy="190" rx="58" ry="80"/>
  <path d="M538 150 C528 122 500 110 480 110 C440 110 420 146 420 190 C420 234 445 270 485 270 C522 270 540 246 540 205 L488 205"/>
  <path d="M610 110 L610 270"/></g>
  <g filter="url(#soft)" fill="none" stroke="#fff4c4" stroke-width="8" stroke-linecap="round" stroke-linejoin="round" opacity=".95">
  <path d="M100 110 L160 195 L220 110 M160 195 L160 270"/>
  <ellipse cx="320" cy="190" rx="58" ry="80"/>
  <path d="M538 150 C528 122 500 110 480 110 C440 110 420 146 420 190 C420 234 445 270 485 270 C522 270 540 246 540 205 L488 205"/>
  <path d="M610 110 L610 270"/></g>
  <circle r="1.8" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="90;91;92" dur="3.3s" begin="-0.2s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="262;93" dur="3.3s" begin="-0.2s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.3s" begin="-0.2s" repeatCount="indefinite"/>
  </circle><circle r="1.8" fill="#ff9a1f" opacity="0">
    <animate attributeName="cx" values="342;335;331" dur="3.2s" begin="-1.1s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="243;106" dur="3.2s" begin="-1.1s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.2s" begin="-1.1s" repeatCount="indefinite"/>
  </circle><circle r="2.6" fill="#ff5a1a" opacity="0">
    <animate attributeName="cx" values="408;413;416" dur="3.5s" begin="-0.4s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="178;-30" dur="3.5s" begin="-0.4s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.5s" begin="-0.4s" repeatCount="indefinite"/>
  </circle><circle r="1.9" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="389;371;360" dur="3.1s" begin="-1.5s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="254;132" dur="3.1s" begin="-1.5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.1s" begin="-1.5s" repeatCount="indefinite"/>
  </circle><circle r="2.4" fill="#ff9a1f" opacity="0">
    <animate attributeName="cx" values="401;377;362" dur="2.4s" begin="-1.9s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="265;83" dur="2.4s" begin="-1.9s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="2.4s" begin="-1.9s" repeatCount="indefinite"/>
  </circle><circle r="2.9" fill="#ff5a1a" opacity="0">
    <animate attributeName="cx" values="420;438;449" dur="3.4s" begin="-4.5s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="152;-54" dur="3.4s" begin="-4.5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.4s" begin="-4.5s" repeatCount="indefinite"/>
  </circle><circle r="1.4" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="603;633;651" dur="2.9s" begin="-4.0s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="273;65" dur="2.9s" begin="-4.0s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="2.9s" begin="-4.0s" repeatCount="indefinite"/>
  </circle><circle r="1.7" fill="#ff9a1f" opacity="0">
    <animate attributeName="cx" values="522;542;554" dur="3.2s" begin="-3.1s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="153;-81" dur="3.2s" begin="-3.1s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.2s" begin="-3.1s" repeatCount="indefinite"/>
  </circle><circle r="2.7" fill="#ff5a1a" opacity="0">
    <animate attributeName="cx" values="280;291;297" dur="2.4s" begin="-3.3s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="274;88" dur="2.4s" begin="-3.3s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="2.4s" begin="-3.3s" repeatCount="indefinite"/>
  </circle><circle r="2.7" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="365;384;395" dur="3.7s" begin="-4.6s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="280;109" dur="3.7s" begin="-4.6s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.7s" begin="-4.6s" repeatCount="indefinite"/>
  </circle><circle r="1.3" fill="#ff9a1f" opacity="0">
    <animate attributeName="cx" values="364;355;350" dur="2.5s" begin="-0.3s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="258;124" dur="2.5s" begin="-0.3s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="2.5s" begin="-0.3s" repeatCount="indefinite"/>
  </circle><circle r="1.6" fill="#ff5a1a" opacity="0">
    <animate attributeName="cx" values="387;392;395" dur="3.8s" begin="-0.5s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="199;58" dur="3.8s" begin="-0.5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.8s" begin="-0.5s" repeatCount="indefinite"/>
  </circle><circle r="2.8" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="387;391;394" dur="2.7s" begin="-4.9s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="279;66" dur="2.7s" begin="-4.9s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="2.7s" begin="-4.9s" repeatCount="indefinite"/>
  </circle><circle r="2.7" fill="#ff9a1f" opacity="0">
    <animate attributeName="cx" values="290;275;266" dur="4.3s" begin="-2.5s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="190;6" dur="4.3s" begin="-2.5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="4.3s" begin="-2.5s" repeatCount="indefinite"/>
  </circle><circle r="2.1" fill="#ff5a1a" opacity="0">
    <animate attributeName="cx" values="610;621;628" dur="5.1s" begin="-0.7s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="171;-65" dur="5.1s" begin="-0.7s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="5.1s" begin="-0.7s" repeatCount="indefinite"/>
  </circle><circle r="2.6" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="246;230;220" dur="3.5s" begin="-4.4s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="213;32" dur="3.5s" begin="-4.4s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.5s" begin="-4.4s" repeatCount="indefinite"/>
  </circle><circle r="2.6" fill="#ff9a1f" opacity="0">
    <animate attributeName="cx" values="144;166;179" dur="5.0s" begin="-1.3s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="248;88" dur="5.0s" begin="-1.3s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="5.0s" begin="-1.3s" repeatCount="indefinite"/>
  </circle><circle r="0.8" fill="#ff5a1a" opacity="0">
    <animate attributeName="cx" values="325;343;354" dur="2.5s" begin="-0.2s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="222;67" dur="2.5s" begin="-0.2s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="2.5s" begin="-0.2s" repeatCount="indefinite"/>
  </circle><circle r="2.2" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="261;270;276" dur="5.4s" begin="-2.5s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="248;108" dur="5.4s" begin="-2.5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="5.4s" begin="-2.5s" repeatCount="indefinite"/>
  </circle><circle r="1.3" fill="#ff9a1f" opacity="0">
    <animate attributeName="cx" values="357;345;338" dur="3.2s" begin="-2.5s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="231;56" dur="3.2s" begin="-2.5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.2s" begin="-2.5s" repeatCount="indefinite"/>
  </circle><circle r="1.9" fill="#ff5a1a" opacity="0">
    <animate attributeName="cx" values="355;359;361" dur="2.8s" begin="-3.1s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="256;77" dur="2.8s" begin="-3.1s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="2.8s" begin="-3.1s" repeatCount="indefinite"/>
  </circle><circle r="2.5" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="205;187;176" dur="3.5s" begin="-0.5s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="224;58" dur="3.5s" begin="-0.5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.5s" begin="-0.5s" repeatCount="indefinite"/>
  </circle><circle r="2.8" fill="#ff9a1f" opacity="0">
    <animate attributeName="cx" values="366;380;388" dur="3.6s" begin="-0.8s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="259;39" dur="3.6s" begin="-0.8s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.6s" begin="-0.8s" repeatCount="indefinite"/>
  </circle><circle r="1.4" fill="#ff5a1a" opacity="0">
    <animate attributeName="cx" values="220;224;226" dur="3.1s" begin="-1.6s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="269;66" dur="3.1s" begin="-1.6s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.1s" begin="-1.6s" repeatCount="indefinite"/>
  </circle><circle r="1.9" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="318;335;345" dur="3.7s" begin="-3.7s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="152;-62" dur="3.7s" begin="-3.7s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.7s" begin="-3.7s" repeatCount="indefinite"/>
  </circle><circle r="2.5" fill="#ff9a1f" opacity="0">
    <animate attributeName="cx" values="100;129;146" dur="3.9s" begin="-3.1s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="151;-70" dur="3.9s" begin="-3.1s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.9s" begin="-3.1s" repeatCount="indefinite"/>
  </circle><circle r="1.3" fill="#ff5a1a" opacity="0">
    <animate attributeName="cx" values="575;590;599" dur="2.9s" begin="-1.8s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="212;-28" dur="2.9s" begin="-1.8s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="2.9s" begin="-1.8s" repeatCount="indefinite"/>
  </circle><circle r="1.2" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="344;319;304" dur="4.1s" begin="-3.0s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="279;121" dur="4.1s" begin="-3.0s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="4.1s" begin="-3.0s" repeatCount="indefinite"/>
  </circle><circle r="2.9" fill="#ff9a1f" opacity="0">
    <animate attributeName="cx" values="341;363;376" dur="4.9s" begin="-0.4s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="225;18" dur="4.9s" begin="-0.4s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="4.9s" begin="-0.4s" repeatCount="indefinite"/>
  </circle><circle r="1.6" fill="#ff5a1a" opacity="0">
    <animate attributeName="cx" values="359;362;364" dur="2.9s" begin="-4.6s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="236;99" dur="2.9s" begin="-4.6s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="2.9s" begin="-4.6s" repeatCount="indefinite"/>
  </circle><circle r="2.2" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="276;294;305" dur="4.9s" begin="-0.1s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="223;-2" dur="4.9s" begin="-0.1s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="4.9s" begin="-0.1s" repeatCount="indefinite"/>
  </circle><circle r="1.1" fill="#ff9a1f" opacity="0">
    <animate attributeName="cx" values="507;520;528" dur="3.0s" begin="-3.7s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="251;119" dur="3.0s" begin="-3.7s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.0s" begin="-3.7s" repeatCount="indefinite"/>
  </circle><circle r="1.6" fill="#ff5a1a" opacity="0">
    <animate attributeName="cx" values="548;549;550" dur="3.4s" begin="-2.5s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="175;45" dur="3.4s" begin="-2.5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="3.4s" begin="-2.5s" repeatCount="indefinite"/>
  </circle><circle r="3.0" fill="#ffd23a" opacity="0">
    <animate attributeName="cx" values="517;541;556" dur="4.0s" begin="-4.8s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="265;100" dur="4.0s" begin="-4.8s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0;1;.8;0" keyTimes="0;.15;.6;1" dur="4.0s" begin="-4.8s" repeatCount="indefinite"/>
  </circle>
</g>
<rect x="60" y="292" width="680" height="3" rx="1.5" fill="url(#floor)" opacity=".7"/>
<text x="400" y="330" text-anchor="middle" font-size="13" letter-spacing="6" fill="#9a8f8a">BUILD  &#183;  SHIP  &#183;  REPEAT</text>
</svg>
