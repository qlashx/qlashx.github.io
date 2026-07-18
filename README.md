<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>qlashx</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Newsreader:opsz,wght@6..72,400;6..72,500;6..72,600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#14171c;
    --line:#2a2f38;
    --text:#d7dbe0;
    --muted:#7f8792;
    --amber:#e0a458;
    --amber-dim:#b9823f;
  }
  *{box-sizing:border-box;margin:0;padding:0}
  body{
    background:var(--bg);
    color:var(--text);
    font-family:"JetBrains Mono",monospace;
    min-height:100vh;
    display:flex;
    flex-direction:column;
    -webkit-font-smoothing:antialiased;
    overflow-x:hidden;
  }

  /* subtle grid backdrop */
  body::before{
    content:"";
    position:fixed;inset:0;
    background-image:
      linear-gradient(var(--line) 1px,transparent 1px),
      linear-gradient(90deg,var(--line) 1px,transparent 1px);
    background-size:52px 52px;
    opacity:.15;
    -webkit-mask-image:radial-gradient(ellipse 80% 70% at 50% 45%,#000 30%,transparent 80%);
            mask-image:radial-gradient(ellipse 80% 70% at 50% 45%,#000 30%,transparent 80%);
    pointer-events:none;
  }

  /* top bar */
  .topbar{
    position:relative;z-index:2;
    display:flex;justify-content:space-between;align-items:center;
    padding:30px 40px;
    font-size:15px;color:var(--muted);
  }
  .topbar .status{display:flex;align-items:center;gap:9px;font-size:14px}
  .dot{width:8px;height:8px;border-radius:50%;background:var(--amber);
       box-shadow:0 0 8px var(--amber);animation:pulse 2s ease-in-out infinite}
  @keyframes pulse{50%{opacity:.4}}
  .topbar nav{display:flex;gap:34px}
  .topbar nav a{
    color:var(--muted);text-decoration:none;transition:.15s;
    font-size:15px;letter-spacing:.3px;padding-bottom:3px;
    border-bottom:1px solid transparent;
  }
  .topbar nav a:hover{color:var(--amber)}
  .topbar nav a.active{color:var(--text);border-color:var(--amber-dim)}
  .topbar nav a.soon{opacity:.5;cursor:default}
  .topbar nav a.soon:hover{color:var(--muted)}

  /* hero */
  main{
    position:relative;z-index:2;
    flex:1;display:flex;flex-direction:column;
    align-items:center;justify-content:center;
    text-align:center;padding:40px 24px;
  }
  h1{
    font-family:"JetBrains Mono",monospace;
    font-weight:700;
    font-size:clamp(46px,12vw,100px);
    letter-spacing:-2px;
    line-height:1;
    color:#eef1f4;
    display:inline-flex;align-items:baseline;
    opacity:0;animation:rise .6s ease .1s forwards;
  }
  h1 .prompt{color:var(--amber);margin-right:2px}
  h1 .cursor{
    display:inline-block;width:.5ch;height:.9em;background:var(--amber);
    margin-left:.06em;transform:translateY(.05em);
    animation:blink 1.1s steps(1) infinite;
  }
  @keyframes blink{50%{opacity:0}}

  .tagline{
    font-family:"Newsreader",serif;
    font-size:clamp(18px,3.6vw,24px);
    color:var(--muted);
    margin-top:30px;max-width:540px;line-height:1.5;
    opacity:0;animation:rise .6s ease .28s forwards;
  }
  .tagline .type{color:var(--text)}

  @keyframes rise{to{opacity:1;transform:translateY(0)}}
  h1,.tagline{transform:translateY(14px)}

  /* footer */
  footer{
    position:relative;z-index:2;
    padding:26px 40px;text-align:center;
    font-size:13px;color:var(--muted);letter-spacing:.3px;
  }

  @media (prefers-reduced-motion:reduce){
    *{animation:none!important}
    h1,.tagline{opacity:1;transform:none}
  }
  @media(max-width:520px){
    .topbar{padding:22px}
    .topbar nav{gap:22px}
    .topbar nav a{font-size:14px}
  }
</style>
</head>
<body>

  <div class="topbar">
    <div class="status"><span class="dot"></span> online</div>
    <nav>
      <a href="index.html" class="active">home</a>
      <a class="soon" title="coming soon">profile</a>
      <a class="soon" title="coming soon">posts</a>
    </nav>
  </div>

  <main>
    <h1><span class="prompt">~/</span>qlashx<span class="cursor"></span></h1>

    <p class="tagline">
      just a <span class="type">noob pentester</span> who wants to develop himself.
    </p>
  </main>

  <footer>© qlashx — ahmed osama</footer>

</body>
</html>
