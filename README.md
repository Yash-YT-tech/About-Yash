<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>GitHub Profile Dashboard — Stunning</title>

  <!-- Google fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">

  <!-- Fontawesome for icons -->
  <script src="https://kit.fontawesome.com/7c6ad5f0a4.js" crossorigin="anonymous"></script>

  <style>
  :root{
    --bg1: #0f1724;
    --bg2: #081024;
    --glass: rgba(255,255,255,0.04);
    --accent: linear-gradient(90deg,#ff6a88,#845ec2);
    --muted: rgba(255,255,255,0.6);
    --glass-border: rgba(255,255,255,0.06);
    --card-shadow: 0 6px 30px rgba(2,6,23,0.6);
    --glass-strong: rgba(255,255,255,0.03);
    --success: #22c55e;
    --danger: #ef4444;
  }

  *{box-sizing:border-box}
  html,body{height:100%}
  body{
    margin:0;
    font-family: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    background: radial-gradient(1200px 600px at 10% 10%, rgba(132,94,194,0.12), transparent),
                radial-gradient(700px 400px at 90% 90%, rgba(255,106,136,0.08), transparent),
                linear-gradient(180deg,var(--bg1), var(--bg2));
    color:#e6eef8;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
    padding:32px;
  }

  /* Container */
  .wrap{
    max-width:1200px;
    margin:0 auto;
    display:grid;
    grid-template-columns: 360px 1fr;
    gap:28px;
    align-items:start;
  }

  /* left column */
  .card{
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border-radius:18px;
    padding:20px;
    border:1px solid var(--glass-border);
    box-shadow:var(--card-shadow);
    backdrop-filter: blur(8px) saturate(120%);
  }

  .profile{
    text-align:center;
    padding:8px;
  }
  .avatar{
    width:120px;
    height:120px;
    margin:0 auto 12px;
    border-radius:999px;
    overflow:hidden;
    border:3px solid rgba(255,255,255,0.06);
    box-shadow: 0 6px 20px rgba(0,0,0,0.6);
    transition: transform .4s ease;
  }
  .avatar img{width:100%;height:100%;object-fit:cover;display:block}
  .avatar:hover{transform:scale(1.03) rotate(-2deg)}

  h1{font-size:20px;margin:0 0 6px;font-weight:800;letter-spacing:0.2px}
  h2{font-size:12px;margin:0;color:var(--muted);font-weight:600}

  .badge-row{display:flex;gap:8px;justify-content:center;margin-top:12px;flex-wrap:wrap}
  .pill{font-size:12px;padding:6px 10px;border-radius:999px;background:linear-gradient(90deg,rgba(255,255,255,0.03),rgba(255,255,255,0.02));border:1px solid var(--glass-border);color:var(--muted)}

  .left-stats{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-top:18px}
  .stat{
    background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border-radius:12px;padding:12px;border:1px solid var(--glass-border);
    text-align:center;
  }
  .stat .num{font-weight:800;font-size:18px}
  .stat .label{font-size:11px;color:var(--muted);margin-top:6px}

  .stack{
    margin-top:16px;
  }
  .stack .icons{display:flex;flex-wrap:wrap;gap:8px}
  .tech{
    background:linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    padding:8px;border-radius:10px;border:1px solid var(--glass-border);
    font-size:12px;display:inline-flex;align-items:center;gap:8px;
  }

  /* right column */
  .header-banner{
    border-radius:14px;
    overflow:hidden;
    position:relative;
    height:150px;
    background: linear-gradient(90deg,#061226 0%, rgba(4,7,22,0.6) 100%);
    border:1px solid var(--glass-border);
    display:flex;align-items:center;padding:18px;
  }
  .banner-left{
    display:flex;flex-direction:column;gap:6px;
  }
  .banner-title{font-weight:800;font-size:20px}
  .banner-sub{font-size:13px;color:var(--muted)}
  .banner-cta{margin-top:8px;display:flex;gap:8px}

  .glass-row{display:flex;gap:18px;margin-top:-36px}
  .glass-lg{flex:1;padding:18px;border-radius:14px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border:1px solid var(--glass-border);box-shadow:var(--card-shadow)}
  .glass-sm{width:260px;padding:18px;border-radius:14px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border:1px solid var(--glass-border);box-shadow:var(--card-shadow)}

  /* Stats panels */
  .stats-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:18px}
  .stat-card{
    padding:14px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.015), rgba(255,255,255,0.01));
    border:1px solid var(--glass-border);
  }
  .stat-card h3{margin:0;font-size:13px}
  .stat-card .big{font-weight:800;font-size:20px;margin-top:8px}

  /* progress bars */
  .progress-wrap{margin-top:12px}
  .progress-item{margin-bottom:12px}
  .progress-label{display:flex;justify-content:space-between;font-size:12px;margin-bottom:6px;color:var(--muted)}
  .progress{
    height:12px;background:linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border-radius:999px;border:1px solid var(--glass-border);overflow:hidden;position:relative;
  }
  .progress > span{
    display:block;height:100%;width:0%;border-radius:999px;
    background: linear-gradient(90deg,#ff6a88,#845ec2);
    animation: progress-anim 1.4s cubic-bezier(.2,.9,.2,1) forwards;
    box-shadow:0 6px 18px rgba(132,94,194,0.18), inset 0 -6px 16px rgba(0,0,0,0.18);
  }
  @keyframes progress-anim{
    from{width:0}
    to{width:var(--w)}
  }

  /* circular charts */
  .radial-wrap{display:flex;gap:12px;align-items:center}
  .radial{
    width:110px;height:110px;border-radius:999px;background:conic-gradient(#00d3ff 0% 0%, rgba(255,255,255,0.03) 0% 100%);
    display:flex;align-items:center;justify-content:center;position:relative;
    box-shadow:0 6px 20px rgba(2,6,23,0.6);
  }
  .radial .val{font-weight:800;font-size:18px}
  .radial small{display:block;font-size:11px;color:var(--muted)}

  /* languages bars */
  .lang-list{margin-top:12px;display:flex;flex-direction:column;gap:10px}
  .lang-row{display:flex;align-items:center;gap:12px}
  .lang-dot{width:12px;height:12px;border-radius:3px;background:#fff;flex:0 0 12px}
  .lang-name{min-width:90px;font-size:13px}
  .bar{flex:1;height:10px;background:rgba(255,255,255,0.03);border-radius:999px;overflow:hidden;border:1px solid var(--glass-border)}
  .bar > i{height:100%;display:block;width:10%;background:linear-gradient(90deg,#ffd36b,#ff6a88);border-radius:999px;box-shadow:0 6px 18px rgba(255,106,136,0.12)}
  .lang-percent{min-width:40px;text-align:right;font-size:12px;color:var(--muted)}

  /* footer */
  .muted{color:var(--muted);font-size:13px}

  /* Theme toggle */
  .theme-toggle{margin-left:auto;border-radius:999px;padding:6px 10px;border:1px solid var(--glass-border);background:linear-gradient(90deg,rgba(255,255,255,0.02),rgba(255,255,255,0.01));display:inline-flex;gap:8px;align-items:center;cursor:pointer}
  .tiny{font-size:11px;color:var(--muted)}

  /* responsiveness */
  @media (max-width:980px){
    .wrap{grid-template-columns:1fr; padding:16px}
    .glass-row{flex-direction:column}
    .stats-grid{grid-template-columns:repeat(1,1fr)}
    .glass-sm{width:100%}
  }

  /* micro animations */
  .shine {
    position: absolute;
    top: -40%;
    left: -40%;
    width: 220%;
    height: 220%;
    background: linear-gradient(120deg, rgba(255,255,255,0.03), rgba(255,255,255,0.06), rgba(255,255,255,0.03));
    transform: rotate(25deg) translateX(-100%);
    pointer-events:none;
    animation: shimmer 6s linear infinite;
    opacity:0.6;
    mix-blend-mode:overlay;
  }
  @keyframes shimmer {
    0%{transform:rotate(25deg) translateX(-100%)}
    100%{transform:rotate(25deg) translateX(100%)}
  }

  /* tiny badges */
  .badge-small{
    display:inline-flex;align-items:center;gap:8px;padding:6px 8px;border-radius:8px;font-size:12px;border:1px solid var(--glass-border);
    background:linear-gradient(90deg, rgba(255,255,255,0.01), rgba(255,255,255,0.02));
  }

  /* cool border glow on hover */
  .hover-glow:hover{box-shadow:0 10px 40px rgba(132,94,194,0.18);transform:translateY(-4px);transition:all .35s ease}
  </style>
</head>
<body>

  <div class="wrap">
    <!-- LEFT COLUMN -->
    <aside class="card">
      <div class="profile">
        <div class="avatar">
          <img id="avatar" src="https://avatars.githubusercontent.com/u/583231?v=4" alt="avatar">
        </div>
        <h1 id="displayName">Your Name</h1>
        <h2 id="headline">Web Developer • AI Enthusiast</h2>

        <div class="badge-row">
          <div class="pill">⭐ GitHub: <span id="githubName">YOUR_USERNAME</span></div>
          <div class="pill">🚀 Dream: Google</div>
        </div>

        <div style="margin-top:12px">
          <div class="badge-small"><i class="fa-brands fa-github"></i> <small id="repoCount">0 Repos</small></div>
        </div>
      </div>

      <div class="left-stats" style="margin-top:18px">
        <div class="stat hover-glow">
          <div class="num" id="stargazers">0</div>
          <div class="label">Total Stars</div>
        </div>
        <div class="stat hover-glow">
          <div class="num" id="commits">—</div>
          <div class="label">Last Year Commits</div>
        </div>
        <div class="stat hover-glow">
          <div class="num" id="prs">0</div>
          <div class="label">PRs</div>
        </div>
        <div class="stat hover-glow">
          <div class="num" id="issues">0</div>
          <div class="label">Issues</div>
        </div>
      </div>

      <div class="stack">
        <h3 style="font-size:13px;margin:12px 0 8px">🧰 Tech Stack</h3>
        <div class="icons">
          <!-- skillicons.dev images -->
          <img src="https://skillicons.dev/icons?i=python,js,react,html,css,nodejs,git,github" style="height:36px" alt="stack">
        </div>
        <div style="margin-top:12px" class="muted">Top tools I use: VSCode • GitHub • Figma • Postman</div>
      </div>

      <div style="margin-top:18px">
        <h3 style="font-size:13px;margin:0 0 8px">📬 Contact</h3>
        <div class="muted">Email: <span id="email">yourmail@example.com</span></div>
        <div class="muted" style="margin-top:6px">Location: Pune, India</div>
      </div>
    </aside>

    <!-- RIGHT COLUMN -->
    <main>
      <div class="header-banner card" id="banner">
        <div class="shine"></div>
        <div class="banner-left">
          <div style="display:flex;align-items:center;gap:12px">
            <div style="width:72px;height:72px;border-radius:12px;overflow:hidden;border:1px solid rgba(255,255,255,0.04);display:flex;align-items:center;justify-content:center;background:linear-gradient(90deg,#0b1320,#132032)">
              <i class="fa-solid fa-terminal" style="font-size:28px;color:#fff"></i>
            </div>
            <div>
              <div class="banner-title" id="bannerTitle">Hi, I'm Yash Tathe</div>
              <div class="banner-sub" id="bannerSub">A Web Developer in making • AI learner • Open Source</div>
            </div>
            <div style="margin-left:auto;display:flex;align-items:center;gap:8px">
              <div class="theme-toggle" id="themeToggle" title="Toggle theme">
                <i class="fa-solid fa-sun"></i>
                <span class="tiny">Theme</span>
              </div>
            </div>
          </div>

          <div class="banner-cta">
            <a id="viewProfile" class="pill" href="#" target="_blank"><i class="fa-brands fa-github"></i> View on GitHub</a>
            <a class="pill" href="#" target="_blank"><i class="fa-solid fa-file-lines"></i> Resume</a>
            <a class="pill" href="#" target="_blank"><i class="fa-solid fa-envelope"></i> Contact</a>
          </div>
        </div>
      </div>

      <div class="glass-row">
        <div class="glass-lg card">
          <h3 style="margin:0 0 8px">📊 GitHub Overview</h3>
          <p class="muted" style="margin:0 0 14px">Real-time stats pulled from GitHub (public).</p>

          <div class="stats-grid" id="statsGrid">
            <div class="stat-card hover-glow">
              <h3>Contributions (Year)</h3>
              <div class="big" id="contribs">—</div>
            </div>
            <div class="stat-card hover-glow">
              <h3>Top Language</h3>
              <div class="big" id="topLang">—</div>
            </div>
            <div class="stat-card hover-glow">
              <h3>Total Repos</h3>
              <div class="big" id="totalRepos">—</div>
            </div>
          </div>

          <div style="margin-top:16px;display:flex;gap:16px;align-items:flex-start;flex-wrap:wrap">
            <div style="flex:1;min-width:240px">
              <h4 style="margin:6px 0">Languages</h4>
              <div class="lang-list" id="languages">
                <!-- JS fills languages -->
              </div>
            </div>

            <div style="width:220px">
              <h4 style="margin:6px 0">Skills Progress</h4>
              <div class="progress-wrap" id="skills">
                <!-- JS fills progress -->
              </div>
            </div>
          </div>

          <div style="margin-top:16px">
            <h4 style="margin:6px 0">Pinned Projects</h4>
            <div id="pinned" style="display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:12px;margin-top:10px">
              <!-- JS -> pinned cards -->
            </div>
          </div>
        </div>

        <div class="glass-sm card">
          <h3 style="margin:0 0 12px">Activity & Badges</h3>

          <div style="margin-top:6px">
            <div style="display:flex;gap:8px;flex-wrap:wrap">
              <img src="https://github-readme-stats.vercel.app/api/pin/?username=YOUR_USERNAME&repo=awesome-project&theme=tokyonight" style="width:100%;border-radius:8px" alt="">
            </div>
          </div>

          <div style="margin-top:12px">
            <h4 style="margin:0 0 8px">Weekly Streak</h4>
            <div class="muted" id="streak">Longest: — • Current: —</div>
          </div>

          <div style="margin-top:12px">
            <h4 style="margin:0 0 8px">Latest Releases</h4>
            <div id="releases" class="muted">—</div>
          </div>

        </div>
      </div>

      <div style="margin-top:18px" class="card">
        <h3 style="margin:6px 0 12px">Interactive Language Wheel</h3>
        <div style="display:flex;gap:18px;align-items:center;flex-wrap:wrap">
          <div id="radials" class="radial-wrap">
            <!-- radial charts inserted here -->
          </div>

          <div style="flex:1;min-width:320px">
            <h4 style="margin:0 0 8px">Detailed Language Breakdown</h4>
            <div id="langGrid" style="display:grid;grid-template-columns:repeat(2,1fr);gap:12px">
              <!-- JS fills -->
            </div>
          </div>
        </div>
      </div>

      <footer style="margin-top:18px" class="card muted">
        Built with ❤️ — copy, customize and host on GitHub Pages. Replace <code>YOUR_USERNAME</code> in the code with your GitHub username.
      </footer>
    </main>
  </div>

  <script>
  /******************************************
   * CONFIG
   ******************************************/
  const GITHUB_USERNAME = "YOUR_USERNAME"; // <<--- replace with the username you want to fetch
  const FALLBACK_AVATAR = "https://avatars.githubusercontent.com/u/583231?v=4";

  /******************************************
   * Small utilities
   ******************************************/
  function el(q){return document.querySelector(q)}
  function elAll(q){return document.querySelectorAll(q)}
  function niceNumber(n){
    if (n===null || n===undefined) return '—'
    if (n >= 1000) return Math.round(n/100)/10 + 'k'
    return String(n)
  }

  /******************************************
   * Animate progress helper
   ******************************************/
  function createProgress(value){
    const wrapper = document.createElement('div')
    wrapper.className = 'progress-item'
    wrapper.innerHTML = `
      <div class="progress-label"><div></div><div class="tiny">${value}%</div></div>
      <div class="progress"><span style="--w:${value}%"></span></div>
    `
    // set label text
    wrapper.querySelector('.progress-label div').textContent = 'Skill'
    // allow CSS animation by forcing reflow
    requestAnimationFrame(()=>{ wrapper.querySelector('span').style.width = value + '%' })
    return wrapper
  }

  /******************************************
   * Fetch GitHub user & stats (public)
   ******************************************/
  async function fetchGitHub(){
    try{
      const userRes = await fetch(`https://api.github.com/users/${GITHUB_USERNAME}`)
      if (!userRes.ok) throw new Error('GitHub user not found')
      const user = await userRes.json()
      // set avatar, name, bio
      el('#avatar').src = user.avatar_url || FALLBACK_AVATAR
      el('#displayName').textContent = user.name || user.login
      el('#headline').textContent = user.bio || 'Developer • Learner • Builder'
      el('#githubName').textContent = user.login
      el('#viewProfile').href = user.html_url
      el('#totalRepos').textContent = user.public_repos
      el('#repoCount').textContent = user.public_repos + ' Repos'

      // fetch repos to compute language breakdown and stars
      let page = 1, repos = []
      while(true){
        const r = await fetch(`https://api.github.com/users/${GITHUB_USERNAME}/repos?per_page=100&page=${page}`)
        const data = await r.json()
        if (!Array.isArray(data)) break
        repos = repos.concat(data)
        if (data.length < 100) break
        page++
      }

      // stats
      const totalStars = repos.reduce((s,r)=> s + (r.stargazers_count||0), 0)
      el('#stargazers').textContent = totalStars
      el('#prs').textContent = repos.filter(r => r.open_issues_count > 0).length

      // top languages
      const langMap = {}
      for (const repo of repos){
        if (!repo.language) continue
        langMap[repo.language] = (langMap[repo.language] || 0) + 1
      }
      const langEntries = Object.entries(langMap).sort((a,b)=> b[1]-a[1])
      const topLang = langEntries.length? langEntries[0][0] : '—'
      el('#topLang').textContent = topLang

      // prepare languages percent (by repo count)
      const total = Object.values(langMap).reduce((a,b)=>a+b,0)
      const langs = langEntries.map(([k,v]) => ({name:k,count:v,percent:Math.round(v/total*100)}))

      // fill languages list
      const languagesDiv = el('#languages')
      languagesDiv.innerHTML = ''
      if (langs.length === 0){
        languagesDiv.innerHTML = '<div class="muted">No languages detected (no public repos with languages)</div>'
      } else {
        langs.forEach(l=>{
          const row = document.createElement('div')
          row.className = 'lang-row'
          row.innerHTML = `
            <div class="lang-dot" style="background:linear-gradient(90deg,#ffd36b,#ff6a88)"></div>
            <div class="lang-name">${l.name}</div>
            <div class="bar"><i style="width:${l.percent}%"></i></div>
            <div class="lang-percent">${l.percent}%</div>
          `
          languagesDiv.appendChild(row)
        })
      }

      // create radials
      const radials = el('#radials')
      radials.innerHTML = ''
      langs.slice(0,3).forEach(l=>{
        const d = document.createElement('div')
        d.className = 'radial'
        d.style.background = `conic-gradient(#ffd36b 0% ${l.percent}%, rgba(255,255,255,0.03) ${l.percent}% 100%)`
        d.innerHTML = `<div><div class="val">${l.percent}%</div><small>${l.name}</small></div>`
        radials.appendChild(d)
      })

      // pinned repos (top 4 by stargazers)
      const pinned = el('#pinned')
      pinned.innerHTML = ''
      const topRepos = repos.slice().sort((a,b)=> (b.stargazers_count||0) - (a.stargazers_count||0)).slice(0,6)
      if (topRepos.length === 0) pinned.innerHTML = '<div class="muted">No public repos yet</div>'
      topRepos.forEach(r=>{
        const card = document.createElement('div')
        card.className = 'stat-card hover-glow'
        card.innerHTML = `
          <div style="display:flex;align-items:center;justify-content:space-between;gap:12px">
            <div style="flex:1">
              <div style="font-weight:700">${r.name}</div>
              <div class="muted" style="margin-top:6px;font-size:13px">${r.description ? r.description.substring(0,80) : 'No description'}</div>
            </div>
            <div style="text-align:right;min-width:70px">
              <div style="font-weight:800">${r.stargazers_count || 0} ★</div>
              <div class="muted" style="font-size:12px;margin-top:6px">${r.language || '—'}</div>
            </div>
          </div>
        `
        pinned.appendChild(card)
      })

      // contributions via /users/:username/events (approx)
      // GitHub does not expose yearly contribution total via REST easily; fetch from the public GitHub contributions page as fallback
      try {
        const graphRes = await fetch(`https://github-contributions-api.now.sh/v1/${GITHUB_USERNAME}`)
        const graphJson = await graphRes.json()
        if (graphJson && graphJson['contributions']) {
          el('#contribs').textContent = graphJson['contributions'].total
        } else {
          el('#contribs').textContent = '—'
        }
      } catch(e){
        el('#contribs').textContent = '—'
      }

      // simple streak (placeholder)
      el('#streak').textContent = 'Longest: — • Current: —'

      // skills progress (hard-coded example, could be dynamic)
      const skills = [
        {name:'HTML & CSS', val:88},
        {name:'JavaScript', val:76},
        {name:'React', val:68},
        {name:'Node.js', val:60},
        {name:'Python', val:72},
        {name:'Data Science', val:40}
      ]
      const skillsWrap = el('#skills')
      skillsWrap.innerHTML = ''
      skills.forEach(s=>{
        const item = document.createElement('div')
        item.className = 'progress-item'
        item.innerHTML = `
          <div class="progress-label"><strong>${s.name}</strong><div class="tiny">${s.val}%</div></div>
          <div class="progress"><span style="--w:${s.val}%"></span></div>
        `
        skillsWrap.appendChild(item)
        // animate width after append
        requestAnimationFrame(()=>{
          item.querySelector('span').style.width = s.val + '%'
        })
      })

      // fill some other fields
      el('#commits').textContent = '—' // optional: could use GraphQL or other APIs
      el('#issues').textContent = repos.reduce((a,b)=> a + (b.open_issues_count||0),0)
      el('#prs').textContent = '—' // needs extra endpoints
      el('#releases').textContent = topRepos.slice(0,1).map(r=> r.name + (r.pushed_at ? ` • updated ${new Date(r.pushed_at).toLocaleDateString()}` : '')).join(', ') || '—'

    } catch(err){
      console.error(err)
      alert('Failed to fetch GitHub data: ' + err.message)
    }
  }

  /******************************************
   * Page interactions
   ******************************************/
  document.getElementById('themeToggle').addEventListener('click', ()=>{
    document.documentElement.classList.toggle('alt-theme')
    // simple theme swap: flip background and accent
    if (document.documentElement.classList.contains('alt-theme')){
      document.body.style.background = 'linear-gradient(180deg,#fff,#f3f6fb)'
      document.body.style.color = '#0b1330'
      // invert cards a bit
      document.querySelectorAll('.card').forEach(c=>{
        c.style.background = 'linear-gradient(180deg, rgba(8,12,28,0.03), rgba(8,12,28,0.01))'
      })
    } else {
      document.body.style.background = ''
      document.body.style.color = ''
      document.querySelectorAll('.card').forEach(c=>{
        c.style.background = ''
      })
    }
  })

  // small initial demo values and animate
  document.addEventListener('DOMContentLoaded', ()=>{
    // customize header name
    el('#bannerTitle').textContent = "Hi, I'm Yash Tathe" // you can change this or set dynamically
    el('#bannerSub').textContent = "A Web Developer in making • Learning AI & Open Source"
    // default avatar placeholder until fetch
    el('#avatar').src = FALLBACK_AVATAR
    // run fetch
    if (GITHUB_USERNAME && GITHUB_USERNAME !== 'YOUR_USERNAME') {
      fetchGitHub()
    } else {
      // if not replaced, show demo placeholders and demo animated progress
      el('#displayName').textContent = 'Demo User'
      el('#githubName').textContent = 'YOUR_USERNAME (replace me)'
      const languages = [
        {name:'JavaScript',percent:60},
        {name:'C++',percent:32},
        {name:'Python',percent:45},
        {name:'HTML',percent:78},
        {name:'CSS',percent:70}
      ]
      const languagesDiv = el('#languages')
      languagesDiv.innerHTML = ''
      languages.forEach(l=>{
        const row = document.createElement('div')
        row.className = 'lang-row'
        row.innerHTML = `
          <div class="lang-dot" style="background:linear-gradient(90deg,#ffd36b,#ff6a88)"></div>
          <div class="lang-name">${l.name}</div>
          <div class="bar"><i style="width:${l.percent}%"></i></div>
          <div class="lang-percent">${l.percent}%</div>
        `
        languagesDiv.appendChild(row)
      })
      // demo radials
      const radials = el('#radials')
      radials.innerHTML = ''
      ['JavaScript','HTML','CSS'].forEach((n,i)=>{
        const p = [68,78,72][i]
        const d = document.createElement('div')
        d.className = 'radial'
        d.style.background = `conic-gradient(#ffd36b 0% ${p}%, rgba(255,255,255,0.03) ${p}% 100%)`
        d.innerHTML = `<div><div class="val">${p}%</div><small>${n}</small></div>`
        radials.appendChild(d)
      })
      // demo skills done earlier
      fetchGitHub().catch(()=>{})
    }
  })
  </script>
</body>
</html>
<!-- Banner -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=200&section=header&text=Hi%20👋,%20I'm%20Yash%20Tathe&fontSize=40&fontColor=fff&animation=fadeIn&fontAlignY=35" />
</p>

<!-- Typing SVG -->
<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=24&duration=4000&color=F70000&center=true&vCenter=true&lines=AI+Engineer+in+Making;Full+Stack+Developer;Generative+AI+Explorer;Open+Source+Contributor" />
</p>

---

### 🚀 About Me
💡 Passionate about **AI + Web Development + Automation**  
📚 Always learning **cutting-edge tech**  
⚡ Love building **interactive projects & AI agents**

---

### 🛠 Tech Stack
<p align="center">
  <img src="https://skillicons.dev/icons?i=python,html,css,js,react,nodejs,mongodb,mysql,java,cpp,git,github" />
</p>

---

### 📊 GitHub Stats
<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME&show_icons=true&theme=radical" height="170"/>
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=YOUR_USERNAME&theme=radical" height="170"/>
</p>

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_USERNAME&layout=compact&theme=radical" height="170"/>
</p>

---

### 🏆 Trophies
<p align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=YOUR_USERNAME&theme=onedark&column=6" />
</p>

---

### 📈 Contribution Graph
<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=YOUR_USERNAME&theme=react-dark&hide_border=true" />
</p>

---

### 🎯 Progress Bars

<div align="center">
  <p>Python</p>
  <img src="https://progress-bar.dev/85/?title=Python&width=500&color=blue" />
  
  <p>JavaScript</p>
  <img src="https://progress-bar.dev/75/?title=JavaScript&width=500&color=yellow" />
  
  <p>React</p>
  <img src="https://progress-bar.dev/60/?title=React&width=500&color=cyan" />
</div>
