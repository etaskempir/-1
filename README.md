# -1
<html lang="kk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Компьютерлік графика — Интеллектуалды оқу құралы</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap');

  :root {
    --bg: #0b0f19;
    --bg2: #111827;
    --card: #1a2234;
    --card-hover: #243049;
    --border: #2d3a52;
    --text: #e8eef7;
    --muted: #94a3b8;
    --primary: #7c5cfc;
    --primary2: #a78bfa;
    --accent: #22d3ee;
    --success: #34d399;
    --warning: #fbbf24;
    --danger: #f87171;
    --gradient: linear-gradient(135deg, #7c5cfc, #22d3ee);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Inter', system-ui, sans-serif;
    background: var(--bg);
    color: var(--text);
    line-height: 1.65;
    min-height: 100vh;
  }

  header {
    background: rgba(11, 15, 25, 0.85);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid var(--border);
    padding: 0.9rem 1.5rem;
    position: sticky;
    top: 0;
    z-index: 100;
  }
  .header-inner {
    max-width: 1100px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 1rem;
    flex-wrap: wrap;
  }
  .logo {
    font-size: 1.25rem;
    font-weight: 800;
    background: var(--gradient);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    letter-spacing: -0.03em;
  }
  nav {
    display: flex;
    flex-wrap: wrap;
    gap: 0.35rem;
  }
  nav button {
    background: transparent;
    border: 1px solid transparent;
    color: var(--muted);
    padding: 0.45rem 0.85rem;
    border-radius: 10px;
    cursor: pointer;
    font-size: 0.88rem;
    font-weight: 500;
    transition: all 0.2s;
  }
  nav button:hover {
    color: var(--text);
    background: var(--card);
  }
  nav button.active {
    background: var(--primary);
    color: white;
    border-color: var(--primary);
    box-shadow: 0 0 20px rgba(124, 92, 252, 0.35);
  }

  main {
    max-width: 1100px;
    margin: 0 auto;
    padding: 2rem 1.4rem 4rem;
  }
  .section { display: none; animation: fadeUp 0.4s ease; }
  .section.active { display: block; }
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(12px); }
    to { opacity: 1; transform: translateY(0); }
  }

  h1 {
    font-size: 1.9rem;
    font-weight: 800;
    margin-bottom: 0.6rem;
    letter-spacing: -0.03em;
  }
  h2 {
    font-size: 1.35rem;
    font-weight: 700;
    margin: 1.8rem 0 0.7rem;
    color: var(--primary2);
  }
  h3 {
    font-size: 1.1rem;
    font-weight: 600;
    margin: 1.2rem 0 0.5rem;
    color: var(--accent);
  }
  p, li { margin-bottom: 0.55rem; color: var(--muted); }
  ul, ol { padding-left: 1.3rem; margin-bottom: 0.9rem; }
  strong { color: var(--text); }

  .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 1.4rem 1.5rem;
    margin-bottom: 1.1rem;
    transition: border-color 0.2s;
  }
  .card:hover { border-color: #3d4f6f; }

  .hero {
    background: linear-gradient(145deg, #1a1440, #0f2a3d);
    border: 1px solid #2d3a52;
    border-radius: 20px;
    padding: 2.8rem 2rem;
    margin-bottom: 2rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle, rgba(124,92,252,0.12) 0%, transparent 60%);
    pointer-events: none;
  }
  .hero h1 {
    font-size: 2.3rem;
    background: var(--gradient);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    margin-bottom: 0.6rem;
  }
  .hero p {
    color: var(--muted);
    max-width: 520px;
    margin: 0 auto;
    font-size: 1.05rem;
  }

  .grid-2 {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 1rem;
  }
  .topic-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 1.3rem;
    cursor: pointer;
    transition: all 0.25s;
  }
  .topic-card:hover {
    background: var(--card-hover);
    border-color: var(--primary);
    transform: translateY(-4px);
    box-shadow: 0 12px 30px rgba(124, 92, 252, 0.15);
  }
  .topic-card h3 { margin-top: 0.3rem; color: var(--text); }
  .badge {
    display: inline-block;
    background: rgba(124, 92, 252, 0.2);
    color: var(--primary2);
    font-size: 0.72rem;
    font-weight: 600;
    padding: 0.2rem 0.65rem;
    border-radius: 20px;
    letter-spacing: 0.02em;
  }

  .task {
    background: linear-gradient(90deg, rgba(124,92,252,0.12), transparent);
    border-left: 4px solid var(--primary);
    padding: 1.1rem 1.3rem;
    margin-bottom: 0.9rem;
    border-radius: 0 12px 12px 0;
  }
  .task strong { color: var(--primary2); }

  .quiz-question {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 1.2rem 1.3rem;
    margin-bottom: 0.9rem;
  }
  .quiz-question h4 {
    margin-bottom: 0.7rem;
    font-weight: 600;
    color: var(--text);
  }
  .options label {
    display: block;
    padding: 0.55rem 0.9rem;
    margin: 0.25rem 0;
    border-radius: 10px;
    cursor: pointer;
    transition: all 0.15s;
    border: 1px solid transparent;
    color: var(--muted);
  }
  .options label:hover {
    background: rgba(124, 92, 252, 0.1);
    border-color: rgba(124, 92, 252, 0.3);
    color: var(--text);
  }
  .options input { margin-right: 0.55rem; accent-color: var(--primary); }

  .btn {
    background: var(--gradient);
    color: white;
    border: none;
    padding: 0.7rem 1.7rem;
    border-radius: 12px;
    font-size: 0.95rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s;
    box-shadow: 0 4px 20px rgba(124, 92, 252, 0.3);
  }
  .btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 28px rgba(124, 92, 252, 0.4);
  }

  .result-box {
    display: none;
    margin-top: 1.5rem;
    padding: 1.8rem;
    border-radius: 16px;
    text-align: center;
    background: var(--card);
    border: 1px solid var(--border);
  }
  .result-box.show { display: block; }
  .score-big {
    font-size: 3.2rem;
    font-weight: 800;
    background: var(--gradient);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .chat-box {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    height: 420px;
    display: flex;
    flex-direction: column;
    overflow: hidden;
  }
  .chat-messages {
    flex: 1;
    overflow-y: auto;
    padding: 1.2rem;
  }
  .msg {
    margin-bottom: 0.85rem;
    max-width: 85%;
    padding: 0.7rem 1.05rem;
    border-radius: 14px;
    font-size: 0.93rem;
    line-height: 1.5;
  }
  .msg.bot {
    background: rgba(124, 92, 252, 0.15);
    border: 1px solid rgba(124, 92, 252, 0.25);
    border-bottom-left-radius: 4px;
    color: var(--text);
  }
  .msg.user {
    background: var(--primary);
    color: white;
    margin-left: auto;
    border-bottom-right-radius: 4px;
  }
  .chat-input {
    display: flex;
    border-top: 1px solid var(--border);
    padding: 0.85rem;
    gap: 0.5rem;
    background: var(--bg2);
  }
  .chat-input input {
    flex: 1;
    padding: 0.7rem 1.1rem;
    border: 1px solid var(--border);
    border-radius: 12px;
    background: var(--card);
    color: var(--text);
    font-size: 0.95rem;
    outline: none;
  }
  .chat-input input:focus { border-color: var(--primary); }
  .chat-input input::placeholder { color: var(--muted); }
  .chat-input button { padding: 0.7rem 1.3rem; }

  .quick-btns {
    display: flex;
    flex-wrap: wrap;
    gap: 0.45rem;
    margin-bottom: 1rem;
  }
  .quick-btns button {
    background: var(--card);
    border: 1px solid var(--border);
    color: var(--muted);
    padding: 0.4rem 0.85rem;
    border-radius: 20px;
    font-size: 0.82rem;
    cursor: pointer;
    transition: all 0.2s;
  }
  .quick-btns button:hover {
    background: rgba(124, 92, 252, 0.2);
    border-color: var(--primary);
    color: var(--text);
  }

  table {
    width: 100%;
    border-collapse: collapse;
    margin: 1rem 0;
    font-size: 0.92rem;
  }
  th, td {
    border: 1px solid var(--border);
    padding: 0.7rem 1rem;
    text-align: left;
  }
  th {
    background: rgba(124, 92, 252, 0.15);
    color: var(--primary2);
    font-weight: 600;
  }
  td { color: var(--muted); }

  .cube-scene { perspective: 600px; }
  .cube {
    width: 100px;
    height: 100px;
    position: relative;
    transform-style: preserve-3d;
    transform: rotateX(30deg) rotateY(45deg);
  }
  .face {
    position: absolute;
    width: 100px;
    height: 100px;
    border: 1px solid rgba(255,255,255,0.2);
  }
  .face.front  { transform: translateZ(50px); }
  .face.back   { transform: rotateY(180deg) translateZ(50px); }
  .face.right  { transform: rotateY(90deg) translateZ(50px); }
  .face.left   { transform: rotateY(-90deg) translateZ(50px); }
  .face.top    { transform: rotateX(90deg) translateZ(50px); }
  .face.bottom { transform: rotateX(-90deg) translateZ(50px); }

  footer {
    text-align: center;
    padding: 1.8rem;
    color: var(--muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--border);
    margin-top: 2rem;
  }

  @media (max-width: 600px) {
    .header-inner { flex-direction: column; align-items: flex-start; }
    nav { width: 100%; }
    nav button { flex: 1; text-align: center; font-size: 0.78rem; padding: 0.4rem 0.4rem; }
    .hero h1 { font-size: 1.7rem; }
    h1 { font-size: 1.5rem; }
  }
</style>
</head>
<body>

<header>
  <div class="header-inner">
    <div class="logo">CG • Оқу құралы</div>
    <nav>
      <button class="active" onclick="showSection('home')">Басты</button>
      <button onclick="showSection('theory')">Теория</button>
      <button onclick="showSection('practice')">Практика</button>
      <button onclick="showSection('quiz')">Тест</button>
      <button onclick="showSection('ai')">ЖИ-көмекші</button>
      <button onclick="showSection('result')">Нәтиже</button>
    </nav>
  </div>
</header>

<main>

<section id="home" class="section active">
  <div class="hero">
    <h1>Компьютерлік графика негіздері</h1>
    <p>Интеллектуалды электронды оқу құралы. Теория, практика, тест және ЖИ-көмекші — бәрі бір жерде.</p>
  </div>

  <div class="card">
    <h2 style="margin-top:0">Оқу құралы туралы</h2>
    <p><strong>Мақсаты:</strong> Студенттерге компьютерлік графиканың теориялық негіздерін, растрлық және векторлық графиканы, түстер теориясын, 2D/3D модельдеуді және анимация негіздерін практикалық деңгейде меңгерту.</p>
    <p><strong>Пән:</strong> Компьютерлік графика / Информатика &nbsp;|&nbsp; <strong>Деңгей:</strong> Бастауыш – орта</p>
  </div>

  <h2>Модульдер</h2>
  <div class="grid-2">
    <div class="topic-card" onclick="showSection('theory')">
      <div class="badge">02</div>
      <h3>Теориялық материал</h3>
      <p>5 негізгі тақырып: кіріспе, растр/вектор, түстер, 2D және 3D графика.</p>
    </div>
    <div class="topic-card" onclick="showSection('practice')">
      <div class="badge">03</div>
      <h3>Практикалық тапсырмалар</h3>
      <p>5 практикалық тапсырма: логотип, палитра, 2D-сурет, 3D-модель.</p>
    </div>
    <div class="topic-card" onclick="showSection('quiz')">
      <div class="badge">04</div>
      <h3>Интеллектуалды тест</h3>
      <p>15 сұрақ, автоматты тексеру және нәтижені есептеу.</p>
    </div>
    <div class="topic-card" onclick="showSection('ai')">
      <div class="badge">05</div>
      <h3>ЖИ-көмекші</h3>
      <p>Кез келген сұраққа жауап беретін виртуалды көмекші.</p>
    </div>
  </div>
</section>

<section id="theory" class="section">
  <h1>Теориялық материал</h1>
  <p style="margin-bottom:1.5rem;color:var(--muted)">Төменде компьютерлік графика бойынша толық теориялық материал берілген. Әр тақырыпты мұқият оқып шығыңыз.</p>

  <div class="card">
    <h2 style="margin-top:0">Тақырып 1. Компьютерлік графикаға кіріспе</h2>
    
    <p>Компьютерлік графика — бұл компьютердің көмегімен визуалды ақпаратты жасау, өңдеу, сақтау, беру және көрсету процесі. Қазіргі заманда ол адам өмірінің барлық саласына еніп кетті: кино мен ойындардан бастап медициналық диагностикаға, сәулет дизайнына және ғылыми зерттеулерге дейін.</p>
    
    <p>Компьютерлік графика екі үлкен топқа бөлінеді: <strong>интерактивті</strong> және <strong>интерактивті емес</strong>. Интерактивті графикада пайдаланушы суретпен тікелей жұмыс істей алады (мысалы, ойындарда немесе графикалық редакторларда). Интерактивті емес графикада сурет алдын ала дайындалып, кейін көрсетіледі (мысалы, анимациялық фильм).</p>

    <h3>Негізгі қолдану салалары</h3>
    <p>Компьютерлік графика көптеген салада қолданылады:</p>
    <ul>
      <li><strong>Компьютерлік ойындар</strong> — ең көп қолданылатын салалардың бірі. 3D-модельдер, текстуралар, жарықтандыру және анимация ойынның сапасын анықтайды.</li>
      <li><strong>Кино және анимация</strong> — арнайы эффекттер, CGI (Computer-Generated Imagery) көмегімен шынайы емес әлемдер жасалады.</li>
      <li><strong>Дизайн және жарнама</strong> — логотиптер, баннерлер, веб-дизайн, полиграфиялық өнімдер.</li>
      <li><strong>Ғылыми визуализация</strong> — молекулалық құрылымдарды, астрономиялық деректерді, медициналық сканерлеу нәтижелерін көрсету.</li>
      <li><strong>Сәулет және инженерия</strong> — ғимараттардың 3D-модельдері, жобалау және симуляция.</li>
    </ul>

    <h3>Қысқаша тарихи дамуы</h3>
    <p>Компьютерлік графиканың тарихы XX ғасырдың ортасынан басталады. 1950–60 жылдары алғашқы векторлық дисплейлер пайда болды. Олар тек сызықтар мен нүктелерді көрсете алды. 1970–80 жылдары растрлық графика дамып, пикселдер негізінде суреттер салына бастады. 1990 жылдардан бастап 3D-графика кең тарады, ал XXI ғасырда нақты уақыттағы рендеринг, виртуалды және толықтырылған шындық (VR/AR) технологиялары қарқынды дамып келеді.</p>
    
    <p>Бүгінде компьютерлік графикасыз заманауи технологияны елестету мүмкін емес. Сондықтан оның негіздерін меңгеру әрбір информатика және дизайн мамандығының студенті үшін маңызды.</p>
  </div>

  <div class="card">
    <h2 style="margin-top:0">Тақырып 2. Растрлық және векторлық графика</h2>
    
    <p>Компьютерлік графикада суреттерді сақтау мен көрсетудің екі негізгі тәсілі бар: <strong>растрлық</strong> және <strong>векторлық</strong>. Олардың әрқайсысының өз артықшылықтары мен кемшіліктері бар, сондықтан қолдану мақсатына қарай таңдалады.</p>

    <h3>Растрлық графика</h3>
    <p>Растрлық (немесе битмап) графика пикселдер торынан тұрады. Әр пикселдің өз түсі бар, ал бүкіл сурет осы пикселдердің жиынтығынан құралады. Суреттің сапасы оның <strong>ажыратымдылығымен</strong> (resolution) анықталады — яғни бір дюймдегі пикселдер санымен (DPI немесе PPI).</p>
    
    <p>Растрлық графиканың басты артықшылығы — фотореалистік суреттерді жоғары сапада көрсету мүмкіндігі. Фотосуреттер, күрделі иллюстрациялар, текстуралар әдетте растрлық форматта сақталады. Негізгі форматтар: <strong>JPEG</strong> (фотосуреттерге қолайлы, кішірейтілген), <strong>PNG</strong> (мөлдірлік қолдайды), <strong>GIF</strong> (қарапайым анимация), <strong>BMP</strong> және <strong>TIFF</strong> (жоғары сапа).</p>
    
    <p>Негізгі кемшілігі — суретті үлкейткенде пикселдер көріне бастайды, сапасы күрт төмендейді. Сондықтан растрлық суретті бастапқы өлшемінен үлкенірек жасау ұсынылмайды.</p>

    <h3>Векторлық графика</h3>
    <p>Векторлық графика математикалық формулаларға — нүктелерге, сызықтарға, қисықтарға және көпбұрыштарға негізделген. Әр объект координаттары мен параметрлері арқылы сипатталады. Сондықтан суретті кез келген өлшемге үлкейткенде немесе кішірейткенде сапасы мүлдем жоғалмайды.</p>
    
    <p>Векторлық графика логотиптер, иконкалар, схемалар, карталар, техникалық сызбалар үшін өте ыңғайлы. Негізгі форматтар: <strong>SVG</strong> (вебте кең қолданылады), <strong>AI</strong> (Adobe Illustrator), <strong>EPS</strong>, <strong>PDF</strong>.</p>
    
    <p>Кемшілігі — күрделі фотосуреттерді немесе шынайы текстураларды векторлық түрде сақтау мүмкін емес немесе өте қиын. Сондықтан практикада екі түрді де бірге қолданады: логотип векторлық, ал фондық сурет растрлық болады.</p>
  </div>

  <div class="card">
    <h2 style="margin-top:0">Тақырып 3. Түстер теориясы және түстер модельдері</h2>
    
    <p>Түс — компьютерлік графиканың ең маңызды элементтерінің бірі. Дұрыс таңдалған түстер композицияны әдемі етеді, ал қате таңдалған түстер бүкіл жұмысты бұзуы мүмкін. Сондықтан түстер теориясын білу әрбір график пен дизайнер үшін міндетті.</p>

    <h3>Негізгі түстер модельдері</h3>
    <p><strong>RGB (Red, Green, Blue)</strong> — аддитивті модель. Жарық қосылғанда түс пайда болады. Экрандар, мониторлар, телефондар, теледидарлар осы модельді қолданады. Әр канал 0-ден 255-ке дейін мән қабылдайды. Мысалы, таза қызыл — (255, 0, 0), ақ — (255, 255, 255), қара — (0, 0, 0).</p>
    
    <p><strong>CMYK (Cyan, Magenta, Yellow, Key/Black)</strong> — субтрактивті модель. Қағазға басып шығарғанда қолданылады. Түстер бір-біріне қосылғанда қараңғыланады. Полиграфияда міндетті түрде осы модельге ауыстырылады, әйтпесе экрандағы түс пен басылған түс әртүрлі болып шығады.</p>
    
    <p><strong>HSV / HSB (Hue, Saturation, Value/Brightness)</strong> — адамның түсті қабылдауына жақын модель. Hue — түс реңі (0–360°), Saturation — қанықтық, Value — жарықтық. Дизайнерлерге түстерді таңдау ыңғайлы.</p>
    
    <p><strong>LAB</strong> — түстерді құрылғыдан тәуелсіз сипаттайтын модель. Түстерді дәл салыстыру және түрлендіру үшін қолданылады.</p>

    <h3>Түстер үйлесімділігі</h3>
    <p>Түстерді үйлестірудің бірнеше классикалық схемасы бар:</p>
    <ul>
      <li><strong>Монохромды</strong> — бір түстің әртүрлі реңктері.</li>
      <li><strong>Аналогтық</strong> — түстер шеңберіндегі көршілес түстер.</li>
      <li><strong>Комплементарлы</strong> — бір-біріне қарама-қарсы түстер (мысалы, көк және сары).</li>
      <li><strong>Триада</strong> — түстер шеңберінде тең қашықтықта орналасқан үш түс.</li>
    </ul>
    <p>Практикада 3–5 түстен аспаған жөн. Негізгі түс, қосымша түс және акценттік түс таңдау — ең жиі қолданылатын тәсіл.</p>
  </div>

  <div class="card">
    <h2 style="margin-top:0">Тақырып 4. 2D-графика негіздері</h2>
    
    <p>Екі өлшемді (2D) графика — жазықтықтағы суреттермен жұмыс істеу. Барлық сурет x және y координаттары арқылы сипатталады. 2D-графика веб-дизайнда, интерфейстерде, ойындарда, иллюстрацияларда және анимацияда кең қолданылады.</p>

    <h3>Координаттар жүйесі</h3>
    <p>Компьютерлік графикада әдетте сол жақ жоғарғы бұрыш бастапқы нүкте (0, 0) болып саналады. x осі оңға қарай, y осі төмен қарай өседі (экран координаттарында). Математикалық жүйеде y осі жоғары қарай өседі, бірақ графикалық бағдарламаларда көбінесе экран координаттары қолданылады.</p>

    <h3>Негізгі примитивтер</h3>
    <p>Кез келген 2D-сурет қарапайым фигуралардан құралады:</p>
    <ul>
      <li><strong>Нүкте</strong> — ең кіші элемент, координаттары (x, y) бар.</li>
      <li><strong>Сызық</strong> — екі нүктені қосатын кесінді.</li>
      <li><strong>Төртбұрыш / тіктөртбұрыш</strong> — төрт бұрышы бар фигура.</li>
      <li><strong>Шеңбер / эллипс</strong> — центр және радиус арқылы анықталады.</li>
      <li><strong>Көпбұрыш</strong> — бірнеше төбесі бар тұйық фигура.</li>
    </ul>

    <h3>Геометриялық түрлендірулер (трансформациялар)</h3>
    <p>Объектілерді өзгерту үшін төрт негізгі операция қолданылады:</p>
    <ul>
      <li><strong>Трансляция (жылжыту)</strong> — объектіні x немесе y бағытында жылжыту.</li>
      <li><strong>Ротация (айналдыру)</strong> — объектіні белгілі бір бұрышқа айналдыру.</li>
      <li><strong>Масштабтау</strong> — объектіні үлкейту немесе кішірейту.</li>
      <li><strong>Қиғаштыру (shear)</strong> — объектіні бір бағытта «созу».</li>
    </ul>
    <p>Бұл операциялар матрицалар арқылы математикалық түрде орындалады. Қазіргі графикалық бағдарламаларда олар бір батырмамен жасалады, бірақ негізін түсіну маңызды.</p>
  </div>

  <div class="card">
    <h2 style="margin-top:0">Тақырып 5. 3D-графика және анимация негіздері</h2>
    
    <p>Үш өлшемді (3D) графика — объектілерді үш өлшемді кеңістікте модельдеу, текстуралау, жарықтандыру және көрсету процесі. Қазіргі кино, ойындар, сәулет және өнеркәсіптік дизайнның негізі осында.</p>

    <h3>3D-кеңістік және координаттар</h3>
    <p>3D-кеңістікте әр нүкте үш координатпен сипатталады: <strong>x, y, z</strong>. z осі әдетте тереңдікті көрсетеді. Объектілер полигондардан (көбінесе үшбұрыштардан) құралады. Полигондардың жиынтығы <strong>тор</strong> (mesh) деп аталады.</p>

    <h3>Негізгі элементтер</h3>
    <ul>
      <li><strong>Полигон</strong> — 3D-модельдің бетінің ең кіші бөлігі.</li>
      <li><strong>Текстура</strong> — модельдің бетіне жабыстырылатын 2D-сурет (түс, өрнек, bump-карта).</li>
      <li><strong>Материал</strong> — объектінің бетінің қасиеттері (жылтырлық, мөлдірлік, шағылысу).</li>
      <li><strong>Жарықтандыру</strong> — Ambient (жалпы жарық), Diffuse (шашыраңқы), Specular (жылтыр шағылысу).</li>
      <li><strong>Камера</strong> — көрерменнің көзқарасы. Перспектива арқылы тереңдік сезімі жасалады.</li>
    </ul>

    <h3>Анимация негіздері</h3>
    <p>Анимация — уақыт бойынша өзгеретін суреттер тізбегі. Негізгі ұғымдар:</p>
    <ul>
      <li><strong>Кадр (frame)</strong> — анимацияның бір суреті.</li>
      <li><strong>Keyframe</strong> — маңызды өзгеріс болатын негізгі кадр.</li>
      <li><strong>Интерполяция</strong> — екі keyframe арасындағы аралық кадрларды автоматты есептеу.</li>
    </ul>
    <p>Қазіргі бағдарламаларда (Blender, Maya, 3ds Max) анимацияны timeline арқылы басқарады. Объектінің орны, бұрышы, масштабы, тіпті материалдары да уақыт бойынша өзгере алады.</p>
    
    <p>3D-графиканы меңгеру үшін алдымен қарапайым примитивтермен (куб, сфера, цилиндр) жұмыс істеп үйрену, кейін модификаторлар, текстуралау және жарықтандыруды меңгеру ұсынылады. Blender — бастаушылар үшін ең қолайлы тегін бағдарламалардың бірі.</p>
  </div>
</section>

<section id="practice" class="section">
  <h1>Практикалық тапсырмалар</h1>
  <p style="margin-bottom:1.5rem">Тапсырмаларды тікелей осы жерде орындаңыз. Сурет салыңыз, түстер таңдаңыз, нәтижені сақтаңыз.</p>

  <!-- Тапсырма 1: Сурет салу -->
  <div class="card">
    <div class="badge">Тапсырма 01–02</div>
    <h2 style="margin-top:0.4rem">Растрлық сурет / логотип салу</h2>
    <p><strong>Мақсаты:</strong> Тінтуірмен сурет салып, растрлық графиканы практикада көру.</p>
    <p>Төмендегі құралдармен сурет салыңыз. Логотип, әріп немесе қарапайым фигура жасауға болады.</p>
    
    <div class="toolbar" style="display:flex;flex-wrap:wrap;gap:0.6rem;margin:1rem 0;align-items:center">
      <label style="color:var(--muted);font-size:0.9rem">Түс: <input type="color" id="drawColor" value="#7c5cfc"></label>
      <label style="color:var(--muted);font-size:0.9rem">Қалыңдық: <input type="range" id="drawSize" min="1" max="40" value="8" style="width:100px"></label>
      <button class="btn" onclick="clearCanvas('drawCanvas')" style="padding:0.4rem 1rem;font-size:0.85rem">Тазалау</button>
      <button class="btn" onclick="downloadCanvas('drawCanvas','logo.png')" style="padding:0.4rem 1rem;font-size:0.85rem">Жүктеу (PNG)</button>
    </div>
    <canvas id="drawCanvas" width="500" height="400" style="width:100%;max-width:500px;background:#fff;border-radius:12px;cursor:crosshair;border:2px solid var(--border);touch-action:none"></canvas>
  </div>

  <!-- Тапсырма 3: Түстер палитрасы -->
  <div class="card">
    <div class="badge">Тапсырма 03</div>
    <h2 style="margin-top:0.4rem">Түстер палитрасын құрастыру</h2>
    <p><strong>Мақсаты:</strong> 5 түстен тұратын үйлесімді палитра жасау.</p>
    <p>Төмендегі 5 түсті таңдаңыз. HEX және RGB кодтары автоматты көрсетіледі.</p>
    
    <div style="display:flex;flex-wrap:wrap;gap:1rem;margin:1.2rem 0" id="palettePickers">
      <div style="text-align:center">
        <input type="color" id="c1" value="#7c5cfc" onchange="updatePalette()" style="width:60px;height:60px;border:none;cursor:pointer;border-radius:10px">
        <div id="hex1" style="font-size:0.8rem;margin-top:0.3rem;color:var(--muted)">#7c5cfc</div>
      </div>
      <div style="text-align:center">
        <input type="color" id="c2" value="#22d3ee" onchange="updatePalette()" style="width:60px;height:60px;border:none;cursor:pointer;border-radius:10px">
        <div id="hex2" style="font-size:0.8rem;margin-top:0.3rem;color:var(--muted)">#22d3ee</div>
      </div>
      <div style="text-align:center">
        <input type="color" id="c3" value="#34d399" onchange="updatePalette()" style="width:60px;height:60px;border:none;cursor:pointer;border-radius:10px">
        <div id="hex3" style="font-size:0.8rem;margin-top:0.3rem;color:var(--muted)">#34d399</div>
      </div>
      <div style="text-align:center">
        <input type="color" id="c4" value="#fbbf24" onchange="updatePalette()" style="width:60px;height:60px;border:none;cursor:pointer;border-radius:10px">
        <div id="hex4" style="font-size:0.8rem;margin-top:0.3rem;color:var(--muted)">#fbbf24</div>
      </div>
      <div style="text-align:center">
        <input type="color" id="c5" value="#f87171" onchange="updatePalette()" style="width:60px;height:60px;border:none;cursor:pointer;border-radius:10px">
        <div id="hex5" style="font-size:0.8rem;margin-top:0.3rem;color:var(--muted)">#f87171</div>
      </div>
    </div>
    
    <div id="palettePreview" style="display:flex;height:50px;border-radius:10px;overflow:hidden;margin-bottom:1rem">
      <div style="flex:1;background:#7c5cfc"></div>
      <div style="flex:1;background:#22d3ee"></div>
      <div style="flex:1;background:#34d399"></div>
      <div style="flex:1;background:#fbbf24"></div>
      <div style="flex:1;background:#f87171"></div>
    </div>
    <div id="paletteCodes" style="font-size:0.85rem;color:var(--muted);line-height:1.8"></div>
  </div>

  <!-- Тапсырма 4: 2D пейзаж -->
  <div class="card">
    <div class="badge">Тапсырма 04</div>
    <h2 style="margin-top:0.4rem">2D-пейзаж салу</h2>
    <p><strong>Мақсаты:</strong> Қарапайым пейзаж салу. Түс пен қалыңдықты өзгертіп, бірнеше элемент салыңыз.</p>
    
    <div class="toolbar" style="display:flex;flex-wrap:wrap;gap:0.6rem;margin:1rem 0;align-items:center">
      <label style="color:var(--muted);font-size:0.9rem">Түс: <input type="color" id="landColor" value="#22d3ee"></label>
      <label style="color:var(--muted);font-size:0.9rem">Қалыңдық: <input type="range" id="landSize" min="1" max="50" value="12" style="width:100px"></label>
      <button class="btn" onclick="clearCanvas('landCanvas')" style="padding:0.4rem 1rem;font-size:0.85rem">Тазалау</button>
      <button class="btn" onclick="downloadCanvas('landCanvas','peyzazh.png')" style="padding:0.4rem 1rem;font-size:0.85rem">Жүктеу (PNG)</button>
    </div>
    <canvas id="landCanvas" width="600" height="400" style="width:100%;max-width:600px;background:#1a2234;border-radius:12px;cursor:crosshair;border:2px solid var(--border);touch-action:none"></canvas>
  </div>

  <!-- Тапсырма 5: 3D куб (CSS) -->
  <div class="card">
    <div class="badge">Тапсырма 05</div>
    <h2 style="margin-top:0.4rem">3D-кубты басқару</h2>
    <p><strong>Мақсаты:</strong> 3D-кеңістікті түсіну. Кубтың түсін өзгертіп, айналдырыңыз.</p>
    
    <div style="display:flex;flex-wrap:wrap;gap:1.5rem;align-items:center;margin-top:1rem">
      <div class="cube-scene" style="width:200px;height:200px;perspective:600px">
        <div class="cube" id="cube3d" style="width:100px;height:100px;position:relative;transform-style:preserve-3d;margin:50px auto;transition:transform 0.5s">
          <div class="face front" style="background:rgba(124,92,252,0.85)"></div>
          <div class="face back" style="background:rgba(34,211,238,0.85)"></div>
          <div class="face right" style="background:rgba(52,211,153,0.85)"></div>
          <div class="face left" style="background:rgba(251,191,36,0.85)"></div>
          <div class="face top" style="background:rgba(248,113,113,0.85)"></div>
          <div class="face bottom" style="background:rgba(167,139,250,0.85)"></div>
        </div>
      </div>
      <div style="flex:1;min-width:200px">
        <label style="display:block;margin-bottom:0.8rem;color:var(--muted)">Түс: <input type="color" id="cubeColor" value="#7c5cfc" onchange="changeCubeColor()"></label>
        <label style="display:block;margin-bottom:0.8rem;color:var(--muted)">X айналдыру: <input type="range" id="rotX" min="0" max="360" value="30" oninput="rotateCube()" style="width:140px"></label>
        <label style="display:block;margin-bottom:0.8rem;color:var(--muted)">Y айналдыру: <input type="range" id="rotY" min="0" max="360" value="45" oninput="rotateCube()" style="width:140px"></label>
        <p style="font-size:0.85rem;color:var(--muted)">Бұл — CSS 3D. Нақты 3D-модельдеу үшін Blender бағдарламасын пайдаланыңыз (тегін: blender.org).</p>
      </div>
    </div>
  </div>

  <!-- Тапсырма 06: Коллаж -->
  <div class="card">
    <div class="badge">Тапсырма 06</div>
    <h2 style="margin-top:0.4rem">Коллаж жасау</h2>
    <p><strong>Мақсаты:</strong> Бірнеше суретті бір композицияға біріктіру.</p>
    <p>Өз суреттеріңізді жүктеп, оларды бір жерге орналастырыңыз. Сосын PNG етіп жүктеп алыңыз.</p>
    
    <div style="margin:1rem 0">
      <input type="file" id="collageFiles" accept="image/*" multiple style="color:var(--muted);font-size:0.9rem">
      <button class="btn" onclick="addCollageImages()" style="padding:0.4rem 1rem;font-size:0.85rem;margin-left:0.5rem">Қосу</button>
      <button class="btn" onclick="clearCanvas('collageCanvas')" style="padding:0.4rem 1rem;font-size:0.85rem">Тазалау</button>
      <button class="btn" onclick="downloadCanvas('collageCanvas','kollazh.png')" style="padding:0.4rem 1rem;font-size:0.85rem">Жүктеу (PNG)</button>
    </div>
    <p style="font-size:0.85rem;color:var(--muted);margin-bottom:0.6rem">Суретті басып ұстап жылжытыңыз. Өлшемін өзгерту үшін оң жақ төменгі бұрышын тартыңыз (қарапайым нұсқада жылжыту ғана).</p>
    <canvas id="collageCanvas" width="600" height="400" style="width:100%;max-width:600px;background:#111827;border-radius:12px;border:2px solid var(--border);cursor:move;touch-action:none"></canvas>
  </div>

  <!-- Тапсырма 07: Спрайт-анимация -->
  <div class="card">
    <div class="badge">Тапсырма 07</div>
    <h2 style="margin-top:0.4rem">Спрайт-анимация</h2>
    <p><strong>Мақсаты:</strong> Кадрларды ауыстырып, қарапайым анимация жасау.</p>
    <p>Төменде 4 кадр бар. «Ойнату» батырмасын басып, анимацияны көріңіз. Жылдамдықты өзгертуге болады.</p>
    
    <div style="display:flex;flex-wrap:wrap;gap:1.5rem;align-items:flex-start;margin-top:1rem">
      <div>
        <canvas id="spriteCanvas" width="120" height="120" style="background:#1a2234;border-radius:12px;border:2px solid var(--border);image-rendering:pixelated"></canvas>
        <div style="margin-top:0.8rem;display:flex;gap:0.5rem;flex-wrap:wrap">
          <button class="btn" id="spritePlayBtn" onclick="toggleSprite()" style="padding:0.4rem 1rem;font-size:0.85rem">Ойнату</button>
          <button class="btn" onclick="spriteFrame=0;drawSpriteFrame()" style="padding:0.4rem 1rem;font-size:0.85rem">Басына</button>
        </div>
        <label style="display:block;margin-top:0.8rem;color:var(--muted);font-size:0.9rem">
          Жылдамдық: <input type="range" id="spriteSpeed" min="50" max="500" value="200" style="width:120px">
          <span id="speedVal">200</span> мс
        </label>
      </div>
      <div style="flex:1;min-width:180px">
        <p style="font-size:0.9rem;color:var(--muted);margin-bottom:0.6rem">Кадрлар (пиксель-арт доп):</p>
        <div style="display:flex;gap:0.5rem;flex-wrap:wrap" id="spriteThumbs"></div>
        <p style="font-size:0.85rem;color:var(--muted);margin-top:1rem">Бұл — спрайт-анимацияның қарапайым мысалы. Ойындарда кейіпкерлер осылай қозғалады.</p>
      </div>
    </div>
  </div>
</section>

<section id="quiz" class="section">
  <h1>Интеллектуалды тест</h1>
  <p>15 сұрақ. Әр сұраққа бір жауап таңдаңыз, содан кейін нәтижені қараңыз.</p>

  <form id="quizForm">
    <div class="quiz-question" data-correct="a">
      <h4>1. Компьютерлік графиканың негізгі екі түрі?</h4>
      <div class="options">
        <label><input type="radio" name="q1" value="a"> а) Растрлық және векторлық</label>
        <label><input type="radio" name="q1" value="b"> б) Тек 3D</label>
        <label><input type="radio" name="q1" value="c"> в) Тек анимация</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="b">
      <h4>2. RGB моделі қайда қолданылады?</h4>
      <div class="options">
        <label><input type="radio" name="q2" value="a"> а) Басып шығару</label>
        <label><input type="radio" name="q2" value="b"> б) Экранға шығару</label>
        <label><input type="radio" name="q2" value="c"> в) Дыбыс жазу</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="b">
      <h4>3. Векторлық графиканың басты артықшылығы?</h4>
      <div class="options">
        <label><input type="radio" name="q3" value="a"> а) Файл өлшемі үлкен</label>
        <label><input type="radio" name="q3" value="b"> б) Масштабтағанда сапасы сақталады</label>
        <label><input type="radio" name="q3" value="c"> в) Тек фотосуретке арналған</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="b">
      <h4>4. CMYK моделі не үшін керек?</h4>
      <div class="options">
        <label><input type="radio" name="q4" value="a"> а) Монитор</label>
        <label><input type="radio" name="q4" value="b"> б) Басып шығару</label>
        <label><input type="radio" name="q4" value="c"> в) 3D-модельдеу</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="b">
      <h4>5. 3D-графикада қандай координаттар қолданылады?</h4>
      <div class="options">
        <label><input type="radio" name="q5" value="a"> а) x, y</label>
        <label><input type="radio" name="q5" value="b"> б) x, y, z</label>
        <label><input type="radio" name="q5" value="c"> в) тек z</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="b">
      <h4>6. Пиксел дегеніміз не?</h4>
      <div class="options">
        <label><input type="radio" name="q6" value="a"> а) Векторлық сызық</label>
        <label><input type="radio" name="q6" value="b"> б) Растрлық суреттің ең кіші элементі</label>
        <label><input type="radio" name="q6" value="c"> в) 3D-объект</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="b">
      <h4>7. SVG форматы қандай графикаға жатады?</h4>
      <div class="options">
        <label><input type="radio" name="q7" value="a"> а) Растрлық</label>
        <label><input type="radio" name="q7" value="b"> б) Векторлық</label>
        <label><input type="radio" name="q7" value="c"> в) 3D</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="b">
      <h4>8. Трансляция дегеніміз не?</h4>
      <div class="options">
        <label><input type="radio" name="q8" value="a"> а) Айналдыру</label>
        <label><input type="radio" name="q8" value="b"> б) Жылжыту</label>
        <label><input type="radio" name="q8" value="c"> в) Жою</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="b">
      <h4>9. Blender қандай бағдарлама?</h4>
      <div class="options">
        <label><input type="radio" name="q9" value="a"> а) Тек 2D-сурет</label>
        <label><input type="radio" name="q9" value="b"> б) 3D-модельдеу және анимация</label>
        <label><input type="radio" name="q9" value="c"> в) Мәтін өңдеу</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="a">
      <h4>10. HSV моделінің құрамдас бөліктері?</h4>
      <div class="options">
        <label><input type="radio" name="q10" value="a"> а) Hue, Saturation, Value</label>
        <label><input type="radio" name="q10" value="b"> б) Red, Green, Blue</label>
        <label><input type="radio" name="q10" value="c"> в) Cyan, Magenta, Yellow</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="b">
      <h4>11. Растрлық суретті үлкейткенде не болады?</h4>
      <div class="options">
        <label><input type="radio" name="q11" value="a"> а) Сапасы артады</label>
        <label><input type="radio" name="q11" value="b"> б) Пикселдер көрінеді, сапа төмендейді</label>
        <label><input type="radio" name="q11" value="c"> в) Ештеңе өзгермейді</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="a">
      <h4>12. Keyframe дегеніміз не?</h4>
      <div class="options">
        <label><input type="radio" name="q12" value="a"> а) Негізгі кадр</label>
        <label><input type="radio" name="q12" value="b"> б) Фондық сурет</label>
        <label><input type="radio" name="q12" value="c"> в) Түстер палитрасы</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="b">
      <h4>13. Ambient жарық дегеніміз не?</h4>
      <div class="options">
        <label><input type="radio" name="q13" value="a"> а) Негізгі жарық көзі</label>
        <label><input type="radio" name="q13" value="b"> б) Жалпы қоршаған жарық</label>
        <label><input type="radio" name="q13" value="c"> в) Көлеңке</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="a">
      <h4>14. Полигон дегеніміз не?</h4>
      <div class="options">
        <label><input type="radio" name="q14" value="a"> а) 3D-модельдің бетінің бөлігі</label>
        <label><input type="radio" name="q14" value="b"> б) Түс коды</label>
        <label><input type="radio" name="q14" value="c"> в) Файл форматы</label>
      </div>
    </div>
    <div class="quiz-question" data-correct="b">
      <h4>15. Перспектива не үшін керек?</h4>
      <div class="options">
        <label><input type="radio" name="q15" value="a"> а) Объектіні жазық көрсету</label>
        <label><input type="radio" name="q15" value="b"> б) Үш өлшемді тереңдікті сезіндіру</label>
        <label><input type="radio" name="q15" value="c"> в) Түсті өзгерту</label>
      </div>
    </div>

    <button type="button" class="btn" onclick="checkQuiz()">Нәтижені көру</button>
  </form>
  <div id="quizResult" class="result-box"></div>
