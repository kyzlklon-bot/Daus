<!DOCTYPE html>
<html lang="kk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Nova</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Unbounded:wght@500;700;900&family=Manrope:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --void:#0a0607;
    --void-2:#160a0c;
    --gold:#ffb648;
    --ember:#ff6a35;
    --magenta:#ff2e88;
    --core-deep:#c81d4f;
    --text:#fbe9dc;
    --text-dim:#a3897f;
    --line:rgba(255,182,72,0.14);
  }
  *{box-sizing:border-box; -webkit-tap-highlight-color:transparent;}
  html,body{
    margin:0; padding:0; height:100%; overflow:hidden;
    background:
      radial-gradient(90% 60% at 50% 100%, rgba(200,29,79,0.18) 0%, transparent 60%),
      radial-gradient(70% 50% at 50% 0%, var(--void-2) 0%, var(--void) 55%);
    font-family:'Manrope',system-ui,sans-serif;
    color:var(--text);
    -webkit-user-select:none; user-select:none;
  }
  #app{ position:relative; width:100%; height:100dvh; display:flex; flex-direction:column; }

  /* film grain overlay for warmth */
  .grain{
    position:fixed; inset:0; pointer-events:none; z-index:1; opacity:0.05; mix-blend-mode:overlay;
    background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='120'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  }

  /* Top bar */
  .topbar{
    display:flex; align-items:flex-start; justify-content:space-between;
    padding:20px 22px 6px; z-index:5;
  }
  .brand{ line-height:1; }
  .brand .word{
    font-family:'Unbounded',sans-serif; font-weight:900; font-size:20px; letter-spacing:0.02em;
    background:linear-gradient(100deg,var(--gold),var(--ember) 55%,var(--magenta));
    -webkit-background-clip:text; background-clip:text; color:transparent;
  }
  .brand .sub{
    display:block; margin-top:3px; font-size:10.5px; letter-spacing:0.16em; text-transform:uppercase;
    color:var(--text-dim); font-weight:600;
  }

  /* Edge tab (opens settings) */
  .edge-tab{
    position:fixed; right:0; top:50%; transform:translateY(-50%);
    width:22px; height:84px; border-radius:14px 0 0 14px;
    background:linear-gradient(180deg, rgba(255,182,72,0.14), rgba(255,46,136,0.14));
    border:1px solid var(--line); border-right:none;
    display:flex; align-items:center; justify-content:center;
    color:var(--text-dim); font-size:13px; letter-spacing:0.05em;
    z-index:8; cursor:pointer;
  }
  .edge-tab .glyph{ writing-mode:vertical-rl; transform:rotate(180deg); }

  /* Stage */
  .stage{ flex:1; position:relative; display:flex; align-items:center; justify-content:center; z-index:2;}
  canvas#flare{ width:min(86vw,380px); height:min(86vw,380px); }

  .status{
    position:absolute; bottom:10px; left:0; right:0; text-align:center;
    font-size:12.5px; color:var(--text-dim); letter-spacing:0.06em; text-transform:uppercase; font-weight:600;
    padding:0 24px; min-height:18px;
  }

  /* Transcript */
  .transcript{
    position:absolute; top:9%; left:0; right:0; padding:0 30px; text-align:center;
    font-size:18px; line-height:1.5; color:var(--text); font-weight:500;
    max-height:30%; overflow:hidden;
    opacity:0; transform:translateY(-6px);
    transition:opacity .3s ease, transform .3s ease;
    pointer-events:none;
  }
  .transcript.show{opacity:1; transform:translateY(0);}
  .transcript .you{
    color:var(--gold); font-size:10.5px; display:block; margin-bottom:8px;
    letter-spacing:0.18em; text-transform:uppercase; font-weight:700; font-family:'Unbounded',sans-serif;
  }

  /* Bottom controls */
  .controls{
    padding:8px 24px calc(30px + env(safe-area-inset-bottom));
    display:flex; align-items:center; justify-content:center; gap:28px;
    z-index:5;
  }
  .side-btn{
    width:44px;height:44px;border-radius:13px;
    background:rgba(255,182,72,0.05); border:1px solid var(--line);
    color:var(--text-dim); display:flex;align-items:center;justify-content:center;
    font-size:16px; cursor:pointer; transition:all .2s ease;
  }
  .side-btn:active{transform:scale(0.92);}
  .side-btn.active{ color:var(--magenta); border-color:rgba(255,46,136,0.5); background:rgba(255,46,136,0.1);}

  .mic-btn{
    width:80px; height:80px; border-radius:50%; border:2px solid transparent; cursor:pointer;
    background:
      linear-gradient(var(--void),var(--void)) padding-box,
      linear-gradient(140deg,var(--gold),var(--ember),var(--magenta)) border-box;
    display:flex; align-items:center; justify-content:center;
    color:var(--gold); font-size:26px; position:relative;
    transition:transform .15s ease;
    box-shadow:0 0 24px -6px rgba(255,106,53,0.55);
  }
  .mic-btn:active{transform:scale(0.94);}
  .mic-btn.listening{
    color:var(--magenta);
    animation:flarePulse 1.3s ease-out infinite;
  }
  .mic-btn.disabled{opacity:0.35; pointer-events:none;}
  @keyframes flarePulse{
    0%{box-shadow:0 0 24px -6px rgba(255,46,136,0.6);}
    70%{box-shadow:0 0 0 20px rgba(255,46,136,0), 0 0 24px -6px rgba(255,46,136,0.6);}
    100%{box-shadow:0 0 0 0 rgba(255,46,136,0), 0 0 24px -6px rgba(255,46,136,0.6);}
  }

  /* Settings sheet */
  .sheet-backdrop{
    position:fixed; inset:0; background:rgba(6,3,4,0.72); backdrop-filter:blur(3px);
    opacity:0; pointer-events:none; transition:opacity .25s ease; z-index:20;
  }
  .sheet-backdrop.show{opacity:1; pointer-events:auto;}
  .sheet{
    position:fixed; left:0; right:0; bottom:0; z-index:21;
    background:linear-gradient(180deg,#1b0e10,#0d0607);
    border-top:1px solid var(--line);
    border-radius:24px 24px 0 0;
    padding:20px 22px calc(24px + env(safe-area-inset-bottom));
    transform:translateY(105%); transition:transform .3s ease;
    max-height:80vh; overflow-y:auto;
  }
  .sheet.show{transform:translateY(0);}
  .sheet h3{
    margin:0 0 16px; font-size:13px; letter-spacing:0.14em; color:var(--gold);
    text-transform:uppercase; font-family:'Unbounded',sans-serif; font-weight:700;
  }
  .sheet label{font-size:12.5px; color:var(--text-dim); display:block; margin:14px 0 6px; font-weight:600;}
  .sheet input, .sheet select, .sheet textarea{
    width:100%; padding:12px 14px; border-radius:12px; border:1px solid var(--line);
    background:rgba(255,182,72,0.04); color:var(--text); font-size:14px; outline:none;
    font-family:'Manrope',sans-serif;
  }
  .sheet input:focus, .sheet select:focus, .sheet textarea:focus{border-color:var(--ember);}
  .sheet .save{
    margin-top:20px; width:100%; padding:14px; border-radius:12px; border:none;
    background:linear-gradient(100deg,var(--gold),var(--ember)); color:#1a0a05; font-size:14.5px;
    font-weight:700; cursor:pointer; font-family:'Unbounded',sans-serif; letter-spacing:0.02em;
  }
  .sheet .closebar{width:36px;height:4px;background:rgba(255,182,72,0.2);border-radius:2px;margin:0 auto 14px;}

  /* PIN lock screen */
  #lockScreen{
    position:fixed; inset:0; z-index:50;
    background:
      radial-gradient(90% 60% at 50% 100%, rgba(200,29,79,0.18) 0%, transparent 60%),
      radial-gradient(70% 50% at 50% 0%, var(--void-2) 0%, var(--void) 55%);
    display:flex; flex-direction:column; align-items:center; justify-content:center; gap:22px;
    padding:24px;
  }
  #lockScreen .word{
    font-family:'Unbounded',sans-serif; font-weight:900; font-size:26px; letter-spacing:0.02em;
    background:linear-gradient(100deg,var(--gold),var(--ember) 55%,var(--magenta));
    -webkit-background-clip:text; background-clip:text; color:transparent;
  }
  .pin-dots{ display:flex; gap:12px; }
  .pin-dots span{
    width:12px; height:12px; border-radius:50%; border:1.5px solid var(--line);
    background:transparent; transition:all .15s ease;
  }
  .pin-dots span.filled{ background:linear-gradient(140deg,var(--gold),var(--magenta)); border-color:transparent; }
  #pinInput{
    position:absolute; opacity:0; width:1px; height:1px;
  }
  .pin-hint{ font-size:12.5px; color:var(--text-dim); letter-spacing:0.04em; min-height:16px; }
  .pin-error{ color:var(--magenta); }
