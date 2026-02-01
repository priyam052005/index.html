<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>For Disna (Baju) 💘</title>
  <style>
    :root{
      --bg1:#fff0f6;
      --bg2:#ffe3ef;
      --text:#5a1440;
      --muted:#7a2a52;
      --yes:#ff4d8d;
      --yesHover:#ff2f78;
      --no:#ffd6e7;
      --card:#ffffffcc;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      background: radial-gradient(900px 500px at 20% 10%, var(--bg2), transparent 70%),
                  radial-gradient(900px 500px at 80% 30%, #ffeef7, transparent 70%),
                  linear-gradient(180deg, var(--bg1), #fff);
      min-height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:18px;
      color:var(--text);
      overflow:hidden;
    }
    .card{
      width:min(720px, 96vw);
      background: var(--card);
      border:1px solid #ffd1e3;
      border-radius: 24px;
      box-shadow: 0 20px 60px rgba(255, 77, 141, 0.18);
      padding: 22px 20px 18px;
      position:relative;
    }
    h1{
      margin: 6px 0 6px;
      font-size: clamp(22px, 3.2vw, 34px);
      line-height:1.15;
      text-align:center;
      color:#b1005a;
    }
    .sub{
      text-align:center;
      margin: 0 auto 14px;
      color: var(--muted);
      font-size: 14px;
    }
    .arena{
      position:relative;
      height: 260px;
      border-radius: 18px;
      background: linear-gradient(180deg, #fff, #fff7fb);
      border: 1px dashed #ffc1d7;
      overflow:hidden;
    }
    .btn{
      position:absolute;
      border:0;
      border-radius: 999px;
      padding: 14px 22px;
      font-weight:800;
      cursor:pointer;
      user-select:none;
      transition: transform .12s ease, box-shadow .12s ease, filter .12s ease;
      box-shadow: 0 12px 22px rgba(0,0,0,0.08);
      letter-spacing: .3px;
    }
    .btn:active{ transform: scale(0.98); }
    #yesBtn{
      background: var(--yes);
      color: white;
      font-size: 18px;
      left: 34%;
      top: 62%;
      transform: translate(-50%, -50%);
    }
    #yesBtn:hover{ background: var(--yesHover); }
    #noBtn{
      background: var(--no);
      color: var(--muted);
      font-size: 16px;
      left: 66%;
      top: 62%;
      transform: translate(-50%, -50%);
    }
    .footer{
      margin-top: 12px;
      font-size: 12px;
      color: #8c3a63;
      text-align:center;
      opacity:0.9;
    }

    /* Modal */
    .overlay{
      position:fixed;
      inset:0;
      background: rgba(30, 0, 18, 0.35);
      display:none;
      align-items:center;
      justify-content:center;
      padding:18px;
      z-index:50;
    }
    .modal{
      width:min(680px, 96vw);
      background:white;
      border-radius: 24px;
      padding: 22px 18px 16px;
      border:1px solid #ffd1e3;
      box-shadow: 0 30px 80px rgba(0,0,0,0.22);
      text-align:center;
      position:relative;
      overflow:hidden;
    }
    .modal h2{
      margin: 0 0 8px;
      color:#b1005a;
      font-size: clamp(22px, 3vw, 34px);
    }
    .modal p{
      margin: 0 auto;
      color: var(--muted);
      font-size: 15px;
      line-height: 1.5;
      max-width: 52ch;
      white-space: pre-line;
    }
    .modal .actions{
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
      font-weight:800;
      cursor:pointer;
      box-shadow: 0 10px 18px rgba(0,0,0,0.08);
    }
    .pink{ background: var(--yes); color:white; }
    .soft{ background: var(--no); color: var(--muted); }

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
      opacity:0.95;
      animation: fall linear forwards;
    }
    @keyframes fall{
      from { transform: translateY(-30px) rotate(0deg); }
      to   { transform: translateY(520px) rotate(680deg); }
    }
  </style>
</head>

<body>
  <div class="card">
    <h1>Disna (Baju), will you be my Valentine? 💘</h1>
    <div class="sub" id="subtitle">Choose wisely 😌</div>

    <div class="arena" id="arena">
      <button class="btn" id="yesBtn">YES 💖</button>
      <button class="btn" id="noBtn">NO 🙃</button>
    </div>

    <div class="footer">P.S. Clicking NO has consequences 😈</div>
  </div>

  <div class="overlay" id="overlay">
    <div class="modal" role="dialog" aria-modal="true">
      <div class="confetti" id="confetti"></div>
      <h2>YAYYYY DISNA!!! 💞</h2>
      <p id="modalText">
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

      // margins so it stays visible
      const margin = 18;

      const maxX = a.width - b.width - margin;
      const maxY = a.height - b.height - margin;

      const x = clamp(Math.random() * maxX + margin/2, margin/2, maxX + margin/2);
      const y = clamp(Math.random() * maxY + margin/2, margin/2, maxY + margin/2);

      noBtn.style.left = `${x}px`;
      noBtn.style.top  = `${y}px`;
      noBtn.style.transform = "translate(0, 0)";
    }

    function growYesButton() {
      yesScale = Math.min(2.8, yesScale + 0.18);
      yesBtn.style.transform = `translate(-50%, -50%) scale(${yesScale})`;
      yesBtn.style.boxShadow = `0 14px 28px rgba(255, 77, 141, ${0.18 + yesScale*0.08})`;
    }

    function makeConfetti() {
      confetti.innerHTML = "";
      const pieces = 120;
      for (let i=0; i<pieces; i++){
        const p = document.createElement("div");
        p.className = "piece";
        const left = Math.random()*100;
        const dur = 1.8 + Math.random()*1.6;
        const delay = Math.random()*0.25;

        // random-ish pastel colors (no external libs)
        const hue = Math.floor(330 + Math.random()*60) % 360; // pink-ish range
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
      yesBtn.style.boxShadow = "0 12px 22px rgba(0,0,0,0.08)";

      // reset NO to default position
      noBtn.style.left = "66%";
      noBtn.style.top = "62%";
      noBtn.style.transform = "translate(-50%, -50%)";
    }

    // Make NO run away when clicked
    noBtn.addEventListener("click", () => {
      noClicks += 1;
      subtitle.textContent = lines[Math.min(noClicks - 1, lines.length - 1)];
      growYesButton();
      moveNoButton();
    });

    // Also make NO dodge when hovered/touched (extra effective on desktop)
    noBtn.addEventListener("mouseenter", () => {
      if (noClicks >= 1) moveNoButton();
    });

    // YES opens celebration
    yesBtn.addEventListener("click", () => {
      openModal();
    });

    replayBtn.addEventListener("click", () => {
      closeModal();
      reset();
    });

    closeBtn.addEventListener("click", () => {
      closeModal();
    });

    // If window resizes, keep NO inside arena
    window.addEventListener("resize", () => {
      if (noClicks >= 1) moveNoButton();
    });
  </script>
</body>
</html>