</section>

<section id="ai" class="section">
  <h1>ЖИ-көмекші</h1>
  <p>Кез келген сұрақ қойыңыз — графикадан бастап күнделікті сөздерге дейін жауап береді.</p>

  <div class="quick-btns">
    <button onclick="askAI('Сәлем')">Сәлем</button>
    <button onclick="askAI('Растрлық пен векторлық айырмашылығы')">Растр vs Вектор</button>
    <button onclick="askAI('RGB мен CMYK')">RGB vs CMYK</button>
    <button onclick="askAI('Blender-де куб қалай жасалады?')">Blender куб</button>
    <button onclick="askAI('Бекс')">Бекс</button>
    <button onclick="askAI('Алихан')">Алихан</button>
  </div>

  <div class="chat-box">
    <div class="chat-messages" id="chatMessages">
      <div class="msg bot">Сәлем! Мен сенің ЖИ-көмекшіңмін. Компьютерлік графика бойынша да, күнделікті сұрақтарға да жауап беремін. Жазып жібер!</div>
    </div>
    <div class="chat-input">
      <input type="text" id="userInput" placeholder="Сұрағыңызды жазыңыз..." onkeypress="if(event.key==='Enter')sendMessage()">
      <button class="btn" onclick="sendMessage()">Жіберу</button>
    </div>
  </div>
