
<style>
@import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@400;700;900&family=Inter:wght@300;400;500&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
.root{background:#030a03;color:#00ff41;font-family:'Share Tech Mono',monospace;overflow-x:hidden;min-height:100vh}
.scanline{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:999;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,255,65,0.015) 2px,rgba(0,255,65,0.015) 4px)}
.grid-bg{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:0;opacity:0.07;background-image:linear-gradient(rgba(0,255,65,0.5) 1px,transparent 1px),linear-gradient(90deg,rgba(0,255,65,0.5) 1px,transparent 1px);background-size:40px 40px}
.content{position:relative;z-index:1}

/* BOOT SCREEN */
#bootScreen{position:relative;min-height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:40px 20px;text-align:center}
.boot-log{font-size:11px;color:#00cc33;letter-spacing:1px;margin-bottom:48px;line-height:2;opacity:0;animation:fadeIn 0.5s 0.2s forwards}
@keyframes fadeIn{to{opacity:1}}
.boot-line{display:block;text-align:left;max-width:420px;margin:0 auto}
.ok{color:#00ff41}
.err{color:#ff4444}

/* ROBOT */
.robot-wrap{position:relative;width:160px;height:220px;margin:0 auto 32px;animation:robotFloat 3s ease-in-out infinite}
@keyframes robotFloat{0%,100%{transform:translateY(0)}50%{transform:translateY(-12px)}}

/* MAIN */
#mainScreen{display:none;padding:0 0 40px}

/* HERO */
.hero{text-align:center;padding:56px 24px 40px;position:relative}
.terminal-tag{font-size:11px;color:#005510;letter-spacing:3px;margin-bottom:24px}
.name-wrap{margin-bottom:8px}
.name{font-family:'Orbitron',monospace;font-size:clamp(26px,5.5vw,52px);font-weight:900;color:#00ff41;letter-spacing:4px;text-shadow:0 0 20px rgba(0,255,65,0.4);animation:glitch 5s infinite}
@keyframes glitch{
  0%,90%,100%{text-shadow:0 0 20px rgba(0,255,65,0.4)}
  91%{text-shadow:-3px 0 #ff0055,3px 0 #00ffff,0 0 20px rgba(0,255,65,0.4)}
  92%{text-shadow:3px 0 #ff0055,-3px 0 #00ffff,0 0 20px rgba(0,255,65,0.4)}
  93%{text-shadow:0 0 20px rgba(0,255,65,0.4)}
}
.subtitle{font-size:12px;color:#005510;letter-spacing:5px;text-transform:uppercase;margin-bottom:20px}
.tw-wrap{height:26px;display:flex;align-items:center;justify-content:center;margin-bottom:32px}
.tw{font-size:14px;color:#39ff14;letter-spacing:2px}
.cursor{display:inline-block;width:10px;height:16px;background:#00ff41;margin-left:2px;vertical-align:middle;animation:blink 0.7s step-end infinite}
@keyframes blink{50%{opacity:0}}
.status-pill{display:inline-flex;align-items:center;gap:8px;padding:8px 20px;border:1px solid #003a00;border-radius:4px;background:rgba(0,255,65,0.04);font-size:11px;color:#39ff14;letter-spacing:2px;margin-bottom:36px}
.pulse{width:7px;height:7px;border-radius:50%;background:#00ff41;animation:pulse 1.2s ease-in-out infinite}
@keyframes pulse{0%,100%{transform:scale(1);opacity:1}50%{transform:scale(1.5);opacity:0.5}}
.cta-row{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-bottom:8px}
.btn-g{display:inline-flex;align-items:center;gap:8px;padding:11px 22px;background:#00ff41;color:#030a03;border:none;border-radius:3px;font-family:'Share Tech Mono',monospace;font-size:12px;font-weight:700;letter-spacing:2px;cursor:pointer;text-decoration:none;transition:all 0.2s;text-transform:uppercase}
.btn-g:hover{background:#39ff14;box-shadow:0 0 24px rgba(0,255,65,0.5);transform:translateY(-2px)}
.btn-o{display:inline-flex;align-items:center;gap:8px;padding:11px 22px;background:transparent;color:#00ff41;border:1px solid #00ff41;border-radius:3px;font-family:'Share Tech Mono',monospace;font-size:12px;letter-spacing:2px;cursor:pointer;text-decoration:none;transition:all 0.2s;text-transform:uppercase}
.btn-o:hover{background:rgba(0,255,65,0.08);box-shadow:0 0 16px rgba(0,255,65,0.3);transform:translateY(-2px)}

.sep{height:1px;background:linear-gradient(90deg,transparent,#00ff41,transparent);margin:0 40px;opacity:0.2}

/* SECTIONS */
.section{padding:44px 24px;max-width:860px;margin:0 auto}
.sec-label{font-size:10px;color:#005510;letter-spacing:4px;text-transform:uppercase;margin-bottom:6px}
.sec-title{font-family:'Orbitron',monospace;font-size:18px;font-weight:700;color:#00ff41;margin-bottom:28px;text-shadow:0 0 10px rgba(0,255,65,0.2)}

/* ABOUT CARDS */
.about-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(175px,1fr));gap:14px;margin-bottom:8px}
.acard{background:rgba(0,255,65,0.03);border:1px solid #003a00;border-radius:4px;padding:18px 14px;text-align:center;transition:all 0.3s;cursor:default}
.acard:hover{border-color:#00ff41;background:rgba(0,255,65,0.07);box-shadow:0 0 20px rgba(0,255,65,0.1);transform:translateY(-3px)}
.a-ico{width:36px;height:36px;border:1px solid #003a00;border-radius:50%;display:flex;align-items:center;justify-content:center;margin:0 auto 10px;font-size:16px;background:rgba(0,255,65,0.06)}
.acard h3{font-size:11px;color:#39ff14;letter-spacing:2px;text-transform:uppercase;margin-bottom:6px}
.acard p{font-size:11px;color:#005510;line-height:1.7}

/* TECH STACK */
.tech-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(80px,1fr));gap:10px}
.tchip{display:flex;flex-direction:column;align-items:center;gap:7px;padding:14px 6px;background:rgba(0,255,65,0.02);border:1px solid #003a00;border-radius:4px;font-size:11px;color:#005510;transition:all 0.3s;cursor:default;letter-spacing:1px}
.tchip:hover{border-color:#00ff41;background:rgba(0,255,65,0.07);color:#00ff41;transform:translateY(-3px);box-shadow:0 4px 16px rgba(0,255,65,0.12)}
.ti{font-size:18px;line-height:1;width:24px;height:24px;display:flex;align-items:center;justify-content:center}

/* CONNECT */
.conn-grid{display:flex;gap:12px;flex-wrap:wrap;justify-content:center}
.cbtn{display:inline-flex;align-items:center;gap:10px;padding:12px 20px;border:1px solid #003a00;border-radius:4px;background:rgba(0,255,65,0.02);color:#39ff14;font-size:12px;font-family:'Share Tech Mono',monospace;text-decoration:none;cursor:pointer;transition:all 0.3s;letter-spacing:1px}
.cbtn:hover{border-color:#00ff41;background:rgba(0,255,65,0.08);box-shadow:0 0 16px rgba(0,255,65,0.15);transform:translateY(-2px)}

/* TERMINAL BLOCK */
.terminal{background:#000;border:1px solid #003a00;border-radius:4px;padding:16px 18px;font-size:12px;line-height:2;max-width:500px;margin:0 auto}
.t-bar{display:flex;gap:6px;margin-bottom:12px}
.t-dot{width:10px;height:10px;border-radius:50%}
.prompt{color:#005510}
.cmd{color:#00ff41}
.out{color:#39ff14}
.quote{font-size:12px;color:#005510;font-style:italic;text-align:center;padding:24px 16px 8px;max-width:480px;margin:0 auto;line-height:2;letter-spacing:1px}
.footer-bar{height:4px;background:linear-gradient(90deg,#000,#003a00,#00ff41,#39ff14,#00ff41,#003a00,#000);background-size:200% 100%;animation:wave 2.5s linear infinite}
@keyframes wave{0%{background-position:0% 0%}100%{background-position:200% 0%}}

/* ROBOT SVG animations */
@keyframes eyeblink{0%,90%,100%{transform:scaleY(1)}95%{transform:scaleY(0.1)}}
@keyframes antennaPulse{0%,100%{opacity:1;r:3}50%{opacity:0.3;r:5}}
@keyframes armSwing{0%,100%{transform:rotate(0deg)}50%{transform:rotate(8deg)}}
@keyframes earPing{0%,100%{opacity:0.4}50%{opacity:1}}
</style>

<div class="root">
  <div class="scanline"></div>
  <div class="grid-bg"></div>
  <div class="content">

    <!-- BOOT SCREEN -->
    <div id="bootScreen">
      <div class="boot-log">
        <span class="boot-line" id="bl0"></span>
        <span class="boot-line" id="bl1"></span>
        <span class="boot-line" id="bl2"></span>
        <span class="boot-line" id="bl3"></span>
        <span class="boot-line" id="bl4"></span>
        <span class="boot-line" id="bl5"></span>
      </div>

      <!-- ROBOT SVG -->
      <div class="robot-wrap" id="robotWrap">
        <svg width="160" height="220" viewBox="0 0 160 220" fill="none" xmlns="http://www.w3.org/2000/svg">
          <!-- Antenna -->
          <line x1="80" y1="10" x2="80" y2="30" stroke="#00ff41" stroke-width="2"/>
          <circle cx="80" cy="7" r="4" fill="#00ff41" style="animation:antennaPulse 1.5s ease-in-out infinite"/>
          <!-- Side ears/antennas -->
          <line x1="44" y1="50" x2="30" y2="42" stroke="#003a00" stroke-width="1.5"/>
          <circle cx="28" cy="41" r="3" fill="#003a00" style="animation:earPing 2s ease-in-out infinite"/>
          <line x1="116" y1="50" x2="130" y2="42" stroke="#003a00" stroke-width="1.5"/>
          <circle cx="132" cy="41" r="3" fill="#003a00" style="animation:earPing 2s ease-in-out infinite 0.5s"/>
          <!-- Head -->
          <rect x="40" y="28" width="80" height="64" rx="10" fill="#030a03" stroke="#00ff41" stroke-width="1.5"/>
          <!-- Head inner border -->
          <rect x="46" y="34" width="68" height="52" rx="7" fill="transparent" stroke="#003a00" stroke-width="0.5"/>
          <!-- Eyes -->
          <g style="transform-origin:62px 58px;animation:eyeblink 4s ease-in-out infinite">
            <rect x="50" y="50" width="24" height="16" rx="4" fill="#00ff41" opacity="0.15"/>
            <rect x="52" y="52" width="20" height="12" rx="3" fill="#00ff41" opacity="0.3"/>
            <rect x="59" y="55" width="6" height="6" rx="1" fill="#00ff41"/>
          </g>
          <g style="transform-origin:98px 58px;animation:eyeblink 4s ease-in-out infinite 0.1s">
            <rect x="86" y="50" width="24" height="16" rx="4" fill="#00ff41" opacity="0.15"/>
            <rect x="88" y="52" width="20" height="12" rx="3" fill="#00ff41" opacity="0.3"/>
            <rect x="95" y="55" width="6" height="6" rx="1" fill="#00ff41"/>
          </g>
          <!-- Nose indicator -->
          <rect x="76" y="68" width="8" height="3" rx="1" fill="#003a00"/>
          <!-- Mouth LED strip -->
          <rect x="52" y="76" width="56" height="8" rx="4" fill="#030a03" stroke="#003a00" stroke-width="0.5"/>
          <rect x="55" y="78" width="8" height="4" rx="2" fill="#00ff41" opacity="0.9"/>
          <rect x="66" y="78" width="8" height="4" rx="2" fill="#00ff41" opacity="0.6"/>
          <rect x="77" y="78" width="8" height="4" rx="2" fill="#00ff41" opacity="0.9"/>
          <rect x="88" y="78" width="8" height="4" rx="2" fill="#00ff41" opacity="0.4"/>
          <rect x="99" y="78" width="6" height="4" rx="2" fill="#00ff41" opacity="0.7"/>

          <!-- Neck -->
          <rect x="70" y="92" width="20" height="12" rx="2" fill="#030a03" stroke="#003a00" stroke-width="1"/>
          <line x1="75" y1="94" x2="75" y2="102" stroke="#003a00" stroke-width="0.5"/>
          <line x1="80" y1="94" x2="80" y2="102" stroke="#003a00" stroke-width="0.5"/>
          <line x1="85" y1="94" x2="85" y2="102" stroke="#003a00" stroke-width="0.5"/>

          <!-- Body -->
          <rect x="28" y="104" width="104" height="76" rx="8" fill="#030a03" stroke="#00ff41" stroke-width="1.5"/>
          <!-- Body inner -->
          <rect x="34" y="110" width="92" height="64" rx="5" fill="transparent" stroke="#003a00" stroke-width="0.5"/>
          <!-- Chest panel: circuit lines -->
          <rect x="42" y="118" width="36" height="28" rx="3" fill="rgba(0,255,65,0.04)" stroke="#003a00" stroke-width="0.5"/>
          <line x1="48" y1="126" x2="72" y2="126" stroke="#003a00" stroke-width="0.5"/>
          <line x1="48" y1="130" x2="65" y2="130" stroke="#003a00" stroke-width="0.5"/>
          <line x1="48" y1="134" x2="70" y2="134" stroke="#003a00" stroke-width="0.5"/>
          <line x1="48" y1="138" x2="60" y2="138" stroke="#003a00" stroke-width="0.5"/>
          <!-- Power core -->
          <circle cx="106" cy="132" r="16" fill="rgba(0,255,65,0.05)" stroke="#003a00" stroke-width="0.5"/>
          <circle cx="106" cy="132" r="10" fill="rgba(0,255,65,0.08)" stroke="#00ff41" stroke-width="1"/>
          <circle cx="106" cy="132" r="5" fill="#00ff41" opacity="0.8" style="animation:antennaPulse 2s ease-in-out infinite"/>
          <!-- Body bottom bar -->
          <rect x="42" y="152" width="76" height="6" rx="3" fill="rgba(0,255,65,0.06)" stroke="#003a00" stroke-width="0.5"/>
          <rect x="44" y="153" width="20" height="4" rx="2" fill="#00ff41" opacity="0.6"/>
          <rect x="66" y="153" width="14" height="4" rx="2" fill="#00ff41" opacity="0.3"/>
          <rect x="82" y="153" width="18" height="4" rx="2" fill="#00ff41" opacity="0.5"/>

          <!-- Left arm -->
          <g style="transform-origin:28px 120px;animation:armSwing 3s ease-in-out infinite">
            <rect x="6" y="104" width="22" height="52" rx="8" fill="#030a03" stroke="#003a00" stroke-width="1"/>
            <rect x="10" y="112" width="14" height="24" rx="3" fill="rgba(0,255,65,0.04)" stroke="#003a00" stroke-width="0.5"/>
            <circle cx="17" cy="148" r="6" fill="#030a03" stroke="#003a00" stroke-width="1"/>
          </g>
          <!-- Right arm -->
          <g style="transform-origin:132px 120px;animation:armSwing 3s ease-in-out infinite reverse">
            <rect x="132" y="104" width="22" height="52" rx="8" fill="#030a03" stroke="#003a00" stroke-width="1"/>
            <rect x="136" y="112" width="14" height="24" rx="3" fill="rgba(0,255,65,0.04)" stroke="#003a00" stroke-width="0.5"/>
            <circle cx="143" cy="148" r="6" fill="#030a03" stroke="#003a00" stroke-width="1"/>
          </g>

          <!-- Legs -->
          <rect x="44" y="180" width="28" height="36" rx="6" fill="#030a03" stroke="#003a00" stroke-width="1"/>
          <rect x="88" y="180" width="28" height="36" rx="6" fill="#030a03" stroke="#003a00" stroke-width="1"/>
          <!-- Feet -->
          <rect x="40" y="208" width="36" height="10" rx="5" fill="#030a03" stroke="#00ff41" stroke-width="1"/>
          <rect x="84" y="208" width="36" height="10" rx="5" fill="#030a03" stroke="#00ff41" stroke-width="1"/>

          <!-- Ground glow -->
          <ellipse cx="80" cy="218" rx="44" ry="4" fill="#00ff41" opacity="0.08"/>
        </svg>
      </div>

      <div style="font-family:'Orbitron',monospace;font-size:13px;color:#00ff41;letter-spacing:4px;margin-bottom:8px">INITIALIZING...</div>
      <div style="font-size:11px;color:#005510;letter-spacing:2px" id="pctText">0%</div>
      <div style="width:220px;height:4px;background:#001500;border-radius:2px;margin:10px auto 0;overflow:hidden">
        <div id="progBar" style="height:100%;width:0%;background:#00ff41;border-radius:2px;transition:width 0.05s linear;box-shadow:0 0 8px #00ff41"></div>
      </div>
    </div>

    <!-- MAIN SCREEN -->
    <div id="mainScreen">
      <div class="hero">
        <div class="terminal-tag">// system.online &gt; portfolio.exe</div>

        <!-- Inline robot (small) -->
        <div style="display:flex;justify-content:center;margin-bottom:20px">
          <svg width="70" height="96" viewBox="0 0 160 220" fill="none" style="animation:robotFloat 3s ease-in-out infinite">
            <line x1="80" y1="10" x2="80" y2="30" stroke="#00ff41" stroke-width="2"/>
            <circle cx="80" cy="7" r="4" fill="#00ff41" style="animation:antennaPulse 1.5s ease-in-out infinite"/>
            <line x1="44" y1="50" x2="30" y2="42" stroke="#003a00" stroke-width="1.5"/>
            <circle cx="28" cy="41" r="3" fill="#003a00" style="animation:earPing 2s ease-in-out infinite"/>
            <line x1="116" y1="50" x2="130" y2="42" stroke="#003a00" stroke-width="1.5"/>
            <circle cx="132" cy="41" r="3" fill="#003a00" style="animation:earPing 2s ease-in-out infinite 0.5s"/>
            <rect x="40" y="28" width="80" height="64" rx="10" fill="#030a03" stroke="#00ff41" stroke-width="1.5"/>
            <rect x="46" y="34" width="68" height="52" rx="7" fill="transparent" stroke="#003a00" stroke-width="0.5"/>
            <g style="transform-origin:62px 58px;animation:eyeblink 4s ease-in-out infinite">
              <rect x="50" y="50" width="24" height="16" rx="4" fill="#00ff41" opacity="0.15"/>
              <rect x="59" y="55" width="6" height="6" rx="1" fill="#00ff41"/>
            </g>
            <g style="transform-origin:98px 58px;animation:eyeblink 4s ease-in-out infinite 0.1s">
              <rect x="86" y="50" width="24" height="16" rx="4" fill="#00ff41" opacity="0.15"/>
              <rect x="95" y="55" width="6" height="6" rx="1" fill="#00ff41"/>
            </g>
            <rect x="52" y="76" width="56" height="8" rx="4" fill="#030a03" stroke="#003a00" stroke-width="0.5"/>
            <rect x="55" y="78" width="8" height="4" rx="2" fill="#00ff41" opacity="0.9"/>
            <rect x="66" y="78" width="8" height="4" rx="2" fill="#00ff41" opacity="0.6"/>
            <rect x="77" y="78" width="8" height="4" rx="2" fill="#00ff41" opacity="0.9"/>
            <rect x="88" y="78" width="8" height="4" rx="2" fill="#00ff41" opacity="0.4"/>
            <rect x="28" y="104" width="104" height="76" rx="8" fill="#030a03" stroke="#00ff41" stroke-width="1.5"/>
            <circle cx="80" cy="142" r="12" fill="rgba(0,255,65,0.1)" stroke="#00ff41" stroke-width="1"/>
            <circle cx="80" cy="142" r="5" fill="#00ff41" opacity="0.8" style="animation:antennaPulse 2s ease-in-out infinite"/>
            <g style="transform-origin:28px 120px;animation:armSwing 3s ease-in-out infinite">
              <rect x="6" y="104" width="22" height="52" rx="8" fill="#030a03" stroke="#003a00" stroke-width="1"/>
            </g>
            <g style="transform-origin:132px 120px;animation:armSwing 3s ease-in-out infinite reverse">
              <rect x="132" y="104" width="22" height="52" rx="8" fill="#030a03" stroke="#003a00" stroke-width="1"/>
            </g>
            <rect x="44" y="180" width="28" height="36" rx="6" fill="#030a03" stroke="#003a00" stroke-width="1"/>
            <rect x="88" y="180" width="28" height="36" rx="6" fill="#030a03" stroke="#003a00" stroke-width="1"/>
            <rect x="40" y="208" width="36" height="10" rx="5" fill="#030a03" stroke="#00ff41" stroke-width="1"/>
            <rect x="84" y="208" width="36" height="10" rx="5" fill="#030a03" stroke="#00ff41" stroke-width="1"/>
            <ellipse cx="80" cy="218" rx="44" ry="4" fill="#00ff41" opacity="0.08"/>
          </svg>
        </div>

        <div class="name-wrap"><div class="name">ABDUL BASIT</div></div>
        <div class="subtitle">Full Stack Developer &nbsp;·&nbsp; Fresher</div>
        <div class="tw-wrap"><span class="tw" id="tw"></span><span class="cursor"></span></div>
        <div class="status-pill"><div class="pulse"></div>SYSTEM ONLINE &nbsp;·&nbsp; OPEN TO HIRE</div>
        <div class="cta-row">
          <a class="btn-g" href="https://basit-dev-six.vercel.app/" target="_blank">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><polygon points="12 2 22 22 2 22"/></svg>
            PORTFOLIO
          </a>
          <a class="btn-o" href="mailto:basitaly261@gmail.com">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
            HIRE ME
          </a>
        </div>
      </div>

      <div class="sep"></div>

      <!-- ABOUT -->
      <div class="section">
        <div class="sec-label">// module_01.about</div>
        <div class="sec-title">&gt; WHO AM I</div>
        <div class="about-grid">
          <div class="acard">
            <div class="a-ico">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#00ff41" stroke-width="2"><rect x="2" y="3" width="20" height="14" rx="2"/><line x1="8" y1="21" x2="16" y2="21"/><line x1="12" y1="17" x2="12" y2="21"/></svg>
            </div>
            <h3>Education</h3>
            <p>Fresher dev dedicated to high-quality web applications</p>
          </div>
          <div class="acard">
            <div class="a-ico">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#00ff41" stroke-width="2"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>
            </div>
            <h3>Focus</h3>
            <p>MERN Stack and Next.js 14 for modern performant apps</p>
          </div>
          <div class="acard">
            <div class="a-ico">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#00ff41" stroke-width="2"><ellipse cx="12" cy="5" rx="9" ry="3"/><path d="M21 12c0 1.66-4 3-9 3s-9-1.34-9-3"/><path d="M3 5v14c0 1.66 4 3 9 3s9-1.34 9-3V5"/></svg>
            </div>
            <h3>Backend</h3>
            <p>Secure APIs and efficient database schemas</p>
          </div>
          <div class="acard">
            <div class="a-ico">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#00ff41" stroke-width="2"><path d="M12 20h9"/><path d="M16.5 3.5a2.121 2.121 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"/></svg>
            </div>
            <h3>UX / UI</h3>
            <p>Smooth, responsive and interactive experiences</p>
          </div>
        </div>
      </div>

      <div class="sep"></div>

      <!-- TECH -->
      <div class="section">
        <div class="sec-label">// module_02.arsenal</div>
        <div class="sec-title">&gt; TECH STACK</div>
        <div class="tech-grid" id="tg"></div>
      </div>

      <div class="sep"></div>

      <!-- TERMINAL -->
      <div class="section">
        <div class="sec-label">// module_03.terminal</div>
        <div class="sec-title">&gt; QUICK INFO</div>
        <div class="terminal">
          <div class="t-bar">
            <div class="t-dot" style="background:#ff5f56"></div>
            <div class="t-dot" style="background:#ffbd2e"></div>
            <div class="t-dot" style="background:#27c93f"></div>
          </div>
          <div><span class="prompt">visitor@portfolio:~$ </span><span class="cmd">whoami</span></div>
          <div><span class="out">Abdul Basit &mdash; MERN Stack &amp; Next.js Developer</span></div>
          <div>&nbsp;</div>
          <div><span class="prompt">visitor@portfolio:~$ </span><span class="cmd">cat skills.txt</span></div>
          <div><span class="out">React, Next.js, Node, Express, MongoDB, TS...</span></div>
          <div>&nbsp;</div>
          <div><span class="prompt">visitor@portfolio:~$ </span><span class="cmd">cat status.txt</span></div>
          <div><span class="out" style="color:#00ff41">AVAILABLE FOR HIRE &mdash; Open to opportunities</span></div>
          <div>&nbsp;</div>
          <div><span class="prompt">visitor@portfolio:~$ </span><span class="cursor" style="width:8px;height:14px;display:inline-block;background:#00ff41;animation:blink 0.7s step-end infinite"></span></div>
        </div>
      </div>

      <div class="sep"></div>

      <!-- CONNECT -->
      <div class="section">
        <div class="sec-label">// module_04.connect</div>
        <div class="sec-title">&gt; LET'S CONNECT</div>
        <div class="conn-grid">
          <a class="cbtn" href="https://www.linkedin.com/in/abdul-basit-aly/" target="_blank">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="#0077B5"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            LinkedIn
          </a>
          <a class="cbtn" href="https://github.com/basitaly101" target="_blank">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="#00ff41"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
            GitHub
          </a>
          <a class="cbtn" href="mailto:basitaly261@gmail.com">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#ff4444" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
            Email
          </a>
          <a class="cbtn" href="https://basit-dev-six.vercel.app/" target="_blank">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#00ff41" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg>
            Portfolio
          </a>
        </div>
      </div>

      <div class="quote">&gt; "Every great developer was once a beginner who refused to quit." _</div>

      <div class="footer-bar"></div>
    </div>
  </div>
</div>

<script>
const bootLines = [
  ['[  0.001]', ' KERNEL BOOT ... ', 'ok'],
  ['[  0.042]', ' LOADING MODULES ... ', 'ok'],
  ['[  0.118]', ' INITIALIZING DISPLAY DRIVER ... ', 'ok'],
  ['[  0.231]', ' CONNECTING TO NETWORK ... ', 'ok'],
  ['[  0.399]', ' LOADING PORTFOLIO DATA ... ', 'ok'],
  ['[  0.521]', ' WELCOME, VISITOR ... ', 'ok'],
];

let li = 0;
function showLine() {
  if (li >= bootLines.length) return;
  const el = document.getElementById('bl' + li);
  const [ts, msg, status] = bootLines[li];
  el.innerHTML = `<span style="color:#003a00">${ts}</span><span style="color:#005510">${msg}</span><span class="${status === 'ok' ? 'ok' : 'err'}">[${status.toUpperCase()}]</span>`;
  li++;
  if (li < bootLines.length) setTimeout(showLine, 220);
}
setTimeout(showLine, 300);

let prog = 0;
const bar = document.getElementById('progBar');
const pct = document.getElementById('pctText');
const timer = setInterval(() => {
  prog = Math.min(prog + (Math.random() * 3 + 1), 100);
  bar.style.width = prog + '%';
  pct.textContent = Math.round(prog) + '%';
  if (prog >= 100) {
    clearInterval(timer);
    setTimeout(() => {
      const boot = document.getElementById('bootScreen');
      const main = document.getElementById('mainScreen');
      boot.style.opacity = '1';
      boot.style.transition = 'opacity 0.6s';
      boot.style.opacity = '0';
      setTimeout(() => {
        boot.style.display = 'none';
        main.style.display = 'block';
        main.style.opacity = '0';
        main.style.transition = 'opacity 0.6s';
        requestAnimationFrame(() => { main.style.opacity = '1'; });
      }, 600);
    }, 400);
  }
}, 40);

const phrases = ['MERN Stack Developer', 'Next.js 14 Specialist', 'Full Stack Engineer', 'API Architect', 'UI/UX Builder'];
let pi = 0, ci = 0, del = false;
const tw = document.getElementById('tw');
function type() {
  const p = phrases[pi];
  if (!del) { tw.textContent = p.substring(0, ++ci); if (ci === p.length) { del = true; setTimeout(type, 1800); return; } }
  else { tw.textContent = p.substring(0, --ci); if (ci === 0) { del = false; pi = (pi + 1) % phrases.length; } }
  setTimeout(type, del ? 55 : 85);
}
setTimeout(type, 3500);

const techs = [
  {l:'Next.js',i:'▲'},{l:'React',i:'⚛'},{l:'TypeScript',i:'TS'},{l:'Node.js',i:'⬡'},
  {l:'Express',i:'〣'},{l:'MongoDB',i:'M'},{l:'Firebase',i:'F'},{l:'Tailwind',i:'~'},
  {l:'Redux',i:'⚡'},{l:'MySQL',i:'DB'},{l:'Git',i:'⑂'},{l:'Vercel',i:'▲'},
  {l:'Postman',i:'P'},{l:'Figma',i:'◈'},{l:'Bootstrap',i:'B'},{l:'GitHub',i:'G'},
];
const tg = document.getElementById('tg');
techs.forEach((t, i) => {
  const el = document.createElement('div');
  el.className = 'tchip';
  el.style.animationDelay = (i * 0.04) + 's';
  el.innerHTML = `<span class="ti" style="font-size:16px;line-height:1;font-family:'Share Tech Mono',monospace;color:#00ff41">${t.i}</span><span>${t.l}</span>`;
  tg.appendChild(el);
});
</script>
