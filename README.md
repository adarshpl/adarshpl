
<style>
  @keyframes pulse-ring {
    0% { transform: scale(0.8); opacity: 1; }
    100% { transform: scale(2); opacity: 0; }
  }
  @keyframes counter-up {
    from { opacity: 0; transform: translateY(12px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes slide-in-left {
    from { opacity: 0; transform: translateX(-24px); }
    to { opacity: 1; transform: translateX(0); }
  }
  @keyframes slide-in-right {
    from { opacity: 0; transform: translateX(24px); }
    to { opacity: 1; transform: translateX(0); }
  }
  @keyframes fade-up {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes bar-grow {
    from { height: 0; }
    to { height: var(--bar-h); }
  }
  @keyframes rotate-slow {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }
  @keyframes spark {
    0%, 100% { opacity: 0; transform: scale(0); }
    50% { opacity: 1; transform: scale(1); }
  }
  @keyframes shimmer {
    0% { left: -100%; }
    100% { left: 200%; }
  }
  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-6px); }
  }
  @keyframes ping {
    0% { transform: scale(1); opacity: 0.8; }
    80%, 100% { transform: scale(2.2); opacity: 0; }
  }

  .gh-card {
    background: var(--color-background-primary);
    border: 0.5px solid var(--color-border-tertiary);
    border-radius: var(--border-radius-lg);
    padding: 1.25rem;
    position: relative;
    overflow: hidden;
  }
  .gh-card::after {
    content: '';
    position: absolute;
    top: 0; left: -100%;
    width: 60%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.04), transparent);
    animation: shimmer 3s infinite;
  }
  .metric-num {
    font-size: 32px;
    font-weight: 500;
    color: var(--color-text-primary);
    animation: counter-up 0.6s ease both;
    line-height: 1;
  }
  .metric-label {
    font-size: 11px;
    color: var(--color-text-secondary);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-top: 4px;
  }
  .metric-date {
    font-size: 11px;
    color: var(--color-text-tertiary);
    margin-top: 2px;
  }
  .lang-pill {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 4px 10px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: 500;
    border: 0.5px solid var(--color-border-tertiary);
    background: var(--color-background-secondary);
    color: var(--color-text-secondary);
    animation: fade-up 0.5s ease both;
  }
  .lang-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }
  .tool-chip {
    width: 36px; height: 36px;
    border-radius: 8px;
    background: var(--color-background-secondary);
    border: 0.5px solid var(--color-border-tertiary);
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
    animation: float 3s ease-in-out infinite;
    transition: transform 0.2s, border-color 0.2s;
    cursor: default;
  }
  .tool-chip:hover {
    transform: translateY(-4px) scale(1.1);
    border-color: var(--color-border-primary);
  }
  .activity-bar {
    flex: 1;
    border-radius: 3px 3px 0 0;
    min-height: 4px;
    animation: bar-grow 0.8s ease both;
    transform-origin: bottom;
  }
  .streak-ring {
    position: relative;
    width: 80px; height: 80px;
    display: flex; align-items: center; justify-content: center;
  }
  .streak-ring svg {
    position: absolute;
    top: 0; left: 0;
    animation: rotate-slow 8s linear infinite;
  }
  .streak-inner {
    text-align: center;
    z-index: 1;
  }
  .social-btn {
    width: 32px; height: 32px;
    border-radius: 8px;
    border: 0.5px solid var(--color-border-tertiary);
    background: var(--color-background-secondary);
    display: flex; align-items: center; justify-content: center;
    font-size: 14px;
    cursor: pointer;
    transition: transform 0.15s, border-color 0.15s;
    text-decoration: none;
  }
  .social-btn:hover { transform: scale(1.12); border-color: var(--color-border-primary); }
  .status-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: #22c55e;
    position: relative;
    flex-shrink: 0;
  }
  .status-dot::after {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 100%;
    border-radius: 50%;
    background: #22c55e;
    animation: ping 1.5s ease infinite;
  }
  .section-label {
    font-size: 11px;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--color-text-secondary);
    margin-bottom: 12px;
  }
  .contrib-cell {
    width: 12px; height: 12px;
    border-radius: 2px;
    transition: transform 0.15s;
    cursor: default;
  }
  .contrib-cell:hover { transform: scale(1.4); }
  .info-row {
    display: flex;
    align-items: flex-start;
    gap: 8px;
    padding: 7px 0;
    border-bottom: 0.5px solid var(--color-border-tertiary);
    font-size: 13px;
    color: var(--color-text-secondary);
    animation: slide-in-left 0.5s ease both;
  }
  .info-row:last-child { border-bottom: none; }
  .info-icon { font-size: 13px; flex-shrink: 0; margin-top: 1px; }