</section>

<section id="result" class="section">
  <h1>Білімді бағалау</h1>
  <div class="card">
    <div id="finalResult">
      <p style="color:var(--muted)">Әзірге тест тапсырылмаған. «Тест» бөліміне өтіп, сұрақтарға жауап беріңіз.</p>
    </div>
  </div>
  <div class="card">
    <h2 style="margin-top:0">Бағалау шкаласы</h2>
    <table>
      <tr><th>Пайыз</th><th>Баға</th><th>Ұсыныс</th></tr>
      <tr><td>90–100%</td><td>Өте жақсы</td><td>Келесі деңгейге өтуге болады</td></tr>
      <tr><td>70–89%</td><td>Жақсы</td><td>3-ші және 5-ші тақырыптарды қайталаңыз</td></tr>
      <tr><td>50–69%</td><td>Орташа</td><td>Практикалық тапсырмаларды қайта орындаңыз</td></tr>
      <tr><td>50%-дан төмен</td><td>Қайталау керек</td><td>Теорияны толық қайта оқыңыз</td></tr>
    </table>
  </div>
</section>

</main>

<footer>
  Компьютерлік графика негіздері • Интеллектуалды электронды оқу құралы • 2026
</footer>

<script>
function showSection(id) {
  document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  document.querySelectorAll('nav button').forEach(b => b.classList.remove('active'));
  const map = {home:0, theory:1, practice:2, quiz:3, ai:4, result:5};
  const btns = document.querySelectorAll('nav button');
  if (map[id] !== undefined) btns[map[id]].classList.add('active');
  window.scrollTo({top:0, behavior:'smooth'});
}

