<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Happy 5-Month Anniversary — Goral</title>
  <style>
    :root{
      --bg1:#ff9a9e; --bg2:#fad0c4; --accent:#fff;
      --card-bg: rgba(255,255,255,0.14);
      --glass: rgba(255,255,255,0.12);
      --shadow: 0 10px 30px rgba(0,0,0,0.18);
      --heart-color:#ff3b6b;
      --font-sans: 'Helvetica Neue', Arial, sans-serif;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:var(--font-sans);background:linear-gradient(135deg,var(--bg1),var(--bg2));}

    .wrap{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:30px}

    .card{
      width:960px;max-width:98vw;background:linear-gradient(135deg, rgba(255,255,255,0.06), rgba(255,255,255,0.03));
      border-radius:18px;padding:40px;box-shadow:var(--shadow);backdrop-filter: blur(6px);
      position:relative;overflow:hidden;border:1px solid rgba(255,255,255,0.12);
    }

    header{display:flex;gap:20px;align-items:center}
    .logo{width:96px;height:96px;border-radius:50%;background:linear-gradient(145deg,var(--heart-color),#ff7fa1);display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:34px;box-shadow:0 6px 18px rgba(0,0,0,0.2)}

    h1{margin:0;font-size:34px;color:var(--accent);text-shadow:0 2px 8px rgba(0,0,0,0.2)}
    p.lead{margin:8px 0 0;color:rgba(255,255,255,0.92)}

    .content{display:grid;grid-template-columns:1fr 360px;gap:28px;margin-top:28px}

    .left{min-height:320px;padding:22px;border-radius:12px;background:var(--card-bg);}

    .message{font-size:18px;color:var(--accent);line-height:1.5}
    .message .name{font-weight:800;color:#fff;font-size:22px}

    .photo{height:260px;border-radius:12px;background:linear-gradient(180deg,rgba(255,255,255,0.05),rgba(255,255,255,0.02));display:flex;align-items:center;justify-content:center;color:rgba(255,255,255,0.7);font-size:16px}
    .controls{display:flex;gap:10px;margin-top:14px}

    .btn{background:rgba(255,255,255,0.12);border:1px solid rgba(255,255,255,0.08);padding:10px 14px;border-radius:10px;color:white;cursor:pointer;backdrop-filter: blur(3px)}
    .btn:active{transform:translateY(1px)}

    .right{padding:18px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));display:flex;flex-direction:column;gap:16px;align-items:center}

    .count{font-size:40px;font-weight:800}
    small{color:rgba(255,255,255,0.85)}

    /* floating hearts */
    .heart{position:absolute;opacity:0.95;filter:drop-shadow(0 6px 12px rgba(255,0,80,0.15));}

    /* confetti canvas on top */
    #confetti{position:absolute;inset:0;pointer-events:none}

    footer{margin-top:18px;color:rgba(255,255,255,0.78);font-size:13px}

    @media (max-width:880px){
      .content{grid-template-columns:1fr}
      .right{order:2}
    }
  </style>
</head>
<body>
  <div class="wrap">
    <div class="card" role="main">
      <canvas id="confetti"></canvas>

      <header>
        <div class="logo">💖</div>
        <div>
          <h1>Happy <span id="monthsTitle">5-Month</span> Anniversary, <span style="color:#fff" id="displayName">Goral</span> 🎉</h1>
          <p class="lead">A special little page to celebrate five months of love and memories.</p>
        </div>
      </header>

      <div class="content">
        <section class="left">
          <div class="photo" id="photo">
            Click to add your favourite photo of you two (paste an image URL).
          </div>

          <div class="message" style="margin-top:18px">
            <div>To my dearest <span class="name">Goral</span>,</div>
            <div style="margin-top:10px">Happy 5-month anniversary! These five months have been the sweetest — thank you for every laugh, every hug, and every little moment in between. I can't wait for all the months ahead with you.</div>
            <div style="margin-top:14px;font-weight:700">— With all my love</div>
          </div>

          <div class="controls">
            <button class="btn" id="playBtn">Play a little tune ▶</button>
            <button class="btn" id="confettiBtn">Celebrate 🎊</button>
            <button class="btn" id="toggleHearts">Toggle Floating Hearts ❤️</button>
          </div>
        </section>

        <aside class="right">
          <div style="text-align:center">
            <div class="count" id="monthsCount">5</div>
            <small>Months together</small>
          </div>

          <div style="text-align:center">
            <div id="sinceDate">Since: <strong id="dateText">(Edit in code)</strong></div>
          </div>

          <div style="width:100%;text-align:center">
            <small>Tip: open this file in a browser. To personalise, edit the HTML — change the name, message, and replace the photo block with an &lt;img&gt; tag, or click the photo and paste a URL.</small>
          </div>
        </aside>
      </div>

      <footer>
        Made with ❤️ — Save this file as <code>anniversary_goral_5months.html</code> and open it in a browser.
      </footer>

      <!-- decorative hearts (template elements) -->
      <svg style="display:none">
        <symbol id="heart" viewBox="0 0 32 29.6"><path d="M23.6 0c-2.9 0-5.4 1.7-6.6 4.2C15.8 1.7 13.3 0 10.4 0 4.7 0 0 4.8 0 10.6c0 6.6 5.4 11.9 13.5 18.3L16 30l2.5-1.1C26.6 22.5 32 17.2 32 10.6 32 4.8 27.3 0 21.6 0z"/></symbol>
      </svg>

    </div>
  </div>

  <script>
    // --------------------- Personalize these variables --------------------
    const PERSON_NAME = 'Goral';
    const ANNIVERSARY_MONTHS = 5; // the page celebrates 5 months together
    // Optional: set START_DATE (YYYY-MM-DD) if you want "Since:" to show the start date
    const START_DATE = '';
    // --------------------------------------------------------------------

    // populate name and date text
    document.addEventListener('DOMContentLoaded', ()=>{
      document.querySelector('.name').textContent = PERSON_NAME;
      document.getElementById('displayName').textContent = PERSON_NAME;
      document.getElementById('monthsCount').textContent = ANNIVERSARY_MONTHS;
      document.getElementById('monthsTitle').textContent = ANNIVERSARY_MONTHS + '-Month';

      if(START_DATE){
        const d = new Date(START_DATE);
        if(!isNaN(d)) document.getElementById('dateText').textContent = d.toDateString();
        else document.getElementById('dateText').textContent = '(invalid date)';
      } else {
        document.getElementById('dateText').textContent = '(optional) set START_DATE in the code';
      }
    });

    // --------------------- Confetti (simple) ------------------------------
    const confettiCanvas = document.getElementById('confetti');
    const ctx = confettiCanvas.getContext('2d');
    let confettiPieces = [];
    function resize(){ confettiCanvas.width = confettiCanvas.clientWidth; confettiCanvas.height = confettiCanvas.clientHeight; }
    window.addEventListener('resize', resize); resize();

    function makeConfetti(){
      confettiPieces = [];
      const colors = ['#ff5d7a','#ffd166','#6ee7b7','#9ad0f5','#ffb3c6'];
      for(let i=0;i<120;i++){
        confettiPieces.push({
          x: Math.random()*confettiCanvas.width,
          y: Math.random()*-confettiCanvas.height,
          w: 6+Math.random()*10,
          h: 6+Math.random()*10,
          r: Math.random()*360,
          speed: 1+Math.random()*4,
          color: colors[Math.floor(Math.random()*colors.length)],
        })
      }
    }

    function drawConfetti(){
      ctx.clearRect(0,0,confettiCanvas.width,confettiCanvas.height);
      confettiPieces.forEach(p=>{
        ctx.save(); ctx.translate(p.x,p.y); ctx.rotate(p.r*Math.PI/180);
        ctx.fillStyle = p.color; ctx.fillRect(-p.w/2,-p.h/2,p.w,p.h);
        ctx.restore();
        p.y += p.speed; p.r += p.speed*2;
        if(p.y>confettiCanvas.height+20){ p.y = -20; p.x = Math.random()*confettiCanvas.width; }
      });
      requestAnimationFrame(drawConfetti);
    }

    document.getElementById('confettiBtn').addEventListener('click', ()=>{
      makeConfetti(); drawConfetti();
    });

    // --------------------- Floating hearts -------------------------------
    let heartsOn = false;
    let heartsInterval;
    function createHeart(){
      const size = 24 + Math.random()*48;
      const svg = document.createElementNS('http://www.w3.org/2000/svg','svg');
      svg.setAttribute('class','heart'); svg.setAttribute('width',size); svg.setAttribute('height',size*(29.6/32));
      svg.style.left = (10 + Math.random()*80) + '%'; svg.style.top = (60 + Math.random()*30) + '%';
      svg.style.opacity = 0.9 - Math.random()*0.4; svg.style.transform = `translateY(${Math.random()*30}px)`;
      const use = document.createElementNS('http://www.w3.org/2000/svg','use'); use.setAttributeNS('http://www.w3.org/1999/xlink','href','#heart');
      use.setAttribute('fill', '#ff6b93');
      svg.appendChild(use);
      document.querySelector('.card').appendChild(svg);
      // animate up and fade
      const dur = 6000 + Math.random()*4000;
      svg.animate([{transform: 'translateY(0px)', opacity: svg.style.opacity},{transform: 'translateY(-180px)', opacity: 0}],{duration:dur, easing:'ease-out'});
      setTimeout(()=>{ if(svg.parentNode) svg.parentNode.removeChild(svg); }, dur+50);
    }

    document.getElementById('toggleHearts').addEventListener('click', ()=>{
      heartsOn = !heartsOn;
      if(heartsOn){ heartsInterval = setInterval(createHeart, 700); }
      else{ clearInterval(heartsInterval); }
    });

    // --------------------- Simple melody via Web Audio -------------------
    let audioCtx, isPlaying=false;
    document.getElementById('playBtn').addEventListener('click', async ()=>{
      if(isPlaying) return;
      try{
        audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        const now = audioCtx.currentTime;
        const master = audioCtx.createGain(); master.connect(audioCtx.destination); master.gain.value = 0.12;
        const notes = [440,494,523,659,587,523]; // simple tune (A4,B4,C5,E5,D5,C5)
        let t = now;
        notes.forEach((f,i)=>{
          const o = audioCtx.createOscillator(); const g = audioCtx.createGain(); o.type='sine'; o.frequency.value = f; o.connect(g); g.connect(master);
          g.gain.setValueAtTime(0.0001,t); g.gain.exponentialRampToValueAtTime(1,t+0.02); g.gain.exponentialRampToValueAtTime(0.0001,t+0.45);
          o.start(t); o.stop(t+0.5);
          t += 0.45;
        });
        isPlaying=true; setTimeout(()=>{ isPlaying=false; }, notes.length*450);
      }catch(e){ console.warn('Audio failed',e); }
    });

    // --------------------- small UX: click photo to add image ----------------
    const photo = document.getElementById('photo');
    photo.addEventListener('click', ()=>{
      const url = prompt('Paste the image URL to show here (or cancel):');
      if(url){ photo.innerHTML = `<img src="${url}" alt="photo" style="width:100%;height:100%;object-fit:cover;border-radius:10px">`; }
    });

  </script>
</body>
</html>