</style>

<div style="padding: 1rem 0; max-width: 800px; margin: 0 auto;">

  <h2 class="sr-only">Adarsh PL — GitHub Profile Dashboard</h2>

  <!-- Header -->
  <div style="display: flex; align-items: center; gap: 16px; margin-bottom: 1.5rem; animation: slide-in-left 0.5s ease both;">
    <div style="position: relative; flex-shrink: 0;">
      <div style="width: 64px; height: 64px; border-radius: 50%; background: linear-gradient(135deg, #7F77DD, #1D9E75); display: flex; align-items: center; justify-content: center; font-size: 24px; font-weight: 500; color: #fff;">AP</div>
      <div style="position: absolute; bottom: 2px; right: 2px; display: flex; align-items: center; justify-content: center;">
        <div class="status-dot"></div>
      </div>
    </div>
    <div style="flex: 1;">
      <div style="font-size: 20px; font-weight: 500; color: var(--color-text-primary);">Adarsh pl</div>
      <div style="font-size: 13px; color: var(--color-text-secondary); margin-top: 2px;">Full Stack Developer · India</div>
      <div style="display: flex; gap: 6px; margin-top: 8px; flex-wrap: wrap;">
        <a class="social-btn" title="LinkedIn">💼</a>
        <a class="social-btn" title="Twitter">🐦</a>
        <a class="social-btn" title="Instagram">📸</a>
        <a class="social-btn" title="YouTube">📺</a>
        <a class="social-btn" title="Email">📧</a>
      </div>
    </div>
    <div style="text-align: right; flex-shrink: 0;">
      <div style="font-size: 24px; font-weight: 500; color: var(--color-text-primary);">131,277</div>
      <div style="font-size: 11px; color: var(--color-text-secondary); text-transform: uppercase; letter-spacing: 0.08em;">profile views</div>
      <div style="font-size: 20px; font-weight: 500; color: var(--color-text-primary); margin-top: 8px;">32</div>
      <div style="font-size: 11px; color: var(--color-text-secondary); text-transform: uppercase; letter-spacing: 0.08em;">followers</div>
    </div>
  </div>

  <!-- Stats row -->
  <div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 10px; margin-bottom: 1rem;">
    <div class="gh-card" style="text-align: center; animation: fade-up 0.5s 0.1s ease both;">
      <div class="metric-num" style="color: #7F77DD;">187</div>
      <div class="metric-label">Total contributions</div>
      <div class="metric-date">Jul 20, 2018 – Present</div>
    </div>
    <div class="gh-card" style="text-align: center; animation: fade-up 0.5s 0.2s ease both;">
      <div class="streak-ring" style="margin: 0 auto 4px;">
        <svg width="80" height="80" viewBox="0 0 80 80">
          <circle cx="40" cy="40" r="34" fill="none" stroke="var(--color-border-tertiary)" stroke-width="3"/>
          <circle cx="40" cy="40" r="34" fill="none" stroke="#7F77DD" stroke-width="3" stroke-dasharray="30 184" stroke-linecap="round" transform="rotate(-90 40 40)"/>
          <circle cx="40" cy="8" r="4" fill="#7F77DD" opacity="0.8"/>
        </svg>
        <div class="streak-inner">
          <div style="font-size: 22px; font-weight: 500; color: var(--color-text-primary);">0</div>
          <div style="font-size: 9px; color: var(--color-text-secondary);">streak</div>
        </div>
      </div>
      <div class="metric-label">Current streak</div>
      <div class="metric-date">Apr 10</div>
    </div>
    <div class="gh-card" style="text-align: center; animation: fade-up 0.5s 0.3s ease both;">
      <div class="metric-num" style="color: #1D9E75;">7</div>
      <div class="metric-label">Longest streak</div>
      <div class="metric-date">Feb 21 – Feb 27, 2021</div>
    </div>
  </div>

  <!-- Activity graph + About -->
  <div style="display: grid; grid-template-columns: 1fr 280px; gap: 10px; margin-bottom: 1rem;">
    <!-- Contribution graph -->
    <div class="gh-card" style="animation: slide-in-left 0.5s 0.15s ease both;">
      <div class="section-label">Contribution activity — past 24 weeks</div>
      <div id="contrib-grid" style="display: flex; flex-direction: column; gap: 3px;"></div>
    </div>

    <!-- About me -->
    <div class="gh-card" style="animation: slide-in-right 0.5s 0.15s ease both;">
      <div class="section-label">About</div>
      <div class="info-row" style="animation-delay:0.2s">
        <span class="info-icon">🏢</span>
        <span>Working @ <strong style="color: var(--color-text-primary);">Z Link Software</strong></span>
      </div>
      <div class="info-row" style="animation-delay:0.3s">
        <span class="info-icon">🌱</span>
        <span>Learning AI software creations</span>
      </div>
      <div class="info-row" style="animation-delay:0.4s">
        <span class="info-icon">🤝</span>
        <span>Open to collaborate on OSS projects</span>
      </div>
      <div class="info-row" style="animation-delay:0.5s">
        <span class="info-icon">💼</span>
        <span><a href="#" style="color: var(--color-text-info);">My Portfolio</a></span>
      </div>
      <div class="info-row" style="animation-delay:0.6s">
        <span class="info-icon">📧</span>
        <span style="font-size: 12px; word-break: break-all;">adarshpltvm@gmail.com</span>
      </div>
      <div class="info-row" style="animation-delay:0.7s">
        <span class="info-icon">⚡</span>
        <span>Interested in crypto trading</span>
      </div>
    </div>
  </div>

  <!-- Languages + Tools -->
  <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 1rem;">
    <!-- Languages -->
    <div class="gh-card" style="animation: slide-in-left 0.5s 0.25s ease both;">
      <div class="section-label">Top languages</div>
      <div style="display: flex; flex-direction: column; gap: 8px;" id="lang-bars"></div>
    </div>

    <!-- Tools -->
    <div class="gh-card" style="animation: slide-in-right 0.5s 0.25s ease both;">
      <div class="section-label">Languages &amp; tools</div>
      <div style="display: flex; flex-wrap: wrap; gap: 8px;" id="tools-grid"></div>
    </div>
  </div>

  <!-- Activity bars -->
  <div class="gh-card" style="animation: fade-up 0.5s 0.35s ease both;">
    <div class="section-label">Weekly activity pattern</div>
    <div style="display: flex; align-items: flex-end; gap: 4px; height: 80px;" id="activity-bars"></div>
    <div style="display: flex; gap: 4px; margin-top: 4px;" id="activity-labels"></div>
  </div>