function checkQuiz() {
  const questions = document.querySelectorAll('.quiz-question');
  let score = 0;
  let total = questions.length;
  let details = [];

  questions.forEach((q, i) => {
    const correct = q.dataset.correct;
    const selected = q.querySelector('input:checked');
    if (selected && selected.value === correct) {
      score++;
      details.push(`<li>Сұрақ ${i+1}: дұрыс ✓</li>`);
    } else {
      details.push(`<li>Сұрақ ${i+1}: қате (дұрыс: ${correct})</li>`);
    }
  });

  const percent = Math.round((score / total) * 100);
  let advice = '';
  if (percent >= 90) advice = 'Өте жақсы! Келесі деңгейге өтуге болады.';
  else if (percent >= 70) advice = 'Жақсы. 3-ші және 5-ші тақырыптарды қайталаңыз.';
  else if (percent >= 50) advice = 'Орташа. Практикалық тапсырмаларды қайта орындаңыз.';
  else advice = 'Теорияны толық қайта оқып, тестті қайта тапсырыңыз.';

  const resultBox = document.getElementById('quizResult');
  resultBox.classList.add('show');
  resultBox.innerHTML = `
    <div class="score-big">${percent}%</div>
    <p style="color:var(--text);margin-top:0.5rem"><strong>${score} / ${total}</strong> дұрыс жауап</p>
    <p>${advice}</p>
  `;

  document.getElementById('finalResult').innerHTML = `
    <div class="score-big">${percent}%</div>
    <p style="color:var(--text);margin-top:0.5rem"><strong>${score} / ${total}</strong> дұрыс жауап</p>
    <p><strong>Ұсыныс:</strong> ${advice}</p>
    <h3>Жеке талдау</h3>
    <ul>${details.join('')}</ul>
  `;
}