</style>
</head>
<body>
<div class="grain"></div>

<div id="lockScreen" style="display:none;">
  <div class="word">NOVA</div>
  <div class="pin-dots" id="pinDots"></div>
  <div class="pin-hint" id="pinHint">8 санды PIN кодты енгізіңіз</div>
  <input type="tel" id="pinInput" inputmode="numeric" maxlength="8" autocomplete="off">
</div>

<div id="app">
  <div class="topbar">
    <div class="brand">
      <span class="word">NOVA</span>
      <span class="sub">дауыстық көмекші</span>
    </div>
  </div>

  <div class="stage">
    <div class="transcript" id="transcript"></div>
    <canvas id="flare" width="700" height="700"></canvas>
  </div>

  <div class="status" id="status">түртіп сөйлеңіз</div>

  <div class="controls">
    <div class="side-btn" id="stopBtn" title="Тоқтату">■</div>
    <button class="mic-btn" id="micBtn">🎙</button>
    <div class="side-btn" id="muteBtn" title="Дауыссыз">🔊</div>
  </div>
</div>

<div class="edge-tab" id="settingsBtn"><span class="glyph">БАПТАУ ⚙</span></div>

<div class="sheet-backdrop" id="sheetBackdrop"></div>
<div class="sheet" id="sheet">
  <div class="closebar"></div>
  <h3>Баптаулар</h3>
  <label>Claude API кілті</label>
  <input type="password" id="apiKeyInput" placeholder="sk-ant-...">
  <label>Тану тілі</label>
  <select id="langSelect">
    <option value="kk-KZ">Қазақша</option>
    <option value="ru-RU">Орысша</option>
    <option value="en-US">English</option>
  </select>
  <label>Контактар (әр жолда: Аты:Нөмір, мыс. Айдос:+77011234567)</label>
  <textarea id="contactsInput" rows="4" placeholder="Айдос:+77011234567&#10;Анна:+77027654321"></textarea>
  <label>Кіру PIN коды (8 сан, бос қалдырсаңыз — құлыпсыз)</label>
  <input type="tel" id="pinSetInput" inputmode="numeric" maxlength="8" placeholder="••••••••">
  <button class="save" id="saveSettings">Сақтау</button>