</div>

<script>
const $ = id => document.getElementById(id);

// Contribution grid
const grid = $('contrib-grid');
const weeks = 24;
const days = 7;
const levels = ['#161b22', '#0e4429', '#006d32', '#26a641', '#39d353'];
let html = '<div style="display:flex;gap:3px;">';
const dayLabels = ['','Mon','','Wed','','Fri',''];
dayLabels.forEach((d, i) => {
  html += `<div style="font-size:9px;color:var(--color-text-tertiary);line-height:12px;width:12px;text-align:right;margin-bottom:2px;">${d}</div>`;
});
html += '</div><div style="display:flex;gap:3px;">';
for (let w = 0; w < weeks; w++) {
  html += '<div style="display:flex;flex-direction:column;gap:3px;">';
  for (let d = 0; d < days; d++) {
    const r = Math.random();
    const lvl = r < 0.55 ? 0 : r < 0.72 ? 1 : r < 0.84 ? 2 : r < 0.93 ? 3 : 4;
    const count = lvl === 0 ? 0 : Math.floor(Math.random() * 8 + 1);
    html += `<div class="contrib-cell" style="background:${levels[lvl]};" title="${count} contributions"></div>`;
  }
  html += '</div>';
}
html += '</div><div style="display:flex;gap:6px;margin-top:8px;align-items:center;">';
html += '<span style="font-size:10px;color:var(--color-text-tertiary);">Less</span>';
levels.forEach(c => {
  html += `<div style="width:11px;height:11px;border-radius:2px;background:${c};border:0.5px solid rgba(255,255,255,0.05)"></div>`;
});
html += '<span style="font-size:10px;color:var(--color-text-tertiary);">More</span></div>';
grid.innerHTML = html;