function askAI(text) {
  document.getElementById('userInput').value = text;
  sendMessage();
}

function sendMessage() {
  const input = document.getElementById('userInput');
  const text = input.value.trim();
  if (!text) return;

  const messages = document.getElementById('chatMessages');
  messages.innerHTML += `<div class="msg user">${text}</div>`;

  const lower = text.toLowerCase();
  let answer = '';

  // Арнайы аттар
  if (lower.includes('бекс')) answer = 'мал';
  else if (lower.includes('алихан')) answer = 'Лев';
  else if (lower.includes('дауке')) answer = 'Тигр';
  else if (lower.includes('есен')) answer = 'Айгыр';

  // Сәлемдесу
  else if (lower.match(/сәлем|салем|привет|hello|hi|ассалаумағалейкум|қош келдің/))
    answer = 'Сәлем! Қалың қалай? Не көмектесейін?';
  else if (lower.match(/қалың қалай|қалайсың|не хабар|как дела/))
    answer = 'Жақсы, рахмет! Өзің қалайсың? Оқу құралы бойынша сұрағың болса — жаз!';
  else if (lower.match(/рахмет|алғыс|спасибо|thanks/))
    answer = 'Оқасы жоқ! Тағы бірдеңе керек болса — жазып жібер.';
  else if (lower.match(/сау бол|көріскенше|пока|bye/))
    answer = 'Сау бол! Кейін көрісейік 👋';

  // Уақыт / күн
  else if (lower.match(/неше|сағат|уақыт|время|час/))
    answer = 'Қазіргі уақытты білгің келсе, телефоныңа қара. Мен оқу құралы бойынша көмектесемін 😊';
  else if (lower.match(/бүгін|күні|дата|день/))
    answer = 'Бүгін — жақсы күн оқуға! Теорияны оқып, тестті тапсырып көр.';

  // Графика сұрақтары
  else if (lower.includes('растр') || lower.includes('вектор'))
    answer = 'Растрлық графика пикселдерден тұрады (JPEG, PNG) — фотоға қолайлы, бірақ үлкейткенде сапасы төмендейді. Векторлық графика математикалық формулалардан тұрады (SVG, AI) — кез келген өлшемде сапасы сақталады.';
  else if (lower.includes('rgb') || lower.includes('cmyk'))
    answer = 'RGB — экранға арналған (Red, Green, Blue). CMYK — басып шығаруға арналған (Cyan, Magenta, Yellow, Black). Вебте RGB, полиграфияда CMYK қолданылады.';
  else if (lower.includes('blender') || lower.includes('куб'))
    answer = 'Blender-де куб: Shift+A → Mesh → Cube. Материал қосып, жарық беріп, F12 басып рендер жаса. Тегін және өте күшті бағдарлама!';
  else if (lower.includes('3d') || lower.includes('модельдеу'))
    answer = '3D-модельдеуді Blender-ден баста. Алдымен қарапайым фигуралармен жұмыс істе, кейін материал, жарық, камераны меңгер.';
  else if (lower.includes('түс') || lower.includes('палитра') || lower.includes('цвет'))
    answer = 'Түстер палитрасын Adobe Color немесе Canva-дан таңда. Комплементарлы, аналогтық немесе триада схемаларын қолдан. 5 түстен аспауға тырыс.';
  else if (lower.includes('пиксел') || lower.includes('pixel'))
    answer = 'Пиксел — растрлық суреттің ең кіші элементі. Көп пиксел = жоғары сапа (разрешение).';
  else if (lower.includes('svg'))
    answer = 'SVG — векторлық формат. Логотип, иконка, иллюстрацияға өте ыңғайлы. Браузерде тікелей ашылады.';
  else if (lower.includes('анимация') || lower.includes('animation'))
    answer = 'Анимацияда негізгі ұғымдар: кадр (frame), keyframe (негізгі кадр), интерполяция. Blender немесе After Effects қолдануға болады.';

  // Оқу / тест
  else if (lower.match(/тест|емтихан|сұрақ|баға/))
    answer = 'Тест бөліміне өтіп, 15 сұраққа жауап бер. Нәтижені бірден көресің. Дайын болсаң — сәттілік!';
  else if (lower.match(/теория|оқу|материал/))
    answer = 'Теория бөлімінде 5 тақырып бар. Ретімен оқып шық, кейін практикалық тапсырмаларды орында.';
  else if (lower.match(/тапсырма|практика|homework/))
    answer = 'Практика бөлімінде 5 тапсырма бар: растрлық/векторлық логотип, түстер палитрасы, 2D-сурет және 3D-модель. Бастап көр!';

  // Жалпы
  else if (lower.match(/кімсің|сен кім|кто ты|what are you/))
    answer = 'Мен осы оқу құралының ЖИ-көмекшісімін. Компьютерлік графиканы түсіндіремін және күнделікті сұрақтарға да жауап беремін.';
  else if (lower.match(/көмек|help|помоги/))
    answer = 'Әрине! Не керек екенін айт: теория, практика, тест немесе басқа сұрақ.';
  else if (lower.match(/жақсы|керемет|круто|cool|super/))
    answer = 'Рахмет! 🙌 Тағы бірдеңе сұрасаң болады.';
  else if (lower.length < 3)
    answer = 'Тағы бірдеңе жазып жіберші 😊';
  else
    answer = 'Қызықты сұрақ! Мен негізінен компьютерлік графика бойынша көмектесемін. Нақтырақ сұрасаң — жақсырақ жауап беремін. Мысалы: «Растр деген не?», «Blender қалай ашылады?»';

  setTimeout(() => {
    messages.innerHTML += `<div class="msg bot">${answer}</div>`;
    messages.scrollTop = messages.scrollHeight;
  }, 350);

  input.value = '';
  messages.scrollTop = messages.scrollHeight;
}