</div>

<script>
(function(){
  // ---------- State ----------
  const state = {
    apiKey: localStorage.getItem('nova_api_key') || '',
    lang: localStorage.getItem('nova_lang') || 'kk-KZ',
    muted: localStorage.getItem('nova_muted') === '1',
    contacts: localStorage.getItem('nova_contacts') || '',
    pin: localStorage.getItem('nova_pin') || '',
    mode: 'idle', // idle | listening | thinking | speaking
    history: []
  };

  document.getElementById('apiKeyInput').value = state.apiKey;
  document.getElementById('langSelect').value = state.lang;
  document.getElementById('contactsInput').value = state.contacts;
  document.getElementById('pinSetInput').value = state.pin;
  updateMuteIcon();

  // numeric-only enforcement on the PIN setting field
  document.getElementById('pinSetInput').addEventListener('input', function(e){
    e.target.value = e.target.value.replace(/\D/g,'').slice(0,8);
  });

  // ---------- PIN lock screen ----------
  const lockScreen = document.getElementById('lockScreen');
  const pinInput = document.getElementById('pinInput');
  const pinDots = document.getElementById('pinDots');
  const pinHint = document.getElementById('pinHint');
  const appEl = document.getElementById('app');
  const edgeTabEl = document.getElementById('settingsBtn');

  function renderPinDots(len){
    pinDots.innerHTML = '';
    for(let i=0;i<8;i++){
      const d = document.createElement('span');
      if(i<len) d.classList.add('filled');
      pinDots.appendChild(d);
    }
  }

  function showLock(){
    appEl.style.visibility = 'hidden';
    edgeTabEl.style.visibility = 'hidden';
    lockScreen.style.display = 'flex';
    renderPinDots(0);
    pinInput.value = '';
    setTimeout(()=>pinInput.focus(), 50);
  }
  function unlock(){
    lockScreen.style.display = 'none';
    appEl.style.visibility = 'visible';
    edgeTabEl.style.visibility = 'visible';
  }

  lockScreen.addEventListener('click', ()=>pinInput.focus());
  pinInput.addEventListener('input', function(){
    pinInput.value = pinInput.value.replace(/\D/g,'').slice(0,8);
    renderPinDots(pinInput.value.length);
    pinHint.classList.remove('pin-error');
    pinHint.textContent = '8 санды PIN кодты енгізіңіз';
    if(pinInput.value.length === 8){
      if(pinInput.value === state.pin){
        unlock();
      } else {
        pinHint.textContent = 'қате PIN, қайталап көріңіз';
        pinHint.classList.add('pin-error');
        setTimeout(()=>{ pinInput.value=''; renderPinDots(0); }, 500);
      }
    }
  });

  if(state.pin && state.pin.length === 8){ showLock(); }

  // ---------- Elements ----------
  const micBtn = document.getElementById('micBtn');
  const stopBtn = document.getElementById('stopBtn');
  const muteBtn = document.getElementById('muteBtn');
  const statusEl = document.getElementById('status');
  const transcriptEl = document.getElementById('transcript');
  const settingsBtn = document.getElementById('settingsBtn');
  const sheet = document.getElementById('sheet');
  const sheetBackdrop = document.getElementById('sheetBackdrop');

  // ---------- Settings sheet ----------
  function openSheet(){ sheet.classList.add('show'); sheetBackdrop.classList.add('show'); }
  function closeSheet(){ sheet.classList.remove('show'); sheetBackdrop.classList.remove('show'); }
  settingsBtn.onclick = openSheet;
  sheetBackdrop.onclick = closeSheet;
  document.getElementById('saveSettings').onclick = function(){
    const pinVal = document.getElementById('pinSetInput').value.trim();
    if(pinVal && pinVal.length !== 8){
      setStatus('PIN дәл 8 саннан тұруы керек');
      return;
    }
    state.apiKey = document.getElementById('apiKeyInput').value.trim();
    state.lang = document.getElementById('langSelect').value;
    state.contacts = document.getElementById('contactsInput').value.trim();
    state.pin = pinVal;
    localStorage.setItem('nova_api_key', state.apiKey);
    localStorage.setItem('nova_lang', state.lang);
    localStorage.setItem('nova_contacts', state.contacts);
    localStorage.setItem('nova_pin', state.pin);
    closeSheet();
    setStatus(state.apiKey ? 'дайын' : 'API кілтін енгізіңіз');
  };

  function updateMuteIcon(){
    muteBtn.textContent = state.muted ? '🔇' : '🔊';
    muteBtn.classList.toggle('active', state.muted);
  }
  muteBtn.onclick = function(){
    state.muted = !state.muted;
    localStorage.setItem('nova_muted', state.muted ? '1':'0');
    updateMuteIcon();
    if(state.muted && window.speechSynthesis) speechSynthesis.cancel();
  };

  // ---------- Corona / Solar-flare Visualizer ----------
  const canvas = document.getElementById('flare');
  const ctx = canvas.getContext('2d');
  const DPR = Math.min(window.devicePixelRatio||1, 2);
  function fitCanvas(){
    const size = canvas.clientWidth;
    canvas.width = size*DPR; canvas.height = size*DPR;
    ctx.setTransform(DPR,0,0,DPR,0,0);
  }
  window.addEventListener('resize', fitCanvas);

  const RAYS = 42;
  const rays = [];
  for(let i=0;i<RAYS;i++){
    rays.push({
      angle: (i/RAYS)*Math.PI*2,
      phase: Math.random()*Math.PI*2,
      speed: 0.5 + Math.random()*1.1,
      lenJitter: 0.6 + Math.random()*0.8
    });
  }

  let embers = [];
  let level = 0, targetLevel = 0.1;
  let spin = 0;

  const palette = {
    idle:      { core:['#ffe6b0','#ff9d4d'], ray:'#ffb648', speed:0.35 },
    listening: { core:['#ffd0e8','#ff2e88'], ray:'#ff2e88', speed:1.1 },
    thinking:  { core:['#ffe0b0','#ff6a35'], ray:'#ff6a35', speed:1.8 },
    speaking:  { core:['#fff2d8','#ffb648'], ray:'#ffdd88', speed:1.4 }
  };

  function lerp(a,b,t){return a+(b-a)*t;}

  function draw(){
    const size = canvas.clientWidth;
    const cx = size/2, cy = size/2;
    ctx.clearRect(0,0,size,size);

    level += (targetLevel - level) * 0.09;
    const P = palette[state.mode] || palette.idle;
    const t = Date.now()*0.001;
    spin += 0.0018 * P.speed;

    // ambient void glow
    const glow = ctx.createRadialGradient(cx,cy,0,cx,cy,size*0.6);
    glow.addColorStop(0, 'rgba(255,106,53,0.14)');
    glow.addColorStop(1, 'rgba(255,106,53,0)');
    ctx.fillStyle = glow;
    ctx.fillRect(0,0,size,size);

    const baseR = size*0.15;
    const outerR = size*0.15 + level*size*0.16;

    // corona rays (flare spikes)
    for(const r of rays){
      const a = r.angle + spin;
      const wob = 1 + Math.sin(t*r.speed*P.speed + r.phase)*0.35*r.lenJitter;
      const len = outerR + (outerR*0.9*wob*(0.4+level*1.1));
      const x1 = cx + Math.cos(a)*baseR*0.9;
      const y1 = cy + Math.sin(a)*baseR*0.9;
      const x2 = cx + Math.cos(a)*len;
      const y2 = cy + Math.sin(a)*len;
      const grad = ctx.createLinearGradient(x1,y1,x2,y2);
      grad.addColorStop(0, P.ray+'cc');
      grad.addColorStop(1, P.ray+'00');
      ctx.strokeStyle = grad;
      ctx.lineWidth = lerp(1.2,3,level) * (0.6+wob*0.4);
      ctx.beginPath();
      ctx.moveTo(x1,y1);
      ctx.lineTo(x2,y2);
      ctx.stroke();
    }

    // embers rising from corona edge
    if(Math.random() < 0.35 + level*0.4){
      const a = Math.random()*Math.PI*2;
      embers.push({
        x: cx + Math.cos(a)*baseR,
        y: cy + Math.sin(a)*baseR,
        vx: Math.cos(a)*0.3 + (Math.random()-0.5)*0.4,
        vy: Math.sin(a)*0.3 - 0.4 - Math.random()*0.5,
        life: 1,
        r: 1 + Math.random()*1.8
      });
    }
    embers.forEach(e=>{
      e.x += e.vx; e.y += e.vy; e.vy -= 0.002; e.life -= 0.012;
    });
    embers = embers.filter(e=>e.life>0);
    embers.forEach(e=>{
      ctx.globalAlpha = Math.max(e.life,0);
      ctx.fillStyle = P.ray;
      ctx.beginPath();
      ctx.arc(e.x,e.y,e.r,0,Math.PI*2);
      ctx.fill();
    });
    ctx.globalAlpha = 1;

    // molten core disc
    const coreR = baseR * (0.85 + level*0.25);
    const coreGrad = ctx.createRadialGradient(cx,cy,0,cx,cy,coreR);
    coreGrad.addColorStop(0, P.core[0]);
    coreGrad.addColorStop(0.55, P.core[1]);
    coreGrad.addColorStop(1, P.core[1]+'00');
    ctx.fillStyle = coreGrad;
    ctx.beginPath();
    ctx.arc(cx,cy,coreR,0,Math.PI*2);
    ctx.fill();

    // hot white center
    ctx.fillStyle = 'rgba(255,250,240,'+(0.55+level*0.4)+')';
    ctx.beginPath();
    ctx.arc(cx,cy,coreR*0.28,0,Math.PI*2);
    ctx.fill();

    requestAnimationFrame(draw);
  }
  fitCanvas();
  requestAnimationFrame(draw);

  function setMode(mode){
    state.mode = mode;
    if(mode==='idle') targetLevel = 0.1;
    if(mode==='thinking') targetLevel = 0.35;
  }

  function setStatus(text){ statusEl.textContent = text; }

  // ---------- Mic audio level (for listening visualizer) ----------
  let audioCtx, analyser, dataArray, micStream;
  async function startAudioMeter(){
    try{
      micStream = await navigator.mediaDevices.getUserMedia({audio:true});
      audioCtx = new (window.AudioContext||window.webkitAudioContext)();
      const src = audioCtx.createMediaStreamSource(micStream);
      analyser = audioCtx.createAnalyser();
      analyser.fftSize = 256;
      src.connect(analyser);
      dataArray = new Uint8Array(analyser.frequencyBinCount);
      meterLoop();
    }catch(e){ /* mic permission denied - fallback to fixed pulsing */ }
  }
  function meterLoop(){
    if(state.mode!=='listening'){ return; }
    analyser.getByteFrequencyData(dataArray);
    let sum=0; for(let i=0;i<dataArray.length;i++) sum+=dataArray[i];
    const avg = sum/dataArray.length/255;
    targetLevel = Math.min(1, 0.15 + avg*1.8);
    requestAnimationFrame(meterLoop);
  }
  function stopAudioMeter(){
    if(micStream){ micStream.getTracks().forEach(t=>t.stop()); micStream=null; }
    if(audioCtx){ audioCtx.close(); audioCtx=null; }
  }

  // ---------- Speech Recognition ----------
  const SR = window.SpeechRecognition || window.webkitSpeechRecognition;
  let recognizer = null;
  let recognizing = false;

  function buildRecognizer(){
    if(!SR) return null;
    const r = new SR();
    r.lang = state.lang;
    r.interimResults = true;
    r.continuous = false;
    r.onstart = function(){
      recognizing = true;
      setMode('listening');
      micBtn.classList.add('listening');
      setStatus('тыңдап тұрмын...');
      startAudioMeter();
    };
    r.onresult = function(e){
      let text = '';
      for(let i=0;i<e.results.length;i++) text += e.results[i][0].transcript;
      showTranscript('Сіз', text);
    };
    r.onerror = function(e){
      setStatus('қате: ' + (e.error||'белгісіз'));
    };
    r.onend = function(){
      recognizing = false;
      micBtn.classList.remove('listening');
      stopAudioMeter();
      const finalText = transcriptEl.dataset.lastText;
      if(finalText && finalText.trim()){
        handleUserSpeech(finalText.trim());
      } else {
        setMode('idle');
        setStatus('түртіп сөйлеңіз');
      }
    };
    return r;
  }

  function showTranscript(who, text){
    transcriptEl.innerHTML = '<span class="you">'+who+'</span>' + escapeHtml(text);
    transcriptEl.classList.add('show');
    transcriptEl.dataset.lastText = text;
  }
  function escapeHtml(s){
    return s.replace(/[&<>"']/g, c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
  }

  micBtn.onclick = function(){
    if(!state.apiKey){ openSheet(); setStatus('алдымен API кілтін енгізіңіз'); return; }
    if(!SR){ setStatus('браузер дауысты танымайды'); return; }
    if(recognizing){ recognizer && recognizer.stop(); return; }
    if(speechSynthesis.speaking) speechSynthesis.cancel();
    transcriptEl.classList.remove('show');
    recognizer = buildRecognizer();
    try{ recognizer.start(); }catch(e){ setStatus('микрофонды бастау мүмкін болмады'); }
  };

  stopBtn.onclick = function(){
    if(recognizing && recognizer) recognizer.stop();
    if(speechSynthesis.speaking) speechSynthesis.cancel();
    setMode('idle');
    setStatus('тоқтатылды');
  };

  // ---------- Claude API call ----------
  function buildSystemPrompt(){
    const contactsList = state.contacts
      ? state.contacts.split('\n').map(l=>l.trim()).filter(Boolean).join('; ')
      : '(контактар енгізілмеген)';
    return "Сенің атың Nova — Android телефондағы дауыстық көмекші. Сен пайдаланушының сөзін нақты әрекетке айналдырасың.\n"
      + "Белгілі контактар: " + contactsList + "\n\n"
      + "ЖАУАПТЫ ТЕК ЖӘНЕ ТЕК осы JSON пішінінде қайтар, басқа ешнәрсе жазба, markdown белгілерін (```) қолданба:\n"
      + '{"speak":"пайдаланушыға дауыстап айтылатын қысқа қазақша жауап","action":{"type":"whatsapp|call|sms|maps|search|url|alarm|none","number":"+7...","text":"...","query":"...","hour":0,"minute":0,"label":"..."}}\n\n'
      + "Ережелер:\n"
      + "- Егер контакт аты аталса, жоғарыдағы тізімнен нөмірін тап. Табылмаса action.type='none' қой және speak-те контакт табылмағанын айт.\n"
      + "- 'ватсапты аш' / контактке хабар жаз -> type:'whatsapp', number, text (text бос болуы мүмкін).\n"
      + "- қоңырау шал -> type:'call', number.\n"
      + "- смс жібер -> type:'sms', number, text.\n"
      + "- жол/карта көрсет -> type:'maps', query.\n"
      + "- интернеттен ізде -> type:'search', query.\n"
      + "- сайт аш -> type:'url', query (толық сілтеме).\n"
      + "- дабыл қой -> type:'alarm', hour, minute, label.\n"
      + "- бұл тек әңгіме/сұрақ болса, әрекет керек емес -> type:'none'.\n"
      + "- speak өрісі әрдайым дауыстап оқылады, сондықтан қысқа әрі табиғи сөйлесу тілінде бол, JSON синтаксисін дауыстап айтпа.";
  }

  async function handleUserSpeech(text){
    setMode('thinking');
    setStatus('ойлануда...');
    state.history.push({role:'user', content:text});
    try{
      const resp = await fetch('https://api.anthropic.com/v1/messages', {
        method:'POST',
        headers:{
          'Content-Type':'application/json',
          'x-api-key': state.apiKey,
          'anthropic-version':'2023-06-01',
          'anthropic-dangerous-direct-browser-access':'true'
        },
        body: JSON.stringify({
          model: 'claude-haiku-4-5-20251001',
          max_tokens: 400,
          system: buildSystemPrompt(),
          messages: state.history
        })
      });
      const data = await resp.json();
      let raw = '';
      if(data && data.content && data.content[0]) raw = data.content[0].text || '';
      if(!raw){
        const errMsg = (data.error && data.error.message) ? data.error.message : 'жауап алынбады';
        showTranscript('Nova', 'Қате: ' + errMsg);
        setStatus('қате');
        setMode('idle');
        return;
      }
      state.history.push({role:'assistant', content: raw});

      let parsed = null;
      try{ parsed = JSON.parse(raw.trim().replace(/^```json|```$/g,'').trim()); }catch(e){ parsed = null; }

      const speakText = parsed && parsed.speak ? parsed.speak : raw;
      showTranscript('Nova', speakText);
      speak(speakText);
      if(parsed && parsed.action && parsed.action.type && parsed.action.type !== 'none'){
        executeAction(parsed.action);
      }
    }catch(e){
      setStatus('желі қатесі');
      setMode('idle');
    }
  }

  // ---------- Action execution (Android intents / web) ----------
  function executeAction(action){
    try{
      const num = (action.number||'').replace(/[^\d+]/g,'');
      let url = null;
      switch(action.type){
        case 'whatsapp':
          url = num
            ? 'https://wa.me/' + num.replace('+','') + (action.text ? '?text=' + encodeURIComponent(action.text) : '')
            : 'https://wa.me/';
          break;
        case 'call':
          url = 'tel:' + num;
          break;
        case 'sms':
          url = 'sms:' + num + (action.text ? '?body=' + encodeURIComponent(action.text) : '');
          break;
        case 'maps':
          url = 'https://www.google.com/maps/search/?api=1&query=' + encodeURIComponent(action.query||'');
          break;
        case 'search':
          url = 'https://www.google.com/search?q=' + encodeURIComponent(action.query||'');
          break;
        case 'url':
          url = action.query || action.text || null;
          break;
        case 'alarm':
          url = 'intent:#Intent;action=android.intent.action.SET_ALARM;i.android.intent.extra.alarm.HOUR='
            + (action.hour||0) + ';i.android.intent.extra.alarm.MINUTES=' + (action.minute||0)
            + ';S.android.intent.extra.alarm.MESSAGE=' + encodeURIComponent(action.label||'Nova') + ';end';
          break;
      }
      if(url) setTimeout(()=>{ window.location.href = url; }, 400);
    }catch(e){ /* silently ignore malformed actions */ }
  }

  function speak(text){
    setMode('speaking');
    setStatus('сөйлеп тұр...');
    if(state.muted || !window.speechSynthesis){
      setTimeout(()=>{ setMode('idle'); setStatus('түртіп сөйлеңіз'); }, 600);
      return;
    }
    const utter = new SpeechSynthesisUtterance(text);
    utter.lang = state.lang;
    utter.rate = 1.02;
    utter.onstart = function(){
      speakPulse();
    };
    utter.onend = function(){
      setMode('idle');
      setStatus('түртіп сөйлеңіз');
    };
    utter.onerror = function(){
      setMode('idle');
      setStatus('түртіп сөйлеңіз');
    };
    speechSynthesis.cancel();
    speechSynthesis.speak(utter);
  }

  let speakT = 0;
  function speakPulse(){
    if(state.mode!=='speaking') return;
    speakT += 0.35;
    const wave = (Math.sin(speakT) + Math.sin(speakT*1.7)*0.6) / 1.6;
    targetLevel = 0.35 + (wave*0.5+0.5) * 0.5 + Math.random()*0.08;
    setTimeout(speakPulse, 70);
  }

  // init status
  setStatus(state.apiKey ? 'түртіп сөйлеңіз' : 'алдымен API кілтін енгізіңіз');
  if(!SR){ setStatus('бұл браузерде дауысты тану қолдау таппайды'); micBtn.classList.add('disabled'); }
})();
</script>
</body>
</html>
