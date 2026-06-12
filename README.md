<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Brian Kerio — Fullstack Developer | Machine Learning Engineer</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=JetBrains+Mono:wght@300;400;600;700&family=Inter:wght@300;400;500;600;700&display=swap');
  
  * { margin: 0; padding: 0; box-sizing: border-box; }
  
  body {
    background: #080400;
    font-family: 'Inter', sans-serif;
    color: #f4da90;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    padding: 20px;
    overflow-x: hidden;
  }
  
  .container {
    width: 900px;
    max-width: 100%;
    position: relative;
    background: #0a0805;
    border: 1px solid #2a1f10;
    border-radius: 16px;
    padding: 40px 50px;
    box-shadow: 
      0 0 80px rgba(215, 145, 87, 0.08),
      0 0 200px rgba(134, 62, 30, 0.05),
      inset 0 1px 0 rgba(244, 218, 144, 0.05);
  }
  
  /* Background grid lines */
  .container::before {
    content: '';
    position: absolute;
    inset: 0;
    background-image: 
      linear-gradient(rgba(215, 145, 87, 0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(215, 145, 87, 0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    border-radius: 16px;
    pointer-events: none;
  }
  
  /* Floating particles */
  .particle {
    position: absolute;
    width: 2px;
    height: 2px;
    background: #d79157;
    border-radius: 50%;
    opacity: 0.4;
    animation: float 8s infinite ease-in-out;
  }
  @keyframes float {
    0%, 100% { transform: translateY(0) scale(1); opacity: 0.3; }
    50% { transform: translateY(-20px) scale(1.5); opacity: 0.8; }
  }
  
  /* Top tagline */
  .top-tagline {
    text-align: center;
    font-family: 'Orbitron', sans-serif;
    font-size: 11px;
    letter-spacing: 6px;
    color: #d79157;
    text-transform: uppercase;
    margin-bottom: 8px;
    opacity: 0.9;
  }
  .top-tagline::before, .top-tagline::after {
    content: '◆━━━';
    margin: 0 15px;
    color: #863e1e;
    letter-spacing: 2px;
  }
  
  /* Main name */
  .main-name {
    text-align: center;
    font-family: 'Orbitron', sans-serif;
    font-size: 72px;
    font-weight: 900;
    background: linear-gradient(180deg, #f4da90 0%, #d79157 50%, #863e1e 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1.1;
    margin-bottom: 8px;
    text-shadow: 0 0 60px rgba(215, 145, 87, 0.3);
    letter-spacing: 2px;
  }
  
  .subtitle {
    text-align: center;
    font-family: 'Inter', sans-serif;
    font-size: 16px;
    color: #b8956a;
    font-weight: 400;
    letter-spacing: 1px;
    margin-bottom: 25px;
  }
  
  /* Hero section layout */
  .hero-section {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 20px;
    margin-bottom: 30px;
    position: relative;
  }
  
  /* Stat boxes */
  .stat-box {
    background: rgba(10, 8, 5, 0.9);
    border: 1px solid rgba(215, 145, 87, 0.25);
    border-radius: 12px;
    padding: 16px 20px;
    min-width: 140px;
    text-align: center;
    position: relative;
    backdrop-filter: blur(10px);
    transition: all 0.3s ease;
  }
  .stat-box:hover {
    border-color: rgba(244, 218, 144, 0.5);
    box-shadow: 0 0 20px rgba(215, 145, 87, 0.15);
  }
  .stat-box .icon {
    font-size: 20px;
    margin-bottom: 6px;
    display: block;
  }
  .stat-box .number {
    font-family: 'Orbitron', sans-serif;
    font-size: 24px;
    font-weight: 700;
    color: #f4da90;
    display: block;
    line-height: 1.2;
  }
  .stat-box .label {
    font-size: 9px;
    color: #d79157;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    margin-top: 4px;
    display: block;
    line-height: 1.4;
  }
  
  /* Left & right stat columns */
  .stat-column {
    display: flex;
    flex-direction: column;
    gap: 12px;
    z-index: 2;
  }
  
  /* Center content */
  .center-content {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
  }
  
  /* Terminal box */
  .terminal-box {
    background: rgba(8, 6, 3, 0.95);
    border: 1px solid rgba(215, 145, 87, 0.2);
    border-radius: 10px;
    padding: 14px 22px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: #d79157;
    line-height: 1.8;
    margin-bottom: 20px;
    width: 100%;
    max-width: 380px;
    position: relative;
    overflow: hidden;
  }
  .terminal-box::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, #d79157, transparent);
    opacity: 0.5;
  }
  .terminal-line {
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .terminal-prompt {
    color: #863e1e;
    font-weight: 600;
  }
  .terminal-text {
    color: #b8956a;
  }
  .terminal-cursor {
    display: inline-block;
    width: 8px;
    height: 15px;
    background: #d79157;
    animation: blink 1s infinite;
    vertical-align: middle;
    margin-left: 2px;
  }
  @keyframes blink {
    0%, 50% { opacity: 1; }
    51%, 100% { opacity: 0; }
  }
  
  /* Africa Map */
  .africa-container {
    position: relative;
    width: 100%;
    height: 320px;
    margin: 10px 0;
  }
  
  .africa-map {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 420px;
    height: 420px;
  }
  
  /* SVG Africa outline with glow */
  .africa-svg {
    width: 100%;
    height: 100%;
    filter: drop-shadow(0 0 30px rgba(215, 145, 87, 0.4)) 
            drop-shadow(0 0 60px rgba(134, 62, 30, 0.2));
  }
  
  .africa-fill {
    fill: url(#africaGradient);
    stroke: #d79157;
    stroke-width: 1.5;
    opacity: 0.9;
  }
  
  .africa-inner {
    fill: none;
    stroke: rgba(244, 218, 144, 0.15);
    stroke-width: 0.5;
  }
  
  /* Network nodes on map */
  .network-node {
    position: absolute;
    width: 4px;
    height: 4px;
    background: #f4da90;
    border-radius: 50%;
    box-shadow: 0 0 8px #f4da90, 0 0 16px rgba(244, 218, 144, 0.4);
    animation: pulse 3s infinite ease-in-out;
  }
  @keyframes pulse {
    0%, 100% { transform: scale(1); opacity: 0.8; }
    50% { transform: scale(1.8); opacity: 1; }
  }
  
  .network-line {
    position: absolute;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(215, 145, 87, 0.3), transparent);
    transform-origin: left center;
  }
  
  /* Kenya highlight */
  .kenya-label {
    position: absolute;
    top: 52%;
    left: 58%;
    font-family: 'Orbitron', sans-serif;
    font-size: 10px;
    color: #f4da90;
    letter-spacing: 2px;
    background: rgba(134, 62, 30, 0.3);
    padding: 2px 8px;
    border-radius: 4px;
    border: 1px solid rgba(244, 218, 144, 0.3);
  }
  .kenya-dot {
    position: absolute;
    top: 50%;
    left: 56%;
    width: 8px;
    height: 8px;
    background: #f4da90;
    border-radius: 50%;
    box-shadow: 0 0 20px #f4da90, 0 0 40px rgba(244, 218, 144, 0.5);
    animation: pulse 2s infinite;
  }
  
  /* Tech orbit icons */
  .tech-orbit {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0; left: 0;
  }
  
  .tech-item {
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
    cursor: pointer;
    transition: transform 0.3s ease;
  }
  .tech-item:hover {
    transform: scale(1.1);
  }
  .tech-item .tech-icon {
    width: 44px;
    height: 44px;
    border: 1px solid rgba(215, 145, 87, 0.4);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    background: rgba(10, 8, 5, 0.8);
    backdrop-filter: blur(4px);
    box-shadow: 0 0 15px rgba(215, 145, 87, 0.1);
  }
  .tech-item .tech-label {
    font-size: 9px;
    color: #d79157;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    text-align: center;
    line-height: 1.3;
    font-weight: 500;
  }
  
  /* Position tech items around the map */
  .tech-aiml { top: 8%; left: 8%; }
  .tech-fintech { top: 38%; left: 2%; }
  .tech-cloud { top: 68%; left: 8%; }
  .tech-data { bottom: 5%; left: 42%; }
  .tech-robotics { top: 8%; right: 8%; }
  .tech-iot { top: 38%; right: 2%; }
  .tech-software { top: 68%; right: 8%; }
  
  /* About section */
  .about-section {
    background: rgba(10, 8, 5, 0.9);
    border: 1px solid rgba(215, 145, 87, 0.2);
    border-radius: 14px;
    padding: 28px 32px;
    margin-top: 20px;
    position: relative;
    backdrop-filter: blur(10px);
  }
  .about-section::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent 10%, #d79157 50%, transparent 90%);
    opacity: 0.6;
    border-radius: 14px 14px 0 0;
  }
  
  .about-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 16px;
  }
  .about-header .icon {
    font-size: 20px;
    color: #d79157;
  }
  .about-header h2 {
    font-family: 'Orbitron', sans-serif;
    font-size: 18px;
    color: #f4da90;
    font-weight: 700;
    letter-spacing: 1px;
  }
  
  .about-content {
    display: flex;
    gap: 30px;
    align-items: flex-start;
  }
  
  .about-text {
    flex: 1;
    font-size: 13px;
    line-height: 1.8;
    color: #b8956a;
    font-weight: 400;
  }
  
  .about-dots {
    width: 100px;
    height: 100px;
    flex-shrink: 0;
    opacity: 0.6;
  }
  
  /* Status cards row */
  .status-row {
    display: flex;
    gap: 14px;
    margin-top: 20px;
  }
  
  .status-card {
    flex: 1;
    background: rgba(8, 6, 3, 0.95);
    border: 1px solid rgba(215, 145, 87, 0.2);
    border-radius: 10px;
    padding: 14px 16px;
    display: flex;
    align-items: center;
    gap: 12px;
    transition: all 0.3s ease;
  }
  .status-card:hover {
    border-color: rgba(244, 218, 144, 0.4);
    box-shadow: 0 0 15px rgba(215, 145, 87, 0.1);
  }
  .status-card .status-icon {
    font-size: 22px;
    width: 36px;
    text-align: center;
  }
  .status-card .status-info {
    display: flex;
    flex-direction: column;
  }
  .status-card .status-label {
    font-size: 11px;
    color: #d79157;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 2px;
  }
  .status-card .status-value {
    font-family: 'Orbitron', sans-serif;
    font-size: 15px;
    color: #f4da90;
    font-weight: 600;
  }
  
  /* Connect section */
  .connect-section {
    margin-top: 24px;
  }
  .connect-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 16px;
  }
  .connect-header .icon {
    font-size: 18px;
    color: #d79157;
  }
  .connect-header h2 {
    font-family: 'Orbitron', sans-serif;
    font-size: 16px;
    color: #f4da90;
    font-weight: 700;
    letter-spacing: 1px;
  }
  
  .connect-grid {
    display: flex;
    gap: 12px;
    justify-content: space-between;
  }
  
  .connect-btn {
    flex: 1;
    background: rgba(8, 6, 3, 0.95);
    border: 1px solid rgba(215, 145, 87, 0.2);
    border-radius: 10px;
    padding: 14px 8px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    text-decoration: none;
    transition: all 0.3s ease;
    cursor: pointer;
  }
  .connect-btn:hover {
    border-color: rgba(244, 218, 144, 0.4);
    transform: translateY(-3px);
    box-shadow: 0 8px 25px rgba(215, 145, 87, 0.15);
  }
  .connect-btn .connect-icon {
    width: 36px;
    height: 36px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
  }
  .connect-btn .connect-label {
    font-size: 11px;
    color: #b8956a;
    letter-spacing: 0.5px;
  }
  
  /* Specific brand colors for icons */
  .connect-btn.linkedin .connect-icon { color: #0077B5; }
  .connect-btn.twitter .connect-icon { color: #fff; }
  .connect-btn.tiktok .connect-icon { color: #ff0050; }
  .connect-btn.whatsapp .connect-icon { color: #25D366; }
  .connect-btn.email .connect-icon { color: #D14836; }
  .connect-btn.website .connect-icon { color: #d79157; }
  
  /* SVG Definitions */
  .svg-defs {
    position: absolute;
    width: 0;
    height: 0;
  }
  
  /* Responsive */
  @media (max-width: 768px) {
    .container { padding: 20px; }
    .main-name { font-size: 42px; }
    .hero-section { flex-direction: column; align-items: center; }
    .stat-column { flex-direction: row; flex-wrap: wrap; justify-content: center; }
    .africa-container { height: 250px; }
    .africa-map { width: 300px; height: 300px; }
    .tech-item { position: relative; top: auto !important; left: auto !important; right: auto !important; bottom: auto !important; }
    .tech-orbit { position: relative; display: flex; flex-wrap: wrap; justify-content: center; gap: 15px; margin-top: 20px; }
    .about-content { flex-direction: column; }
    .status-row { flex-direction: column; }
    .connect-grid { flex-wrap: wrap; }
    .connect-btn { min-width: 100px; }
  }
</style>
</head>
<body>

<svg class="svg-defs">
  <defs>
    <linearGradient id="africaGradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a0f00;stop-opacity:0.95" />
      <stop offset="50%" style="stop-color:#2a1505;stop-opacity:0.9" />
      <stop offset="100%" style="stop-color:#1a0f00;stop-opacity:0.95" />
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>
</svg>

<div class="container">
  <!-- Floating particles -->
  <div class="particle" style="top:10%;left:15%;animation-delay:0s;"></div>
  <div class="particle" style="top:20%;left:85%;animation-delay:1s;"></div>
  <div class="particle" style="top:60%;left:10%;animation-delay:2s;"></div>
  <div class="particle" style="top:80%;left:80%;animation-delay:3s;"></div>
  <div class="particle" style="top:40%;left:90%;animation-delay:4s;"></div>
  <div class="particle" style="top:70%;left:20%;animation-delay:5s;"></div>
  
  <!-- Top tagline -->
  <div class="top-tagline">Building Intelligent Systems for Africa</div>
  
  <!-- Main Name -->
  <div class="main-name">Brian Kerio</div>
  <div class="subtitle">Fullstack Developer &nbsp;|&nbsp; Machine Learning Engineer</div>
  
  <!-- Hero Section -->
  <div class="hero-section">
    <!-- Left Stats -->
    <div class="stat-column">
      <div class="stat-box">
        <span class="icon">🚀</span>
        <span class="number">15+</span>
        <span class="label">Projects<br>Delivered</span>
      </div>
      <div class="stat-box">
        <span class="icon">📊</span>
        <span class="number">5000+</span>
        <span class="label">Transactions<br>Processed</span>
      </div>
      <div class="stat-box">
        <span class="icon">🧠</span>
        <span class="number">AI + IoT</span>
        <span class="label">Intelligent<br>Solutions</span>
      </div>
    </div>
    
    <!-- Center -->
    <div class="center-content">
      <!-- Terminal -->
      <div class="terminal-box">
        <div class="terminal-line">
          <span class="terminal-prompt">></span>
          <span class="terminal-text">Building intelligent systems...</span>
        </div>
        <div class="terminal-line">
          <span class="terminal-prompt">></span>
          <span class="terminal-text">Crafting scalable web solutions...</span>
        </div>
        <div class="terminal-line">
          <span class="terminal-prompt">></span>
          <span class="terminal-text">Exploring the frontiers of AI...</span>
        </div>
        <div class="terminal-line">
          <span class="terminal-prompt">></span>
          <span class="terminal-text">Turning coffee into code ☕</span>
          <span class="terminal-cursor"></span>
        </div>
      </div>
      
      <!-- Africa Map Container -->
      <div class="africa-container">
        <div class="africa-map">
          <svg class="africa-svg" viewBox="0 0 400 420" xmlns="http://www.w3.org/2000/svg">
            <!-- Simplified Africa continent path -->
            <path class="africa-fill" d="
              M 180 20
              C 160 20, 140 30, 130 45
              C 120 55, 115 70, 110 85
              C 105 100, 100 115, 95 130
              C 90 145, 85 160, 82 175
              C 78 190, 75 205, 72 220
              C 68 235, 65 250, 62 265
              C 58 280, 55 295, 58 310
              C 60 325, 68 340, 78 350
              C 88 360, 100 368, 115 372
              C 130 376, 145 378, 160 375
              C 175 372, 190 365, 205 355
              C 220 345, 235 332, 248 318
              C 260 304, 270 288, 278 272
              C 286 256, 292 240, 295 224
              C 298 208, 298 192, 295 176
              C 292 160, 286 144, 278 128
              C 270 112, 260 98, 248 86
              C 238 76, 228 68, 218 60
              C 208 52, 198 42, 190 32
              C 186 26, 183 22, 180 20
              Z
              M 295 180
              C 305 185, 315 192, 322 200
              C 328 208, 332 218, 334 228
              C 336 238, 335 248, 332 258
              C 329 268, 324 276, 318 282
              C 312 288, 305 292, 298 294
              C 291 296, 284 295, 278 292
              C 272 289, 268 284, 265 278
              C 262 272, 260 265, 260 258
              C 260 250, 262 242, 266 234
              C 270 226, 276 218, 282 210
              C 288 202, 292 190, 295 180
              Z
            "/>
            <!-- Inner detail lines -->
            <path class="africa-inner" d="M 130 80 Q 150 100 170 90" />
            <path class="africa-inner" d="M 110 150 Q 140 160 160 140" />
            <path class="africa-inner" d="M 100 220 Q 130 230 150 210" />
            <path class="africa-inner" d="M 120 300 Q 150 310 170 290" />
            <path class="africa-inner" d="M 200 100 Q 220 120 240 110" />
            <path class="africa-inner" d="M 220 200 Q 240 210 260 190" />
            <path class="africa-inner" d="M 180 280 Q 200 290 220 270" />
            <!-- Madagascar -->
            <ellipse class="africa-inner" cx="310" cy="240" rx="18" ry="35" transform="rotate(-15 310 240)" />
          </svg>
          
          <!-- Network nodes -->
          <div class="network-node" style="top:25%;left:30%;"></div>
          <div class="network-node" style="top:35%;left:45%;"></div>
          <div class="network-node" style="top:45%;left:25%;"></div>
          <div class="network-node" style="top:55%;left:55%;"></div>
          <div class="network-node" style="top:65%;left:35%;"></div>
          <div class="network-node" style="top:40%;left:60%;"></div>
          <div class="network-node" style="top:70%;left:50%;"></div>
          <div class="network-node" style="top:30%;left:65%;"></div>
          <div class="network-node" style="top:60%;left:20%;"></div>
          <div class="network-node" style="top:50%;left:40%;"></div>
          
          <!-- Kenya highlight -->
          <div class="kenya-dot"></div>
          <div class="kenya-label">KENYA</div>
        </div>
        
        <!-- Tech orbit items -->
        <div class="tech-orbit">
          <div class="tech-item tech-aiml">
            <div class="tech-icon">🧠</div>
            <div class="tech-label">AI / ML</div>
          </div>
          <div class="tech-item tech-fintech">
            <div class="tech-icon">💰</div>
            <div class="tech-label">FINTECH</div>
          </div>
          <div class="tech-item tech-cloud">
            <div class="tech-icon">☁️</div>
            <div class="tech-label">CLOUD<br>COMPUTING</div>
          </div>
          <div class="tech-item tech-data">
            <div class="tech-icon">🗄️</div>
            <div class="tech-label">DATA &<br>ANALYTICS</div>
          </div>
          <div class="tech-item tech-robotics">
            <div class="tech-icon">🤖</div>
            <div class="tech-label">ROBOTICS</div>
          </div>
          <div class="tech-item tech-iot">
            <div class="tech-icon">📡</div>
            <div class="tech-label">IoT &<br>EMBEDDED</div>
          </div>
          <div class="tech-item tech-software">
            <div class="tech-icon">💻</div>
            <div class="tech-label">SOFTWARE<br>ENGINEERING</div>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Right Stats -->
    <div class="stat-column">
      <div class="stat-box">
        <span class="icon">📍</span>
        <span class="number">EAST</span>
        <span class="label">Africa<br>Focused</span>
      </div>
      <div class="stat-box">
        <span class="icon">&lt;/&gt;</span>
        <span class="number">FULL</span>
        <span class="label">Stack<br>Developer</span>
      </div>
      <div class="stat-box">
        <span class="icon">⚙️</span>
        <span class="number">ML</span>
        <span class="label">Machine Learning<br>Engineer</span>
      </div>
    </div>
  </div>
  
  <!-- About Section -->
  <div class="about-section">
    <div class="about-header">
      <span class="icon">👤</span>
      <h2>About Me</h2>
    </div>
    <div class="about-content">
      <p class="about-text">
        I design and build intelligent systems that connect AI, fintech, and automation 
        with real-world infrastructure. I develop scalable solutions that enable real-time 
        payments, integrate IoT and embedded devices, and deliver actionable, data-driven 
        insights. My work focuses on creating practical, impactful technology that addresses 
        real challenges across East Africa.
      </p>
      <svg class="about-dots" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <!-- Dotted Africa pattern -->
        <defs>
          <pattern id="dotPattern" x="0" y="0" width="6" height="6" patternUnits="userSpaceOnUse">
            <circle cx="1" cy="1" r="1" fill="#d79157" opacity="0.6"/>
          </pattern>
        </defs>
        <ellipse cx="50" cy="50" rx="45" ry="48" fill="url(#dotPattern)" opacity="0.5"/>
        <ellipse cx="78" cy="55" rx="12" ry="18" fill="url(#dotPattern)" opacity="0.4" transform="rotate(-15 78 55)"/>
      </svg>
    </div>
    
    <!-- Status Cards -->
    <div class="status-row">
      <div class="status-card">
        <span class="status-icon">👁️</span>
        <div class="status-info">
          <span class="status-label">Profile Views</span>
          <span class="status-value">25K+</span>
        </div>
      </div>
      <div class="status-card">
        <span class="status-icon">🎯</span>
        <div class="status-info">
          <span class="status-label">Focus</span>
          <span class="status-value">Machine Learning & Internet of Things</span>
        </div>
      </div>
      <div class="status-card">
        <span class="status-icon">🤝</span>
        <div class="status-info">
          <span class="status-label">Status</span>
          <span class="status-value">Open to Collaborate</span>
        </div>
      </div>
    </div>
  </div>
  
  <!-- Connect Section -->
  <div class="connect-section">
    <div class="connect-header">
      <span class="icon">🔗</span>
      <h2>Connect with Me</h2>
    </div>
    <div class="connect-grid">
      <a href="https://linkedin.com/in/BrianKerio" class="connect-btn linkedin" target="_blank">
        <div class="connect-icon">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        </div>
        <span class="connect-label">LinkedIn</span>
      </a>
      <a href="https://x.com/@realbrianKerio" class="connect-btn twitter" target="_blank">
        <div class="connect-icon">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
        </div>
        <span class="connect-label">X (Twitter)</span>
      </a>
      <a href="https://www.tiktok.com/@realbriankerio" class="connect-btn tiktok" target="_blank">
        <div class="connect-icon">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M12.525.02c1.31-.02 2.61-.01 3.91-.02.08 1.53.63 3.09 1.75 4.17 1.12 1.11 2.7 1.62 4.24 1.79v4.03c-1.44-.05-2.89-.35-4.2-.97-.57-.26-1.1-.59-1.62-.93-.01 2.92.01 5.84-.02 8.75-.08 1.4-.54 2.79-1.35 3.94-1.31 1.92-3.58 3.17-5.91 3.21-1.43.08-2.86-.31-4.08-1.03-2.02-1.19-3.44-3.37-3.65-5.71-.02-.5-.03-1-.01-1.49.18-1.9 1.12-3.72 2.58-4.96 1.66-1.44 3.98-2.13 6.15-1.72.02 1.48-.04 2.96-.04 4.44-.99-.32-2.15-.23-3.02.37-.63.41-1.11 1.04-1.36 1.75-.21.51-.15 1.07-.14 1.61.24 1.64 1.82 3.02 3.5 2.87 1.12-.01 2.19-.66 2.77-1.61.19-.33.4-.67.41-1.06.1-1.79.06-3.57.07-5.36.01-4.03-.01-8.05.02-12.07z"/></svg>
        </div>
        <span class="connect-label">TikTok</span>
      </a>
      <a href="https://wa.me/254717000480" class="connect-btn whatsapp" target="_blank">
        <div class="connect-icon">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
        </div>
        <span class="connect-label">WhatsApp</span>
      </a>
      <a href="mailto:briankerio47@gmail.com" class="connect-btn email" target="_blank">
        <div class="connect-icon">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.11l-6.545-4.38v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-.904.732-1.636 1.636-1.636h.655L12 10.91l9.709-7.09h.655c.904 0 1.636.732 1.636 1.636z"/></svg>
        </div>
        <span class="connect-label">Email</span>
      </a>
      <a href="https://briankerio.com" class="connect-btn website" target="_blank">
        <div class="connect-icon">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm10.24 11h-3.2c-.1-2.3-.5-4.5-1.1-6.4 1.9.9 3.3 2.7 4.3 6.4zM12 2c1.7 0 3.2 2.6 3.9 6.5H8.1C8.8 4.6 10.3 2 12 2zM4.1 11H.9c1-3.7 2.4-5.5 4.3-6.4-.6 1.9-1 4.1-1.1 6.4zm.9 2h3.2c.1 2.3.5 4.5 1.1 6.4-1.9-.9-3.3-2.7-4.3-6.4zM12 22c-1.7 0-3.2-2.6-3.9-6.5h7.8C15.2 19.4 13.7 22 12 22zm-2.3-6.5H6.5c.3-1.5.7-2.9 1.2-4.1.3.7.6 1.4 1 2.1.4.7.7 1.4 1 2zm4.6 0c-.3-1.5-.7-2.9-1.2-4.1-.3.7-.6 1.4-1 2.1-.4.7-.7 1.4-1 2h3.2zm1.5 6.4c.6-1.9 1-4.1 1.1-6.4h3.2c-1 3.7-2.4 5.5-4.3 6.4zm1.1-8.4h-3.2c-.1-2.3-.5-4.5-1.1-6.4 1.9.9 3.3 2.7 4.3 6.4z"/></svg>
        </div>
        <span class="connect-label">Website</span>
      </a>
    </div>
  </div>
</div>

</body>
</html>