// ===== Практика: Canvas сурет салу =====
function initCanvas(canvasId, colorId, sizeId) {
  const canvas = document.getElementById(canvasId);
  if (!canvas) return;
  const ctx = canvas.getContext('2d');
  let drawing = false;

  function getPos(e) {
    const rect = canvas.getBoundingClientRect();
    const scaleX = canvas.width / rect.width;
    const scaleY = canvas.height / rect.height;
    const clientX = e.touches ? e.touches[0].clientX : e.clientX;
    const clientY = e.touches ? e.touches[0].clientY : e.clientY;
    return {
      x: (clientX - rect.left) * scaleX,
      y: (clientY - rect.top) * scaleY
    };
  }

  function start(e) {
    e.preventDefault();
    drawing = true;
    const p = getPos(e);
    ctx.beginPath();
    ctx.moveTo(p.x, p.y);
  }
  function draw(e) {
    if (!drawing) return;
    e.preventDefault();
    const p = getPos(e);
    ctx.strokeStyle = document.getElementById(colorId).value;
    ctx.lineWidth = document.getElementById(sizeId).value;
    ctx.lineCap = 'round';
    ctx.lineJoin = 'round';
    ctx.lineTo(p.x, p.y);
    ctx.stroke();
  }
  function stop() { drawing = false; }

  canvas.addEventListener('mousedown', start);
  canvas.addEventListener('mousemove', draw);
  canvas.addEventListener('mouseup', stop);
  canvas.addEventListener('mouseleave', stop);
  canvas.addEventListener('touchstart', start, {passive:false});
  canvas.addEventListener('touchmove', draw, {passive:false});
  canvas.addEventListener('touchend', stop);
}

