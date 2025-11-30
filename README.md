<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Nandhavardhan Achari — Waiting for you</title>
  <meta name="description" content="Nandhavardhan Achari is waiting for you." />

  <style>
    /* Reset */
    *{box-sizing:border-box;margin:0;padding:0}
    html,body{height:100%}
    body{
      font-family:Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
      min-height:100%;
      display:flex;
      align-items:center;
      justify-content:center;
      background: radial-gradient(1200px 600px at 10% 10%, rgba(255,230,120,0.06), transparent),
                  radial-gradient(1000px 500px at 90% 90%, rgba(255,200,80,0.04), transparent),
                  linear-gradient(180deg,#0b0b0b,#121212);
      color:#fff;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      padding:32px;
    }

    .card{
      width:100%;
      max-width:880px;
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:18px;
      box-shadow: 0 10px 30px rgba(2,2,2,0.6), inset 0 1px 0 rgba(255,255,255,0.02);
      padding:48px;
      text-align:center;
      border:1px solid rgba(255,215,140,0.06);
    }

    .title{
      font-size:clamp(28px,5vw,52px);
      line-height:1.02;
      font-weight:700;
      letter-spacing:0.4px;
      margin-bottom:12px;
      background: linear-gradient(90deg,#ffd66b,#ffb84d,#ffd66b);
      -webkit-background-clip:text;
      background-clip:text;
      color:transparent;
      text-shadow: 0 6px 18px rgba(0,0,0,0.6);
      position:relative;
    }

    .subtitle{
      font-size:16px;
      color:rgba(255,255,255,0.75);
      margin-bottom:24px;
    }

    .gold-crest{
      display:inline-block;
      background:linear-gradient(45deg,#ffd66b,#ffb84d,#ffd66b);
      padding:10px 18px;
      border-radius:999px;
      font-weight:700;
      color:#111;
      box-shadow: 0 6px 22px rgba(255,184,77,0.12);
      margin-bottom:22px;
    }

    .cta-row{display:flex;gap:12px;justify-content:center;flex-wrap:wrap}

    .btn{
      padding:12px 20px;
      border-radius:10px;
      border:1px solid rgba(255,215,140,0.16);
      font-weight:600;
      cursor:pointer;
      min-width:160px;
    }

    .btn-primary{
      background:linear-gradient(90deg,#ffe79a,#ffcf6b);
      color:#111;
      box-shadow: 0 12px 30px rgba(255,187,79,0.12);
      transform:translateY(0);
      transition:transform .18s ease,box-shadow .18s ease;
    }
    .btn-primary:active{transform:translateY(2px)}
    .btn-secondary{
      background:transparent;color:rgba(255,255,255,0.9);
    }

    .footer{
      margin-top:26px;color:rgba(255,255,255,0.45);font-size:13px
    }

    /* small animated sparkle behind the title */
    .sparkle{
      position:absolute;left:50%;top:-10px;pointer-events:none;transform:translateX(-50%);
      width:220px;height:220px;border-radius:50%;
      background: radial-gradient(circle at 30% 30%, rgba(255,220,140,0.18), transparent 20%),
                  radial-gradient(circle at 70% 70%, rgba(255,200,80,0.12), transparent 15%);
      filter:blur(28px);opacity:0.9;mix-blend-mode:screen;z-index:0
    }

    .title-wrap{position:relative;display:inline-block;padding:6px 10px}

    /* tiny animation */
    @keyframes shimmer {0%{transform:translateX(-100%)}100%{transform:translateX(100%)}}
    .shimmer-line{position:absolute;left:0;top:0;height:100%;width:100%;overflow:hidden;border-radius:8px}
    .shimmer-line::after{content:'';position:absolute;left:-120%;top:0;height:100%;width:120%;background:linear-gradient(90deg,transparent,rgba(255,255,255,0.14),transparent);animation:shimmer 2.5s linear infinite}

    /* Responsive */
    @media (max-width:480px){
      .card{padding:28px;border-radius:14px}
      .gold-crest{padding:8px 14px}
    }
  </style>
</head>
<body>
  <div class="card" role="main">
    <div class="title-wrap">
      <div class="sparkle" aria-hidden="true"></div>
      <h1 class="title">Nandhavardhan Achari is waiting for you</h1>
      <div class="shimmer-line" aria-hidden="true"></div>
    </div>

    <div style="height:12px"></div>

    <div class="gold-crest" aria-hidden="true">Premium</div>

    <p class="subtitle">Simple. Elegant. Memorable.</p>

    <div class="cta-row">
      <button class="btn btn-primary" onclick="copyMessage()" aria-label="Copy message">Copy message</button>
      <button class="btn btn-secondary" onclick="shareWeb()" aria-label="Share link">Share link</button>
    </div>

    <p class="footer">Tip: You can host this page for free (GitHub Pages / Netlify / Vercel). Use the "Copy message" button to copy the headline quickly.</p>
  </div>

  <script>
    function copyMessage(){
      const txt = 'Nandha Vardhan is waiting for you.';
      if(navigator.clipboard){
        navigator.clipboard.writeText(txt).then(()=>{
          alert('Message copied to clipboard!');
        }).catch(()=>{prompt('Copy this message:',txt)});
      } else {
        prompt('Copy this message:',txt);
      }
    }

    function shareWeb(){
      const u = window.location.href;
      if(navigator.share){
        navigator.share({title:document.title,text:'Nandha Vardhan is waiting for you.',url:u}).catch(()=>{});
      } else {
        prompt('Share this page URL',u);
      }
    }
  </script>
</body>
</html>
