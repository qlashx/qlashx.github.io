<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>qlashx — reversing &amp; mobile security</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Newsreader:opsz,wght@6..72,400;6..72,500;6..72,600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#14171c;
    --panel:#1a1e24;
    --line:#2a2f38;
    --text:#d7dbe0;
    --muted:#7f8792;
    --amber:#e0a458;
    --amber-dim:#b9823f;
  }
  *{box-sizing:border-box;margin:0;padding:0}
  html{scroll-behavior:smooth}
  body{
    background:var(--bg);
    color:var(--text);
    font-family:"Newsreader",Georgia,serif;
    font-size:18px;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }
  a{color:inherit;text-decoration:none}
  .wrap{max-width:720px;margin:0 auto;padding:0 24px}

  /* header */
  header{border-bottom:1px solid var(--line);padding:40px 0 28px}
  .brand{
    font-family:"JetBrains Mono",monospace;
    font-weight:700;
    font-size:20px;
    letter-spacing:-0.5px;
    color:var(--text);
    display:inline-flex;align-items:baseline;gap:2px;
  }
  .brand .prompt{color:var(--amber)}
  .brand .cursor{
    display:inline-block;width:9px;height:18px;background:var(--amber);
    margin-left:4px;transform:translateY(2px);
    animation:blink 1.1s steps(1) infinite;
  }
  @keyframes blink{50%{opacity:0}}
  .tag{
    font-family:"JetBrains Mono",monospace;
    font-size:13px;color:var(--muted);margin-top:12px;letter-spacing:0.2px;
  }
  nav{margin-top:20px;display:flex;gap:20px}
  nav a{
    font-family:"JetBrains Mono",monospace;font-size:13px;color:var(--muted);
    padding-bottom:2px;border-bottom:1px solid transparent;transition:.15s;
  }
  nav a:hover{color:var(--amber);border-color:var(--amber-dim)}

  /* intro */
  .intro{padding:36px 0 8px;color:var(--muted);font-size:17px}
  .intro b{color:var(--text);font-weight:500}

  /* post list */
  .posts{padding:16px 0 64px}
  .list-label{
    font-family:"JetBrains Mono",monospace;font-size:12px;text-transform:uppercase;
    letter-spacing:2px;color:var(--muted);padding:24px 0 4px;
    border-bottom:1px solid var(--line);margin-bottom:8px;
  }
  .post{
    display:block;padding:22px 0;border-bottom:1px solid var(--line);
    transition:.15s;
  }
  .post:hover{padding-left:10px}
  .post .meta{
    font-family:"JetBrains Mono",monospace;font-size:12px;color:var(--muted);
    display:flex;gap:14px;margin-bottom:8px;flex-wrap:wrap;
  }
  .post .meta .cat{color:var(--amber)}
  .post h2{
    font-family:"Newsreader",serif;font-weight:600;font-size:26px;
    line-height:1.2;color:var(--text);transition:.15s;
  }
  .post:hover h2{color:var(--amber)}
  .post p{color:var(--muted);font-size:16px;margin-top:6px}

  footer{
    border-top:1px solid var(--line);padding:28px 0 48px;
    font-family:"JetBrains Mono",monospace;font-size:12px;color:var(--muted);
    display:flex;justify-content:space-between;flex-wrap:wrap;gap:8px;
  }
  footer a:hover{color:var(--amber)}

  @media(max-width:520px){
    body{font-size:17px}
    .post h2{font-size:22px}
  }
</style>
</head>
<body>
<div class="wrap">

  <header>
    <a href="index.html" class="brand"><span class="prompt">~/</span>qlashx<span class="cursor"></span></a>
    <div class="tag">android reversing · mobile security · ctf writeups</div>
    <nav>
      <a href="index.html">home</a>
      <a href="https://github.com/qlashx" target="_blank" rel="noopener">github</a>
      <a href="#posts">posts</a>
    </nav>
  </header>

  <p class="intro">
    Notes from taking apart Android apps — <b>deep links, Frida hooks, native flag builders,</b>
    and whatever else the target throws up. Mostly writeups, written the way I'd want to read them.
  </p>

  <section class="posts" id="posts">
    <div class="list-label">Writeups</div>

    <a class="post" href="posts/strings-challenge.html">
      <div class="meta">
        <span class="cat">mobile / android</span>
        <span>frida · deep links · jni</span>
      </div>
      <h2>Strings — Mobile Hacking Lab</h2>
      <p>An exported activity, an uninitialized date check, an AES gate, and a native <code>getflag()</code> that hides the real flag in memory.</p>
    </a>

  </section>

  <footer>
    <span>© qlashx</span>
    <span><a href="https://github.com/qlashx" target="_blank" rel="noopener">github.com/qlashx</a></span>
  </footer>

</div>
</body>
</html>
