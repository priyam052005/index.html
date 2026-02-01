<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>For Disna (Baju) 💘</title>

  <style>
    :root{
      --bgA:#fff0f7;
      --bgB:#ffe3f2;
      --ink:#4b0f33;
      --muted:#7a2a52;

      --yes:#ff4d8d;
      --yes2:#ff78aa;

      --no:#ffe2ee;
      --noInk:#7a2a52;

      --card:#ffffffd8;
      --stroke:#ffc3da;

      --shadow: 0 20px 60px rgba(255, 77, 141, 0.22);
    }

    *{ box-sizing:border-box; }
    body{
      margin:0;
      min-height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:18px;
      font-family: ui-rounded, system-ui, -apple-system, "Segoe UI", Roboto, Arial, sans-serif;
      color:var(--ink);
      overflow:hidden;

      background:
        radial-gradient(900px 520px at 20% 10%, var(--bgB), transparent 70%),
        radial-gradient(900px 520px at 80% 30%, #ffeef7, transparent 70%),
        linear-gradient(180deg, var(--bgA), #fff);
    }

    /* floating hearts background */
    .hearts{
      position:fixed;
      inset:0;
      pointer-events:none;
      overflow:hidden;
      opacity:0.55;
      filter: blur(0.1px);
    }
    .heart{
      position:absolute;
      font-size:18px;
      animation: floatUp linear forwards;
      transform: translateY(110vh);
      user-select:none;
    }
    @keyframes floatUp{
      from { transform: translateY(110vh) translateX(0) rotate(0deg); opacity:0; }
      10%  { opacity:1; }
      to   { transform: translateY(-20vh) translateX(var(--drift)) rotate(240deg); opacity:0; }
    }

    .card{
      width:min(780px, 96vw);
      background: var(--card);
      border: 1px solid var(--stroke);
      border-radius: 26px;
      box-shadow: var(--shadow);
      padding: 22px 18px 16px;
      position:relative;
      backdrop-filter: blur(10px);
    }

    .badge{
      position:absolute;
      top:14px;
      left:14px;
      padding: 8px 12px;
      border-radius: 999px;
      border: 1px solid #ffd1e3;
      background: #fff;
      font-weight: 800;
      font-size: 12px;
      color:#b1005a;
      box-shadow: 0 10px 22px rgba(0,0,0,0.06);
    }

    h1{
      margin: 6px 0 6px;
      text-align:center;
      color:#b1005a;
      font-size: clamp(24px, 3.2vw, 38px);
      line-height:1.12;
      letter-spacing: .2px;
    }
    .sub{
      text-align:center;
      margin: 0 auto 14px;
      color: var(--muted);
      font-size: 14px;
    }

    .arena{
      position:relative;
      height: 290px;
      border-radius: 20px;
      border: 1px dashed #ffc1d7;
      background:
        radial-gradient(220px 140px at 25% 30%, #fff3f9, transparent 72%),
        radial-gradient(220px 140px at 75% 65%, #fff1f7, transparent 72%),
        linear-gradient(180deg, #fff, #fff7fb);
      overflow:hidden;
    }

    .sparkle{
      position:absolute;
      inset:-40px;
      background:
        radial-gradient(circle at 10% 20%, rgba(255, 180, 210, 0.35), transparent 30%),
        radial-gradient(circle at 80% 25%, rgba(255, 210, 230, 0.30), transparent 28%),
        radial-gradient(circle at 40% 80%, rgba(255, 200, 225, 0.25), transparent 28%);
      filter: blur(0.4px);
      animation: shimmer 4.5s ease-in-out infinite;
      pointer-events:none;
    }
    @keyframes shimmer{
      0%,100%{ transform: translateY(0); opacity:0.75; }
      50%{ transform: translateY(8px); opacity:1; }
    }

    .btn{
      position:absolute;
      border:0;
      border-radius: 999px;
      padding: 14px 22px;
      font-weight: 900;
      cursor:pointer;
      user-select:none;
      letter-spacing: .3px;
      box-shadow: 0 14px 28px rgba(0,0,0,0.10);
      transition: transform .12s ease, box-shadow .12s ease, filter .12s ease;
      will-change: transform;
    }
    .btn:active{ transform: scale(0.98); }

    #yesBtn{
      left: 34%;
      top: 62%;
      transform: translate(-50%, -50%);
      font-size: 18px;
      color:white;
      background: linear-gradient(135deg, var(--yes), var(--yes2));
      text-shadow: 0 2px 10px rgba(0,0,0,0.12);
    }
    #yesBtn:hover{ filter: brightness(1.02); box-shadow: 0 18px 34px rgba(255, 77, 141, 0.28); }

    #noBtn{
      left: 66%;
      top: 62%;
      transform: translate(-50%, -50%);
      font-size: 16px;
      color: var(--noInk);
      background: linear-gradient(180deg, #fff, var(--no));
      border: 1px solid #ffd1e3;
    }
    #noBtn:hover{ box-shadow: 0 18px 34px rgba(0,0,0,0.10); }

    .footer{
      margin-top: 12px;
      font-size: 12px;
      color: #8c3a63;
      text-align:center;
      opacity:0.92;
    }

    /* Modal */
    .overlay{
      position:fixed;
      inset:0;
      background: rgba(30, 0, 18, 0.38);
      display:none;
      align-items:center;
      justify-content:center;
      padding:18px;
      z-index:50;
    }
    .modal{
      width:min(720px, 96vw);
      background: white;
      border-radius: 26px;
      padding: 22px 18px 16px;
      border: 1px solid #ffd1e3;
      box-shadow: 0 30px 90px rgba(0,0,0,0.25);
      text-align:center;
      position:relative;
      overflow:hidden;
    }
    .modal h2{
      margin: 0 0 8px;
      color:#b1005a;
      font-size: clamp(24px, 3.2vw, 40px);
      letter-spacing: .2px;
    }
    .modal p{
      margin: 8px auto 0;
      color: var(--muted);
      font-size: 15px;
      line-height: 1.5;
      max-width: 56ch;
      white-space: pre-line;
    }

    .gifWrap{
      display:flex;
      justify-content:center;
      margin: 10px 0 6px;
    }
    .gifWrap img{
      width:min(360px, 90%);
      border-radius: 18px;
      border: 1px solid #ffd1e3;
      box-shadow: 0 16px 32px rgba(0,0,0,0.10);
    }

    .actions{
      display:flex;
      gap:10px;
      justify-content:center;
      margin-top: 14px;
      flex-wrap:wrap;
    }
    .smallBtn{
      border:0;
      border-radius:999px;
      padding: 10px 16px;
      font-weight:900;
      cursor:pointer;
      box-shadow: 0 12px 22px rgba(0,0,0,0.10);
      transition: transform .12s ease;
    }
    .smallBtn:active{ transform: scale(0.98); }
    .pink{ background: linear-gradient(135deg, var(--yes), var(--yes2)); color:white; }
    .soft{ background: linear-gradient(180deg, #fff, var(--no)); color: var(--muted); border:1px solid #ffd1e3; }

    /* Confetti */
    .confetti{
      position:absolute;
      inset:0;
      pointer-events:none;
      overflow:hidden;
    }
    .piece{
      position:absolute;
      width:10px;
      height:14px;
      border-radius: 3px;
      opacity:0.96;
      animation: fall linear forwards;
    }
    @keyframes fall{
      from { transform: translateY(-30px) rotate(0deg); }
      to   { transform: translateY(560px) rotate(720deg); }
    }
  </style>
</head>

<body>
  <div class="hearts" id="hearts"></div>

  <div class="card">
    <div class="badge">made with 💖</div>

    <h1>Disna (Baju), will you be my Valentine? 💘</h1>
    <div class="sub" id="subtitle">Choose wisely 😌</div>

    <div class="arena" id="arena">
      <div class="sparkle"></div>
      <button class="btn" id="yesBtn">YES 💖</button>
      <button class="btn" id="noBtn">NO 🙃</button>
    </div>

    <div class="footer">P.S. Clicking NO has consequences 😈</div>
  </div>

  <div class="overlay" id="overlay">
    <div class="modal" role="dialog" aria-modal="true">
      <div class="confetti" id="confetti"></div>

      <h2>YAYYYY DISNA!!! 💞</h2>

      <div class="gifWrap">
        <!-- Celebration GIF (dancing) -->
        <img
          alt="Celebration dance"
          src="https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExZDJvang5eHQ0OHc4YmtseWd4ZHFxb3Y5ODY5ank3Nm1tbGx5b3o5YSZlcD12MV9naWZzX3NlYXJjaCZjdD1n/fUQ4rhUZJYiQsas6WD/200w.gif"
        />
      </div>

      <p>
Official Valentine Status: ACCEPTED 💌

Reward unlocked:
🍫 snacks
🤗 hugs
🌸 cute date

Now screenshot this as proof 😌
      </p>

      <div class="actions">
        <button class="smallBtn soft" id="replayBtn">Replay 🔁</button>
        <button class="smallBtn pink" id="closeBtn">Close 💘</button>
      </div>
    </div>
  </div>

  <script>
    // Cute floating hearts background
    const hearts = document.getElementById("hearts");
    const heartChars = ["💗","💖","💘","💝","💕","💞","💓","🌸","✨"];
    function spawnHeart(){
      const h = document.createElement("div");
      h.className = "heart";
      h.textContent = heartChars[Math.floor(Math.random()*heartChars.length)];
      const left = Math.random()*100;
      const size = 14 + Math.random()*18;
      const dur  = 6 + Math.random()*6;
      const drift = (Math.random()*120 - 60) + "px";
      h.style.left = left + "%";
      h.style.fontSize = size + "px";
      h.style.animationDuration = dur + "s";
      h.style.setProperty("--drift", drift);
      hearts.appendChild(h);
      setTimeout(()=> h.remove(), dur*1000);
    }
    setInterval(spawnHeart, 380);

    const arena = document.getElementById("arena");
    const yesBtn = document.getElementById("yesBtn");
    const noBtn  = document.getElementById("noBtn");
    const subtitle = document.getElementById("subtitle");

    const overlay = document.getElementById("overlay");
    const confetti = document.getElementById("confetti");
    const replayBtn = document.getElementById("replayBtn");
    const closeBtn = document.getElementById("closeBtn");

    let noClicks = 0;
    let yesScale = 1;

    const lines = [
      "Baju… are you sure? 🥺",
      "Okay okay… think again 😭",
      "NO is a strong word 😤",
      "I’m gonna pretend I didn’t see that 🙈",
      "Last chance… 👀",
      "The YES button is looking comfy 😌",
      "You can’t resist forever 😈",
      "At this point… just click YES 😂"
    ];

    function clamp(val, min, max){ return Math.max(min, Math.min(max, val)); }

    function moveNoButton() {
      const a = arena.getBoundingClientRect();
      const b = noBtn.getBoundingClientRect();
      const margin = 16;

      const maxX = a.width - b.width - margin;
      const maxY = a.height - b.height - margin;

      const x = clamp(Math.random() * maxX + margin/2, margin/2, maxX + margin/2);
      const y = clamp(Math.random() * maxY + margin/2, margin/2, maxY + margin/2);

      noBtn.style.left = `${x}px`;
      noBtn.style.top  = `${y}px`;
      noBtn.style.transform = "translate(0, 0)";
    }

    function growYesButton() {
      yesScale = Math.min(3.1, yesScale + 0.19);
      yesBtn.style.transform = `translate(-50%, -50%) scale(${yesScale})`;
      yesBtn.style.boxShadow = `0 18px 38px rgba(255, 77, 141, ${0.18 + yesScale*0.10})`;
    }

    function makeConfetti() {
      confetti.innerHTML = "";
      const pieces = 140;
      for (let i=0; i<pieces; i++){
        const p = document.createElement("div");
        p.className = "piece";
        const left = Math.random()*100;
        const dur = 1.7 + Math.random()*1.7;
        const delay = Math.random()*0.25;

        const hue = Math.floor(320 + Math.random()*70) % 360; // pink/purple range
        p.style.background = `hsl(${hue} 95% 70%)`;

        p.style.left = `${left}%`;
        p.style.animationDuration = `${dur}s`;
        p.style.animationDelay = `${delay}s`;
        p.style.top = `-20px`;

        confetti.appendChild(p);
      }
    }

    function openModal() {
      makeConfetti();
      overlay.style.display = "flex";
    }
    function closeModal() {
      overlay.style.display = "none";
      confetti.innerHTML = "";
    }

    function reset() {
      noClicks = 0;
      yesScale = 1;
      subtitle.textContent = "Choose wisely 😌";

      yesBtn.style.transform = "translate(-50%, -50%) scale(1)";
      yesBtn.style.boxShadow = "0 14px 28px rgba(0,0,0,0.10)";

      noBtn.style.left = "66%";
      noBtn.style.top = "62%";
      noBtn.style.transform = "translate(-50%, -50%)";
    }

    // NO runs away (click)
    noBtn.addEventListener("click", () => {
      noClicks += 1;
      subtitle.textContent = lines[Math.min(noClicks - 1, lines.length - 1)];
      growYesButton();
      moveNoButton();
    });

    // Also run away on hover after first NO (desktop fun)
    noBtn.addEventListener("mouseenter", () => {
      if (noClicks >= 1) moveNoButton();
    });

    // YES = celebration
    yesBtn.addEventListener("click", () => openModal());

    replayBtn.addEventListener("click", () => {
      closeModal();
      reset();
    });

    closeBtn.addEventListener("click", () => closeModal());

    window.addEventListener("resize", () => {
      if (noClicks >= 1) moveNoButton();
    });
  </script>
</body>
</html>