function clearCanvas(id) {
  const canvas = document.getElementById(id);
  const ctx = canvas.getContext('2d');
  ctx.clearRect(0, 0, canvas.width, canvas.height);
}

function downloadCanvas(id, filename) {
  const canvas = document.getElementById(id);
  const link = document.createElement('a');
  link.download = filename;
  link.href = canvas.toDataURL('image/png');
  link.click();
}

// ===== Палитра =====
function updatePalette() {
  const ids = ['c1','c2','c3','c4','c5'];
  const preview = document.getElementById('palettePreview');
  const codes = document.getElementById('paletteCodes');
  let html = '';
  let codeText = '';
  ids.forEach((id, i) => {
    const val = document.getElementById(id).value;
    document.getElementById('hex' + (i+1)).textContent = val;
    html += `<div style="flex:1;background:${val}"></div>`;
    const r = parseInt(val.slice(1,3),16);
    const g = parseInt(val.slice(3,5),16);
    const b = parseInt(val.slice(5,7),16);
    codeText += `Түс ${i+1}: ${val} &nbsp; RGB(${r}, ${g}, ${b})<br>`;
  });
  preview.innerHTML = html;
  codes.innerHTML = codeText;
}

// ===== 3D куб =====
function rotateCube() {
  const x = document.getElementById('rotX').value;
  const y = document.getElementById('rotY').value;
  document.getElementById('cube3d').style.transform = `rotateX(${x}deg) rotateY(${y}deg)`;
}
function changeCubeColor() {
  const c = document.getElementById('cubeColor').value;
  document.querySelector('#cube3d .face.front').style.background = c;
}

// ===== Коллаж =====
let collageImages = [];
let dragIndex = -1;
let dragOffset = {x:0, y:0};

