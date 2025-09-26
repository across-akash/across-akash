# 🦖 Dino Dash (Markdown Edition)

Welcome! Click or tap inside the game window to make the dinosaur jump. The cactus will keep looping from right to left—time your jumps so the cactus passes underneath while the dino is mid-air.

<svg viewBox="0 0 600 200" width="100%" style="max-width: 640px; border: 2px solid #222; border-radius: 12px; background: linear-gradient(#87CEEB, #B0E0E6); font-family: 'Segoe UI', system-ui, sans-serif;">
  <style>
    .ground { fill: #5D4037; }
    .dust { fill: rgba(255, 255, 255, 0.6); }
    .dino { fill: #2ecc71; stroke: #145a32; stroke-width: 3; }
    .cactus { fill: #27ae60; stroke: #1e8449; stroke-width: 3; }
    .cloud { fill: rgba(255, 255, 255, 0.85); }
    text { fill: #ffffff; font-size: 18px; font-weight: 600; letter-spacing: 1px; }
  </style>

  <rect x="0" y="0" width="600" height="200" fill="transparent" id="gameArea" pointer-events="all" />
  <text x="24" y="36">Score yourself: +1 each time the cactus loops!</text>

  <g>
    <rect class="ground" x="0" y="170" width="600" height="30" />
    <rect class="ground" x="0" y="166" width="600" height="6" fill="#795548" />
  </g>

  <g id="dino" transform="translate(0,0)">
    <rect class="dino" x="60" y="120" width="40" height="50" rx="6" />
    <rect class="dino" x="95" y="140" width="18" height="30" rx="4" />
    <circle fill="#145a32" cx="85" cy="135" r="4" />
    <rect fill="#145a32" x="72" y="150" width="16" height="6" rx="3" />

    <animate attributeName="y" begin="gameArea.click" dur="0.65s" values="0;-70;0" keyTimes="0;0.5;1" calcMode="spline" keySplines="0.42 0 0.58 1;0.42 0 0.58 1" />
  </g>

  <g id="cactus" transform="translate(0,0)">
    <rect class="cactus" x="0" y="120" width="28" height="52" rx="6" />
    <rect class="cactus" x="-18" y="140" width="22" height="32" rx="6" />
    <rect class="cactus" x="22" y="146" width="18" height="26" rx="6" />

    <animateTransform attributeName="transform" attributeType="XML" type="translate" from="650 0" to="-120 0" dur="2.4s" repeatCount="indefinite" />
  </g>

  <g opacity="0.75">
    <g>
      <ellipse class="cloud" cx="160" cy="60" rx="28" ry="18" />
      <ellipse class="cloud" cx="182" cy="54" rx="20" ry="14" />
      <ellipse class="cloud" cx="140" cy="56" rx="20" ry="16" />
      <animateTransform attributeName="transform" type="translate" from="0 0" to="-200 0" dur="18s" repeatCount="indefinite" />
    </g>
    <g>
      <ellipse class="cloud" cx="480" cy="42" rx="24" ry="14" />
      <ellipse class="cloud" cx="504" cy="38" rx="18" ry="12" />
      <ellipse class="cloud" cx="456" cy="40" rx="18" ry="12" />
      <animateTransform attributeName="transform" type="translate" from="0 0" to="-260 0" dur="24s" repeatCount="indefinite" />
    </g>
  </g>

  <g opacity="0.4">
    <circle class="dust" cx="520" cy="176" r="4">
      <animate attributeName="cx" from="520" to="-40" dur="3s" repeatCount="indefinite" />
      <animate attributeName="opacity" values="0;1;0" keyTimes="0;0.5;1" dur="3s" repeatCount="indefinite" />
    </circle>
    <circle class="dust" cx="460" cy="176" r="3">
      <animate attributeName="cx" from="460" to="-60" dur="2.4s" repeatCount="indefinite" />
      <animate attributeName="opacity" values="0;1;0" keyTimes="0;0.4;1" dur="2.4s" repeatCount="indefinite" />
    </circle>
  </g>

  <text x="24" y="196" font-size="14" fill="#212121">Tip: hover or tap repeatedly to keep the jumps coming.</text>
</svg>

> 💡 **Challenge:** Count how many loops you can survive. If the cactus visually collides with the dino, consider that a hit and restart!

---

Want to take it further? Fork this repository and turn the SVG into a full game using canvas + JavaScript on a GitHub Page!