// Language bars
const langs = [
  { name: 'JavaScript', pct: 42, color: '#EF9F27' },
  { name: 'Python', pct: 24, color: '#7F77DD' },
  { name: 'HTML/CSS', pct: 18, color: '#D85A30' },
  { name: 'Java', pct: 11, color: '#D4537E' },
  { name: 'Other', pct: 5, color: '#888780' },
];
$('lang-bars').innerHTML = langs.map((l, i) => `
  <div style="animation: fade-up 0.4s ${0.1 * i + 0.3}s ease both; opacity: 0; animation-fill-mode: both;">
    <div style="display:flex;justify-content:space-between;margin-bottom:4px;">
      <div style="display:flex;align-items:center;gap:6px;">
        <div style="width:8px;height:8px;border-radius:50%;background:${l.color};flex-shrink:0;"></div>
        <span style="font-size:12px;color:var(--color-text-secondary);">${l.name}</span>
      </div>
      <span style="font-size:12px;font-weight:500;color:var(--color-text-primary);">${l.pct}%</span>
    </div>
    <div style="height:5px;background:var(--color-background-secondary);border-radius:3px;overflow:hidden;">
      <div style="height:100%;width:0%;background:${l.color};border-radius:3px;transition:width 1s ${0.1 * i + 0.6}s ease;" data-w="${l.pct}%"></div>
    </div>
  </div>
`).join('');

setTimeout(() => {
  document.querySelectorAll('[data-w]').forEach(el => {
    el.style.width = el.dataset.w;
  });
}, 100);

// Tools
const tools = [
  { icon: '☕', name: 'Java' },
  { icon: '⚛', name: 'React' },
  { icon: '🌿', name: 'Spring' },
  { icon: '🟨', name: 'JS' },
  { icon: '🎨', name: 'HTML5' },
  { icon: '💎', name: 'CSS3' },
  { icon: '🅱', name: 'Bootstrap' },
  { icon: '🐍', name: 'Python' },
  { icon: '🟢', name: 'Node.js' },
  { icon: '🗄', name: 'MySQL' },
  { icon: '🔥', name: 'Firebase' },
  { icon: '🔴', name: 'Redux' },
];
$('tools-grid').innerHTML = tools.map((t, i) => `
  <div class="tool-chip" title="${t.name}" style="animation-delay: ${i * 0.07}s;">${t.icon}</div>
`).join('');

// Activity bars
const actDays = ['Mon','Tue','Wed','Thu','Fri','Sat','Sun'];
const actVals = [3, 7, 5, 9, 6, 2, 1];
const maxV = Math.max(...actVals);
$('activity-bars').innerHTML = actVals.map((v, i) => {
  const hPct = Math.round((v / maxV) * 72);
  const colors = ['#7F77DD','#1D9E75','#7F77DD','#D4537E','#1D9E75','#888780','#888780'];
  return `<div style="flex:1;display:flex;flex-direction:column;align-items:center;justify-content:flex-end;height:80px;">
    <div style="width:100%;height:${hPct}px;background:${colors[i]};border-radius:3px 3px 0 0;animation:bar-grow 0.7s ${i*0.08+0.3}s ease both;transform-origin:bottom;"></div>
  </div>`;
}).join('');
$('activity-labels').innerHTML = actDays.map(d =>
  `<div style="flex:1;text-align:center;font-size:10px;color:var(--color-text-tertiary);">${d}</div>`
).join('');
</script>