function addCollageImages() {
  const input = document.getElementById('collageFiles');
  const files = input.files;
  if (!files.length) return;
  const canvas = document.getElementById('collageCanvas');
  const ctx = canvas.getContext('2d');
  
  Array.from(files).forEach((file, i) => {
    const reader = new FileReader();
    reader.onload = (e) => {
      const img = new Image();
      img.onload = () => {
        const maxW = 180;
        const scale = Math.min(1, maxW / img.width);
        collageImages.push({
          img: img,
          x: 30 + (collageImages.length % 3) * 190,
          y: 30 + Math.floor(collageImages.length / 3) * 160,
          w: img.width * scale,
          h: img.height * scale
        });
        redrawCollage();
      };
      img.src = e.target.result;
    };
    reader.readAsDataURL(file);
  });
  input.value = '';
}

function redrawCollage() {
  const canvas = document.getElementById('collageCanvas');
  const ctx = canvas.getContext('2d');
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  collageImages.forEach(obj => {
    ctx.drawImage(obj.img, obj.x, obj.y, obj.w, obj.h);
  });
}

function initCollageDrag() {
  const canvas = document.getElementById('collageCanvas');
  if (!canvas) return;

  function getPos(e) {
    const rect = canvas.getBoundingClientRect();
    const scaleX = canvas.width / rect.width;
    const scaleY = canvas.height / rect.height;
    const clientX = e.touches ? e.touches[0].clientX : e.clientX;
    const clientY = e.touches ? e.touches[0].clientY : e.clientY;
    return { x: (clientX - rect.left) * scaleX, y: (clientY - rect.top) * scaleY };
  }

  canvas.addEventListener('mousedown', (e) => {
    const p = getPos(e);
    for (let i = collageImages.length - 1; i >= 0; i--) {
      const o = collageImages[i];
      if (p.x >= o.x && p.x <= o.x + o.w && p.y >= o.y && p.y <= o.y + o.h) {
        dragIndex = i;
        dragOffset = { x: p.x - o.x, y: p.y - o.y };
        break;
      }
    }
  });
  canvas.addEventListener('mousemove', (e) => {
    if (dragIndex < 0) return;
    const p = getPos(e);
    collageImages[dragIndex].x = p.x - dragOffset.x;
    collageImages[dragIndex].y = p.y - dragOffset.y;
    redrawCollage();
  });
  canvas.addEventListener('mouseup', () => { dragIndex = -1; });
  canvas.addEventListener('mouseleave', () => { dragIndex = -1; });

  // Touch
  canvas.addEventListener('touchstart', (e) => {
    e.preventDefault();
    const p = getPos(e);
    for (let i = collageImages.length - 1; i >= 0; i--) {
      const o = collageImages[i];
      if (p.x >= o.x && p.x <= o.x + o.w && p.y >= o.y && p.y <= o.y + o.h) {
        dragIndex = i;
        dragOffset = { x: p.x - o.x, y: p.y - o.y };
        break;
      }
    }
  }, {passive:false});
  canvas.addEventListener('touchmove', (e) => {
    if (dragIndex < 0) return;
    e.preventDefault();
    const p = getPos(e);
    collageImages[dragIndex].x = p.x - dragOffset.x;
    collageImages[dragIndex].y = p.y - dragOffset.y;
    redrawCollage();
  }, {passive:false});
  canvas.addEventListener('touchend', () => { dragIndex = -1; });
}

// clearCanvas for collage also clears images array
const _origClear = clearCanvas;
clearCanvas = function(id) {
  if (id === 'collageCanvas') collageImages = [];
  _origClear(id);
};

// ===== Спрайт-анимация =====
let spriteFrame = 0;
let spritePlaying = false;
let spriteTimer = null;

// 4 кадрлық қарапайым доп анимациясы (8x8 пиксель, масштабталған)
const spriteFrames = [
  // кадр 0 - доп солға
  [
    [0,0,0,1,1,0,0,0],
    [0,0,1,1,1,1,0,0],
    [0,1,1,1,1,1,1,0],
    [1,1,1,1,1,1,1,1],
    [1,1,1,1,1,1,1,1],
    [0,1,1,1,1,1,1,0],
    [0,0,1,1,1,1,0,0],
    [0,0,0,1,1,0,0,0]
  ],
  // кадр 1 - сәл қысылған
  [
    [0,0,0,0,0,0,0,0],
    [0,0,1,1,1,1,0,0],
    [0,1,1,1,1,1,1,0],
    [1,1,1,1,1,1,1,1],
    [1,1,1,1,1,1,1,1],
    [0,1,1,1,1,1,1,0],
    [0,0,1,1,1,1,0,0],
    [0,0,0,0,0,0,0,0]
  ],
  // кадр 2 - оңға
  [
    [0,0,0,1,1,0,0,0],
    [0,0,1,1,1,1,0,0],
    [0,1,1,1,1,1,1,0],
    [1,1,1,1,1,1,1,1],
    [1,1,1,1,1,1,1,1],
    [0,1,1,1,1,1,1,0],
    [0,0,1,1,1,1,0,0],
    [0,0,0,1,1,0,0,0]
  ],
  // кадр 3 - жоғары
  [
    [0,0,1,1,1,1,0,0],
    [0,1,1,1,1,1,1,0],
    [1,1,1,1,1,1,1,1],
    [1,1,1,1,1,1,1,1],
    [0,1,1,1,1,1,1,0],
    [0,0,1,1,1,1,0,0],
    [0,0,0,1,1,0,0,0],
    [0,0,0,0,0,0,0,0]
  ]
];

function drawSpriteFrame() {
  const canvas = document.getElementById('spriteCanvas');
  if (!canvas) return;
  const ctx = canvas.getContext('2d');
  const frame = spriteFrames[spriteFrame % spriteFrames.length];
  const scale = 12;
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  ctx.fillStyle = '#7c5cfc';
  for (let y = 0; y < 8; y++) {
    for (let x = 0; x < 8; x++) {
      if (frame[y][x]) {
        ctx.fillRect(12 + x * scale, 12 + y * scale, scale, scale);
      }
    }
  }
}

function toggleSprite() {
  const btn = document.getElementById('spritePlayBtn');
  if (spritePlaying) {
    clearInterval(spriteTimer);
    spritePlaying = false;
    btn.textContent = 'Ойнату';
  } else {
    spritePlaying = true;
    btn.textContent = 'Тоқтату';
    const speed = () => parseInt(document.getElementById('spriteSpeed').value) || 200;
    spriteTimer = setInterval(() => {
      spriteFrame = (spriteFrame + 1) % spriteFrames.length;
      drawSpriteFrame();
    }, speed());
    // speed change while playing
    document.getElementById('spriteSpeed').oninput = function() {
      document.getElementById('speedVal').textContent = this.value;
      if (spritePlaying) {
        clearInterval(spriteTimer);
        spriteTimer = setInterval(() => {
          spriteFrame = (spriteFrame + 1) % spriteFrames.length;
          drawSpriteFrame();
        }, parseInt(this.value));
      }
    };
  }
}

function initSpriteThumbs() {
  const container = document.getElementById('spriteThumbs');
  if (!container) return;
  container.innerHTML = '';
  spriteFrames.forEach((frame, i) => {
    const c = document.createElement('canvas');
    c.width = 48; c.height = 48;
    c.style.borderRadius = '6px';
    c.style.border = '1px solid var(--border)';
    c.style.cursor = 'pointer';
    c.title = 'Кадр ' + (i+1);
    const ctx = c.getContext('2d');
    ctx.fillStyle = '#1a2234';
    ctx.fillRect(0,0,48,48);
    ctx.fillStyle = '#7c5cfc';
    const s = 5;
    for (let y = 0; y < 8; y++)
      for (let x = 0; x < 8; x++)
        if (frame[y][x]) ctx.fillRect(4 + x*s, 4 + y*s, s, s);
    c.onclick = () => { spriteFrame = i; drawSpriteFrame(); };
    container.appendChild(c);
  });
}

// Бастапқы инициализация
document.addEventListener('DOMContentLoaded', () => {
  initCanvas('drawCanvas', 'drawColor', 'drawSize');
  initCanvas('landCanvas', 'landColor', 'landSize');
  updatePalette();
  rotateCube();
  initCollageDrag();
  drawSpriteFrame();
  initSpriteThumbs();
  const sp = document.getElementById('spriteSpeed');
  if (sp) sp.oninput = function() { document.getElementById('speedVal').textContent = this.value; };
});
</script>
</body>
</html>
