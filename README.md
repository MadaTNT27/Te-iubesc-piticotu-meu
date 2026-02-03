# Te-iubesc-piticotu-meu
<!doctype html>
<html lang="ro">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Pentru piticotu' meu 💖</title>
  <style>
    :root{
      --pink:#ffd4e6;
      --deep:#ff2f74;
      font-family:"Poppins", system-ui, Arial;
    }
    html,body{height:100%;margin:0}
    body{
      background:linear-gradient(180deg,var(--pink),#ffe6f2,#fff);
      display:flex;align-items:center;justify-content:center;
      padding:16px;overflow:hidden
    }
    .card{
      max-width:900px;width:100%;background:rgba(255,255,255,.92);
      border-radius:22px;box-shadow:0 20px 50px rgba(255,90,150,.25);
      padding:28px 22px 36px;text-align:center;z-index:2
    }
    h1{font-size:22px;color:#6b1738}
    p{font-size:17px;color:#421427;line-height:1.55}
    .love-text{font-size:19px;font-weight:700;color:var(--deep)}
    .date{margin-top:10px;font-weight:600;color:#a01846}

    .heart-beat{
      margin:18px auto;width:40px;height:40px;background:var(--deep);
      transform:rotate(-45deg);animation:beat 1s infinite
    }
    .heart-beat:before,.heart-beat:after{
      content:"";position:absolute;width:40px;height:40px;background:var(--deep);
      border-radius:50%
    }
    .heart-beat:before{top:-20px;left:0}
    .heart-beat:after{left:20px;top:0}

    @keyframes beat{0%,100%{transform:rotate(-45deg) scale(1)}50%{transform:rotate(-45deg) scale(1.25)}}

    .question-btn{
      margin-top:26px;padding:14px 22px;border:none;border-radius:30px;
      background:var(--deep);color:#fff;font-size:16px;cursor:pointer
    }

    .overlay{position:fixed;inset:0;background:rgba(0,0,0,.35);display:none;align-items:center;justify-content:center;z-index:10}
    .popup{background:#fff;border-radius:22px;padding:26px 22px;text-align:center;max-width:320px;width:90%}
    .answers{display:flex;gap:12px;margin-top:16px}
    .answers button{flex:1;padding:12px;border:none;border-radius:20px;font-size:15px;cursor:pointer}
    .yes{background:var(--deep);color:#fff}
    .no{background:#ddd;color:#555}

    .final{position:fixed;inset:0;background:linear-gradient(180deg,#ffd4e6,#fff);display:none;align-items:center;justify-content:center;flex-direction:column;z-index:20;overflow:hidden}
    .final h1{font-size:42px;color:var(--deep);animation:beat 1.2s infinite}

    .hearts{position:absolute;inset:0;pointer-events:none}
    .fall-heart{position:absolute;width:26px;height:26px;background:var(--deep);transform:rotate(-45deg);animation:fall linear forwards}
    .fall-heart:before,.fall-heart:after{content:"";position:absolute;width:26px;height:26px;background:var(--deep);border-radius:50%}
    .fall-heart:before{top:-13px}
    .fall-heart:after{left:13px}
    @keyframes fall{from{top:-10%}to{top:110%}}

    .signature{position:fixed;right:14px;bottom:12px;font-size:14px;color:#6b1738}

    .music-btn{position:fixed;left:14px;bottom:14px;background:var(--deep);color:#fff;border:none;border-radius:20px;padding:10px 16px;cursor:pointer;z-index:30}

    @media(max-width:600px){h1{font-size:18px}.final h1{font-size:32px}}
  </style>
</head>
<body>

<div class="card">
  <h1>Pentru piticotu' meu 💕</h1>
  <p>"Sunt cel mai norocos băiețel pentru că am o iubită atât de perfectă, îi mulțumesc lui Dumnezeu că ai apărut în viața mea și că fiecare zi petrecută alături de tine e una de vis."</p>
  <p class="love-text">Te ador și te iubesc cel mai mult, piticotu' meu 💖</p>
  <p style="margin-top:14px;font-size:16px;color:#5a1532;">
    Vreau să știi că <strong>voi fi mereu lângă tine</strong>, în zilele frumoase și în cele grele.
    Orice ar fi, eu sunt aici să te țin de mână, să te fac să zâmbești,
    să te fac să te simți <strong>iubită, apreciată și în siguranță</strong>.
    Fericirea ta e promisiunea mea și inima mea e acasă oriunde ești tu.
  </p>
  <div class="date">14 februarie ❤️</div>
  <div class="heart-beat"></div>
  <button class="question-btn" onclick="openPopup()">Am o întrebare pentru tine 💌</button>
</div>

<div class="overlay" id="overlay">
  <div class="popup">
    <h2>Vrei să petreci Ziua Îndrăgostiților cu mine? 💘</h2>
    <div class="answers">
      <button class="yes" onclick="yesAnswer()">DA 💖</button>
      <button class="no" id="noBtn">Nu 🙈</button>
    </div>
  </div>
</div>

<div class="final" id="final">
  <div class="hearts" id="hearts"></div>
  <h1>TE IUBESC ❤️</h1>
</div>

<div class="signature">Cu drag, nebunu' tău</div>

<iframe id="ytplayer" width="0" height="0" src="https://www.youtube.com/embed/SM-N4pmi73A?enablejsapi=1&loop=1&playlist=SM-N4pmi73A" allow="autoplay"></iframe>
<button class="music-btn" id="musicBtn">▶️ Play</button>

<script>
const overlay=document.getElementById('overlay');
const final=document.getElementById('final');
const hearts=document.getElementById('hearts');
function openPopup(){overlay.style.display='flex'}
function yesAnswer(){overlay.style.display='none';final.style.display='flex';startHearts()}

document.getElementById('noBtn').addEventListener('click',()=>{
  const btn=document.getElementById('noBtn');
  btn.style.position='absolute';
  btn.style.left=Math.random()*200+'px';
  btn.style.top=Math.random()*80+'px';
});

function startHearts(){setInterval(()=>{const h=document.createElement('div');h.className='fall-heart';h.style.left=Math.random()*100+'%';h.style.animationDuration=(Math.random()*3+4)+'s';hearts.appendChild(h);setTimeout(()=>h.remove(),8000)},180)}

let player,isPlaying=false;
function onYouTubeIframeAPIReady(){player=new YT.Player('ytplayer')}
const tag=document.createElement('script');tag.src="https://www.youtube.com/iframe_api";document.body.appendChild(tag);
const btn=document.getElementById('musicBtn');
btn.onclick=()=>{if(player){if(!isPlaying){player.playVideo();btn.textContent='⏸ Pauză'}else{player.pauseVideo();btn.textContent='▶️ Play'}isPlaying=!isPlaying}}
</script>
</body>
</html>
