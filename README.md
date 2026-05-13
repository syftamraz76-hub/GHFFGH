<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>مُلهم | الصحيفة الإلكترونية للبودكاست السعودي</title>
  <link rel="icon" type="image/png" href="https://img.icons8.com/fluency-systems-filled/48/7A5A2E/microphone.png">
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;900&display=swap');

    :root{
      --bg:#F4F1EA;
      --brown:#7A5A2E;
      --olive:#7A856F;
      --text:#4E4A43;
    }

    html{scroll-behavior:smooth}
    body{
      font-family:'Tajawal',sans-serif;
      background:var(--bg);
      color:var(--text);
      overflow-x:hidden;
    }

    .soft{transition:all .22s ease}
    .glass{
      background:rgba(255,255,255,.76);
      backdrop-filter:blur(18px);
      -webkit-backdrop-filter:blur(18px);
    }

    .panel{
      display:none;
      min-height:100vh;
      animation:fadeIn .22s ease-out;
    }
    .panel.active{display:block}

    @keyframes fadeIn{
      from{opacity:0;transform:translateY(10px)}
      to{opacity:1;transform:translateY(0)}
    }

    .nav-btn.active{
      background:var(--brown);
      color:#fff;
      box-shadow:0 8px 24px rgba(122,90,46,.22);
    }

    .card-hover:hover{
      transform:translateY(-6px);
      box-shadow:0 18px 40px rgba(122,90,46,.12);
    }

    .chip{
      border:1px solid rgba(122,90,46,.10);
      background:rgba(122,90,46,.06);
      color:var(--brown);
    }

    .overlay-hidden{
      opacity:0;
      pointer-events:none;
      transform:translateY(14px) scale(.99);
    }
    .overlay-visible{
      opacity:1;
      pointer-events:auto;
      transform:translateY(0) scale(1);
    }

    .wm{
      position:absolute;
      inset:0;
      pointer-events:none;
      opacity:.13;
      display:flex;
      align-items:center;
      justify-content:center;
      font-weight:900;
      color:#fff;
      text-shadow:0 0 2px rgba(0,0,0,.15);
      mix-blend-mode:screen;
    }
    .wm span{
      transform:rotate(-16deg);
      border:2px solid rgba(255,255,255,.55);
      padding:.45rem 1rem;
      border-radius:999px;
      background:rgba(122,90,46,.35);
    }

    .question-badge{
      position:absolute;
      bottom:14px;
      right:14px;
      z-index:2;
      width:46px;
      height:46px;
      border-radius:999px;
      display:flex;
      align-items:center;
      justify-content:center;
      background:rgba(255,255,255,.92);
      color:var(--brown);
      font-size:1.5rem;
      font-weight:900;
      box-shadow:0 12px 30px rgba(0,0,0,.16)
    }

    .hero-cover{
      position:relative;
      overflow:hidden;
      border-radius:1.5rem;
    }
    .hero-cover::after{
      content:"مُلهم";
      position:absolute;
      top:14px;
      left:14px;
      z-index:2;
      color:#fff;
      font-weight:900;
      padding:.45rem .8rem;
      border-radius:999px;
      background:rgba(122,90,46,.78);
      box-shadow:0 8px 24px rgba(0,0,0,.18);
      font-size:.82rem
    }

    .search::placeholder{color:rgba(78,74,67,.55)}
    .detail-body p,.detail-rich p{
      margin-bottom:1rem;
      line-height:2.1;
    }
    .detail-rich{
      line-height:2.15;
    }

    .gallery-card{
      position:relative;
      overflow:hidden;
      border-radius:1.5rem;
      background:#eee;
      box-shadow:0 16px 32px rgba(122,90,46,.10);
    }
    .gallery-card img{
      width:100%;
      height:280px;
      object-fit:cover;
      display:block;
    }
    .gallery-card figcaption{
      position:absolute;
      left:0;
      right:0;
      bottom:0;
      background:linear-gradient(transparent, rgba(0,0,0,.6));
      color:#fff;
      padding:1rem 1rem .85rem;
      font-weight:700;
      font-size:.95rem;
    }
  </style>
</head>
<body class="min-h-screen">

  <div class="fixed inset-0 pointer-events-none -z-10 overflow-hidden opacity-[0.03]">
    <div class="absolute top-0 left-0 w-full h-full bg-[radial-gradient(circle_at_top_left,#7A856F,transparent_40%)]"></div>
    <div class="absolute bottom-0 right-0 w-full h-full bg-[radial-gradient(circle_at_bottom_right,#7A5A2E,transparent_40%)]"></div>
  </div>

  <div id="toastContainer" class="fixed bottom-5 left-5 z-[200] space-y-3 pointer-events-none"></div>

  <header class="sticky top-0 z-[80] glass border-b border-black/5">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 py-4 flex items-center justify-between gap-4">
      <div class="flex items-center gap-3">
        <div class="w-12 h-12 rounded-2xl bg-[#7A5A2E] text-white flex items-center justify-center shadow-lg">
          <span class="text-xl font-black">🎙</span>
        </div>
        <div>
          <h1 class="text-2xl sm:text-3xl font-black text-[#7A5A2E] leading-none">مُلهم</h1>
          <p class="text-sm text-[#7A856F] mt-1">الصحيفة الإلكترونية للبودكاست السعودي</p>
        </div>
      </div>

      <button id="devBtn" type="button" class="inline-flex items-center justify-center w-12 h-12 rounded-2xl border border-[#7A5A2E]/15 bg-white/80 text-[#7A5A2E] shadow-sm hover:shadow-md soft" aria-label="المطورون">
        <svg viewBox="0 0 24 24" class="w-5 h-5 fill-none stroke-current stroke-[1.8]">
          <rect x="3" y="4" width="18" height="13" rx="2"></rect>
          <path d="M8 20h8"></path>
          <path d="M12 17v3"></path>
        </svg>
      </button>
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 pb-4">
      <nav class="flex flex-wrap items-center gap-2 justify-start">
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="home">الرئيسية</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="news">أخبار</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="reports">تقارير</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="articles">مقال</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="investigations">تحقيق</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="programs">البرامج</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="interactive">تفاعلي</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="videos">فيديو</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="references">المراجع</button>
      </nav>
    </div>
  </header>

  <main class="relative z-10">
    <section id="panel-home" class="panel active">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-8 md:py-10">
        <div class="rounded-[2rem] overflow-hidden border border-white/60 shadow-[0_24px_70px_rgba(122,90,46,.10)] bg-gradient-to-b from-[#E7DED2] to-[#F4F1EA]">
          <div class="relative px-6 sm:px-10 py-16 md:py-24 text-center">
            <div class="absolute inset-0 opacity-20">
              <div class="absolute w-[650px] h-[650px] bg-[#7A856F] rounded-full blur-3xl top-[-220px] right-[-200px] animate-pulse"></div>
              <div class="absolute w-[500px] h-[500px] bg-[#7A5A2E] rounded-full blur-3xl bottom-[-180px] left-[-120px] animate-pulse"></div>
            </div>
            <div class="relative z-10 max-w-5xl mx-auto">
              <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/70 border border-white/50 shadow-sm text-[#7A5A2E] font-bold mb-6">
                <span>مُلهم.. نغوص في كواليس البودكاست السعودي لننقل لكم سر البدايات</span>
              </div>
              <h2 class="text-5xl sm:text-7xl md:text-8xl font-black text-[#7A5A2E] leading-tight mb-6">مُلهم.. الصفحة الأولى في عالم البودكاست السعودي</h2>
              <p class="text-xl md:text-2xl leading-loose text-[#7A856F] max-w-4xl mx-auto">
                صحيفة إلكترونية فخمة ومقسّمة بوضوح إلى أخبار وتقارير ومقالات وتحقيقات وبرامج ومراجع وفيديو وتفاعل، وكلها تدور حول البودكاست السعودي فقط.
              </p>
              <div class="mt-10 flex flex-wrap justify-center gap-4">
                <button class="jump-btn bg-[#7A5A2E] text-white px-7 py-4 rounded-2xl text-lg font-bold shadow-xl hover:scale-[1.03] soft" data-panel="news">تصفّح الأخبار</button>
                <button class="jump-btn border-2 border-[#7A856F] text-[#7A856F] px-7 py-4 rounded-2xl text-lg font-bold hover:bg-[#7A856F] hover:text-white soft" data-panel="programs">البرامج</button>
              </div>
            </div>
          </div>
        </div>

        <div class="mt-8 py-4 overflow-hidden bg-white rounded-2xl border border-black/5 shadow-sm">
          <div class="quote whitespace-nowrap flex gap-16 px-6 text-2xl font-black text-[#7A5A2E]">
            <span>مُلهم.. نبض البودكاست السعودي</span>
            <span>صوت السعودية المسموع.. يرويه لكم مُلهم</span>
            <span>من قلب المملكة.. مُلهم يكتب تاريخ الصوت السعودي</span>
            <span>هنا نؤرخ للكلمة المسموعة.. كيف بدأ الحلم وصار بودكاست</span>
            <span>مُلهم.. حيث يبدأ الإلهام السعودي</span>
          </div>
        </div>

        <div class="grid lg:grid-cols-3 gap-6 mt-8">
          <div class="bg-white rounded-3xl p-6 shadow-xl border border-black/5 card-hover soft">
            <div class="w-14 h-14 rounded-2xl bg-[#7A5A2E]/10 text-[#7A5A2E] flex items-center justify-center text-2xl mb-4">📰</div>
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">صحيفة مكتملة العناصر</h3>
            <p class="text-lg leading-8 text-[#5d594f]">أخبار، تقارير، مقال، تحقيق، برامج، مراجع، وفيديو داخل تصميم واحد متناسق.</p>
          </div>
          <div class="bg-white rounded-3xl p-6 shadow-xl border border-black/5 card-hover soft">
            <div class="w-14 h-14 rounded-2xl bg-[#7A856F]/10 text-[#7A856F] flex items-center justify-center text-2xl mb-4">🎧</div>
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">برامج سعودية واضحة</h3>
            <p class="text-lg leading-8 text-[#5d594f]">بطاقات برامج بعرض بصري خاص، ووصف كامل وصور مخصصة لكل برنامج.</p>
          </div>
          <div class="bg-white rounded-3xl p-6 shadow-xl border border-black/5 card-hover soft">
            <div class="w-14 h-14 rounded-2xl bg-[#7A5A2E]/10 text-[#7A5A2E] flex items-center justify-center text-2xl mb-4">⚡</div>
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">تفاعل حي وسريع</h3>
            <p class="text-lg leading-8 text-[#5d594f]">بودكاست اليوم، المود، التصويت، الاقتباس، والاختبار تعمل مباشرة.</p>
          </div>
        </div>
      </div>
    </section>

    <section id="panel-news" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="text-4xl md:text-5xl font-black text-[#7A5A2E]">أخبار</h2>
            <p class="text-[#7A856F] mt-3 text-lg">أخبار تحريرية عن البودكاست السعودي وبرامجه الأبرز.</p>
          </div>
          <div class="px-4 py-2 rounded-full bg-white border border-black/5 shadow-sm font-bold text-[#7A5A2E]">تغطية يومية</div>
        </div>
        <div id="newsGrid" class="grid md:grid-cols-2 xl:grid-cols-3 gap-6"></div>
      </div>
    </section>

    <section id="panel-reports" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="text-4xl md:text-5xl font-black text-[#7A5A2E]">تقارير</h2>
            <p class="text-[#7A856F] mt-3 text-lg">تقارير صحفية تشرح التحولات والاتجاهات.</p>
          </div>
        </div>
        <div id="reportsGrid" class="grid md:grid-cols-2 gap-6"></div>
      </div>
    </section>

    <section id="panel-articles" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="text-4xl md:text-5xl font-black text-[#7A5A2E]">مقال</h2>
            <p class="text-[#7A856F] mt-3 text-lg">مقالات رأي وتفسير عن البودكاست السعودي.</p>
          </div>
        </div>
        <div id="articlesGrid" class="grid md:grid-cols-3 gap-6"></div>
      </div>
    </section>

    <section id="panel-investigations" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="text-4xl md:text-5xl font-black text-[#7A5A2E]">تحقيق</h2>
            <p class="text-[#7A856F] mt-3 text-lg">تحقيقات صحفية بزاوية أعمق وأكثر سؤالًا.</p>
          </div>
        </div>
        <div id="investigationsGrid" class="grid md:grid-cols-3 gap-6"></div>
      </div>
    </section>

    <section id="panel-programs" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="text-4xl md:text-5xl font-black text-[#7A5A2E]">البرامج</h2>
            <p class="text-[#7A856F] mt-3 text-lg">كل برنامج له صورة مخصصة ووصف كامل عند الفتح.</p>
          </div>
          <label class="relative w-full md:w-[360px]">
            <input id="programSearch" type="search" placeholder="ابحث عن برنامج..." class="search w-full bg-white border border-black/10 rounded-2xl px-5 py-4 pr-12 text-lg outline-none focus:border-[#7A5A2E] soft shadow-sm">
            <span class="absolute right-4 top-1/2 -translate-y-1/2 text-[#7A856F]">⌕</span>
          </label>
        </div>

        <div class="flex flex-wrap items-center gap-3 mb-8">
          <button id="toggleExtraBtn" type="button" class="bg-[#7A856F] text-white px-6 py-4 rounded-2xl font-black shadow-xl hover:scale-[1.03] soft">إظهار المزيد</button>
          <div class="flex items-center gap-2 text-[#7A856F] font-bold">
            <span class="inline-flex items-center justify-center w-9 h-9 rounded-xl bg-white border border-black/5">▶</span>
            <span>روابط رسمية لكل برنامج</span>
          </div>
        </div>

        <div id="programGrid" class="grid sm:grid-cols-2 xl:grid-cols-4 gap-6"></div>

        <div id="extraWrap" class="hidden mt-10">
          <div class="flex items-center justify-between gap-4 flex-wrap mb-6">
            <h3 class="text-3xl font-black text-[#7A5A2E]">برامج إضافية</h3>
          </div>
          <div id="extraGrid" class="grid sm:grid-cols-2 xl:grid-cols-4 gap-6"></div>
        </div>
      </div>
    </section>

    <section id="panel-interactive" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="text-4xl md:text-5xl font-black text-[#7A5A2E]">تفاعلي</h2>
            <p class="text-[#7A856F] mt-3 text-lg">أزرار، تصويت، ترشيحات، وواجهة حية للزائر.</p>
          </div>
        </div>

        <div class="grid lg:grid-cols-3 gap-6">
          <div class="bg-white rounded-[2rem] p-7 shadow-xl border border-black/5">
            <span class="text-6xl block mb-4">🎧</span>
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">بودكاست اليوم</h3>
            <p class="text-lg leading-8 text-[#5d594f] mb-5">كل دخول يعرض ترشيحًا مختلفًا مع وصف مختصر.</p>
            <button id="recommendBtn" type="button" class="bg-[#7A5A2E] text-white px-5 py-4 rounded-2xl font-black w-full shadow-xl hover:scale-[1.03] soft">اقترح لي برنامجًا</button>
            <div id="recommendBox" class="hidden mt-5 rounded-3xl p-5 bg-[#F4F1EA] border border-[#7A5A2E]/10">
              <h4 id="recommendTitle" class="text-2xl font-black text-[#7A5A2E] mb-2"></h4>
              <p id="recommendText" class="text-[#5d594f] leading-8"></p>
              <button id="openRecommended" type="button" class="mt-4 bg-[#7A856F] text-white px-5 py-3 rounded-2xl font-black w-full">فتح البطاقة</button>
            </div>
          </div>

          <div class="bg-white rounded-[2rem] p-7 shadow-xl border border-black/5">
            <span class="text-6xl block mb-4">💡</span>
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">اختر مودك</h3>
            <p class="text-lg leading-8 text-[#5d594f] mb-5">أبي أضحك، أبي أفكر، أبي شيء نفسي، أبي تشويق.</p>
            <div class="grid grid-cols-2 gap-2">
              <button type="button" class="mood-btn bg-[#7A5A2E]/10 hover:bg-[#7A5A2E] hover:text-white text-[#7A5A2E] px-3 py-3 rounded-xl font-bold soft" data-mood="ضحك">أبي أضحك</button>
              <button type="button" class="mood-btn bg-[#7A5A2E]/10 hover:bg-[#7A5A2E] hover:text-white text-[#7A5A2E] px-3 py-3 rounded-xl font-bold soft" data-mood="تفكير">أبي أفكر</button>
              <button type="button" class="mood-btn bg-[#7A5A2E]/10 hover:bg-[#7A5A2E] hover:text-white text-[#7A5A2E] px-3 py-3 rounded-xl font-bold soft" data-mood="نفسي">أبي شيء نفسي</button>
              <button type="button" class="mood-btn bg-[#7A5A2E]/10 hover:bg-[#7A5A2E] hover:text-white text-[#7A5A2E] px-3 py-3 rounded-xl font-bold soft" data-mood="تشويق">أبي تشويق</button>
            </div>
            <div class="mt-5 bg-[#F4F1EA] rounded-2xl p-4 border border-[#7A5A2E]/10">
              <div class="text-sm text-[#7A856F] mb-1">المود الحالي</div>
              <div id="currentMood" class="text-2xl font-black text-[#7A5A2E]">ضحك</div>
            </div>
          </div>

          <div class="bg-white rounded-[2rem] p-7 shadow-xl border border-black/5">
            <span class="text-6xl block mb-4">🗳</span>
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">صوّت لأفضل بودكاست سعودي</h3>
            <p class="text-lg leading-8 text-[#5d594f] mb-5">تصويت مباشر داخل الصفحة، والنتيجة تتحدث فورًا.</p>
            <button id="openVoteBtn" type="button" class="bg-white border-2 border-[#7A5A2E] text-[#7A5A2E] px-5 py-4 rounded-2xl font-black w-full hover:bg-[#7A5A2E] hover:text-white soft">ابدأ التصويت</button>
            <div class="mt-5 space-y-3 text-right bg-[#F4F1EA] rounded-3xl p-5 border border-[#7A5A2E]/10">
              <div class="flex justify-between"><span>فنجان</span><span id="voteFanjan">0</span></div>
              <div class="flex justify-between"><span>جناية</span><span id="voteJinaya">0</span></div>
              <div class="flex justify-between"><span>The Mo Show</span><span id="voteMosho">0</span></div>
              <div class="flex justify-between"><span>سرديات</span><span id="voteSardyat">0</span></div>
            </div>
          </div>
        </div>

        <div class="grid lg:grid-cols-3 gap-6 mt-6">
          <div class="bg-white rounded-[2rem] p-7 shadow-xl border border-black/5">
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">كم ساعة تسمع بودكاست بالأسبوع؟</h3>
            <input id="hoursSlider" type="range" min="0" max="40" value="8" class="w-full">
            <div class="flex justify-between text-sm text-[#7A856F] mt-2"><span>0</span><span>40</span></div>
            <div class="mt-4 rounded-2xl bg-[#F4F1EA] border border-[#7A5A2E]/10 p-4">
              <div class="text-sm text-[#7A856F]">عدد الساعات</div>
              <div id="hoursValue" class="text-3xl font-black text-[#7A5A2E]">8 ساعة</div>
            </div>
          </div>

          <div class="bg-white rounded-[2rem] p-7 shadow-xl border border-black/5">
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">اقتباس اليوم</h3>
            <div id="quoteBox" class="rounded-3xl bg-[#F4F1EA] border border-[#7A5A2E]/10 p-5 leading-9 text-lg text-[#5d594f]">“مو كل صمت راحة.”</div>
            <button id="nextQuoteBtn" type="button" class="mt-4 bg-[#7A856F] text-white px-5 py-3 rounded-2xl font-black w-full">اقتباس جديد</button>
          </div>

          <div class="bg-white rounded-[2rem] p-7 shadow-xl border border-black/5">
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">اختبر شخصيتك: أي بودكاست يشبهك؟</h3>
            <div class="grid grid-cols-2 gap-2">
              <button type="button" class="quiz-btn bg-[#7A5A2E]/10 text-[#7A5A2E] px-3 py-3 rounded-xl font-bold soft" data-result="fanjan">تفكير عميق</button>
              <button type="button" class="quiz-btn bg-[#7A5A2E]/10 text-[#7A5A2E] px-3 py-3 rounded-xl font-bold soft" data-result="jinaya">تشويق</button>
              <button type="button" class="quiz-btn bg-[#7A5A2E]/10 text-[#7A5A2E] px-3 py-3 rounded-xl font-bold soft" data-result="kanbat">شيء نفسي</button>
              <button type="button" class="quiz-btn bg-[#7A5A2E]/10 text-[#7A5A2E] px-3 py-3 rounded-xl font-bold soft" data-result="abjora">تطوير ذات</button>
            </div>
            <div id="quizResult" class="mt-4 rounded-2xl bg-[#F4F1EA] border border-[#7A5A2E]/10 p-4">اختر إجابة لتظهر النتيجة.</div>
          </div>
        </div>

        <div class="grid lg:grid-cols-2 gap-6 mt-6">
          <div class="bg-white rounded-[2rem] p-7 shadow-xl border border-black/5">
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">ترشيحات حسب مودك</h3>
            <div id="moodRecommendation" class="rounded-3xl bg-[#F4F1EA] border border-[#7A5A2E]/10 p-5">اضغط أحد الأزرار بالأعلى لاختيار مزاجك.</div>
          </div>

          <div class="bg-white rounded-[2rem] p-7 shadow-xl border border-black/5">
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">خريطة المنصات</h3>
            <div class="grid sm:grid-cols-3 gap-4">
              <div class="rounded-3xl p-4 bg-[#F4F1EA] border border-black/5">
                <div class="font-black text-lg text-[#7A5A2E] flex items-center gap-2"><span>🍎</span>Apple Podcasts</div>
                <div class="text-sm text-[#5d594f] mt-2">الصفحات الرسمية للحلقات والبرامج.</div>
              </div>
              <div class="rounded-3xl p-4 bg-[#F4F1EA] border border-black/5">
                <div class="font-black text-lg text-[#7A5A2E] flex items-center gap-2"><span>🟢</span>Spotify</div>
                <div class="text-sm text-[#5d594f] mt-2">خيار شائع للاستماع أثناء الحركة.</div>
              </div>
              <div class="rounded-3xl p-4 bg-[#F4F1EA] border border-black/5">
                <div class="font-black text-lg text-[#7A5A2E] flex items-center gap-2"><span>▶</span>YouTube</div>
                <div class="text-sm text-[#5d594f] mt-2">للمشاهد المرئية والمقاطع القصيرة.</div>
              </div>
            </div>
          </div>
        </div>

        <div class="mt-6 bg-[#7A5A2E] text-white rounded-[2rem] p-8 shadow-2xl">
          <p class="text-2xl md:text-3xl font-black leading-relaxed">“مُلهم.. حيث يبدأ الإلهام السعودي، ويُكتب تاريخ الصوت من قلب المملكة.”</p>
        </div>
      </div>
    </section>

    <section id="panel-videos" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="text-4xl md:text-5xl font-black text-[#7A5A2E]">فيديو</h2>
            <p class="text-[#7A856F] mt-3 text-lg">مقاطع يوتيوب مرتبطة بعالم البودكاست السعودي.</p>
          </div>
          <div class="flex items-center gap-3 text-[#7A5A2E] font-bold">
            <span class="inline-flex items-center justify-center w-9 h-9 rounded-xl bg-white border border-black/5">▶</span>
            <span>YouTube</span>
          </div>
        </div>
        <div id="videoGrid" class="grid lg:grid-cols-2 gap-6"></div>
      </div>
    </section>

    <section id="panel-references" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="text-4xl md:text-5xl font-black text-[#7A5A2E]">المراجع</h2>
            <p class="text-[#7A856F] mt-3 text-lg">مرتب حسب المحتوى؛ العنوان ثم نوع المادة ثم المصدر.</p>
          </div>
        </div>
        <div id="referencesGrid" class="grid gap-6"></div>
      </div>
    </section>

    <section id="panel-detail" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-8 md:py-10">
        <div class="flex items-center justify-between gap-4 mb-6">
          <button id="detailBackBtn" type="button" class="px-5 py-3 rounded-2xl bg-white border border-black/5 font-black text-[#7A5A2E] shadow-sm hover:shadow-md soft">عودة</button>
          <div class="font-black text-[#7A856F]">مُلهم</div>
        </div>

        <div class="bg-white rounded-[2rem] overflow-hidden shadow-[0_24px_70px_rgba(122,90,46,.10)] border border-black/5 relative">
          <div id="detailTopFlag" class="hidden question-badge">؟</div>
          <div class="grid lg:grid-cols-5">
            <div class="lg:col-span-2">
              <div class="hero-cover">
                <img id="detailHero" src="" alt="" class="w-full h-full min-h-[280px] lg:min-h-[100%] object-cover">
                <div class="wm"><span>مُلهم</span></div>
              </div>
            </div>

            <div class="lg:col-span-3 p-6 md:p-8 lg:p-10">
              <div class="flex flex-wrap items-center gap-3 mb-4">
                <span id="detailLabel" class="px-3 py-1 rounded-full bg-[#7A5A2E]/10 text-[#7A5A2E] font-black text-sm"></span>
                <span id="detailMeta" class="text-sm text-[#7A856F] font-bold"></span>
                <span id="detailType" class="text-sm text-[#7A856F] font-bold"></span>
              </div>
              <h2 id="detailTitle" class="text-4xl md:text-5xl font-black text-[#7A5A2E] leading-tight"></h2>
              <p id="detailLead" class="mt-5 text-xl md:text-2xl leading-loose text-[#5d594f]"></p>

              <div id="detailBody" class="detail-body mt-8"></div>

              <div class="mt-8">
                <button id="expandBtn" type="button" class="bg-[#7A856F] text-white px-6 py-4 rounded-2xl font-black shadow-lg hover:scale-[1.02] soft">اقرأ المزيد</button>
              </div>

              <div id="detailBullets" class="flex flex-wrap gap-2 mt-6"></div>
              <div id="detailLinks" class="flex flex-wrap gap-3 mt-8"></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="panel-more" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-8 md:py-10">
        <div class="flex items-center justify-between gap-4 mb-6">
          <button id="moreBackBtn" type="button" class="px-5 py-3 rounded-2xl bg-white border border-black/5 font-black text-[#7A5A2E] shadow-sm hover:shadow-md soft">رجوع</button>
          <div class="font-black text-[#7A856F]">مُلهم</div>
        </div>

        <div class="bg-white rounded-[2rem] overflow-hidden shadow-[0_24px_70px_rgba(122,90,46,.10)] border border-black/5">
          <div class="grid lg:grid-cols-5">
            <div class="lg:col-span-2">
              <div class="hero-cover">
                <img id="moreHero" src="" alt="" class="w-full h-full min-h-[280px] lg:min-h-[100%] object-cover">
                <div class="wm"><span>مُلهم</span></div>
              </div>
            </div>
            <div class="lg:col-span-3 p-6 md:p-8 lg:p-10">
              <div class="flex flex-wrap items-center gap-3 mb-4">
                <span id="moreLabel" class="px-3 py-1 rounded-full bg-[#7A5A2E]/10 text-[#7A5A2E] font-black text-sm"></span>
                <span id="moreMeta" class="text-sm text-[#7A856F] font-bold"></span>
              </div>
              <h2 id="moreTitle" class="text-4xl md:text-5xl font-black text-[#7A5A2E] leading-tight"></h2>
              <p id="moreIntro" class="mt-5 text-xl md:text-2xl leading-loose text-[#5d594f]"></p>
            </div>
          </div>
        </div>

        <div id="moreBody" class="mt-8"></div>
      </div>
    </section>
  </main>

  <div id="devModal" class="fixed inset-0 z-[130] flex items-center justify-center p-4 hidden overlay-hidden soft">
    <div class="absolute inset-0 bg-black/65 backdrop-blur-sm" data-close="dev"></div>
    <div class="relative z-10 w-full max-w-2xl bg-white rounded-[2rem] shadow-2xl overflow-hidden border border-black/5">
      <div class="p-6 md:p-8">
        <div class="flex items-start justify-between gap-4 mb-5">
          <div>
            <div class="text-sm text-[#7A856F] font-bold mb-2">مطورين الموقع</div>
            <h3 class="text-3xl md:text-4xl font-black text-[#7A5A2E]">فريق مُلهم</h3>
          </div>
          <button type="button" class="w-11 h-11 rounded-full bg-black/5 hover:bg-black/10 soft text-2xl leading-none" data-close="dev">×</button>
        </div>
        <div class="grid gap-4">
          <div class="rounded-2xl p-4 border border-black/5 bg-[#F4F1EA] flex items-center justify-between"><span class="font-black text-lg text-[#7A5A2E]">عهد المحمدي</span><span class="font-bold text-[#4E4A43]">4556365</span></div>
          <div class="rounded-2xl p-4 border border-black/5 bg-[#F4F1EA] flex items-center justify-between"><span class="font-black text-lg text-[#7A5A2E]">علياء العوفي</span><span class="font-bold text-[#4E4A43]">4553854</span></div>
          <div class="rounded-2xl p-4 border border-black/5 bg-[#F4F1EA] flex items-center justify-between"><span class="font-black text-lg text-[#7A5A2E]">كوثر المطرفي</span><span class="font-bold text-[#4E4A43]">4550073</span></div>
          <div class="rounded-2xl p-4 border border-black/5 bg-[#F4F1EA] flex items-center justify-between"><span class="font-black text-lg text-[#7A5A2E]">ساره الحربي</span><span class="font-bold text-[#4E4A43]">4555801</span></div>
          <div class="rounded-2xl p-4 border border-black/5 bg-[#F4F1EA] flex items-center justify-between"><span class="font-black text-lg text-[#7A5A2E]">هديل الحربي</span><span class="font-bold text-[#4E4A43]">4554545</span></div>
        </div>
        <div class="mt-6 rounded-2xl bg-[#7A5A2E] text-white p-5">
          <div class="font-black text-lg">شعبة F7</div>
          <div class="text-white/90 mt-1">دكتور المقرر : خالد القحطاني</div>
        </div>
      </div>
    </div>
  </div>

  <div id="voteModal" class="fixed inset-0 z-[128] flex items-center justify-center p-4 hidden overlay-hidden soft">
    <div class="absolute inset-0 bg-black/65 backdrop-blur-sm" data-close="vote"></div>
    <div class="relative z-10 w-full max-w-xl bg-white rounded-[2rem] shadow-2xl overflow-hidden border border-black/5">
      <div class="p-6 md:p-8">
        <div class="flex items-start justify-between gap-4 mb-5">
          <div>
            <div class="text-sm text-[#7A856F] font-bold mb-2">تصويت مباشر</div>
            <h3 class="text-3xl font-black text-[#7A5A2E]">اختر برنامجك المفضل</h3>
          </div>
          <button type="button" class="w-11 h-11 rounded-full bg-black/5 hover:bg-black/10 soft text-2xl leading-none" data-close="vote">×</button>
        </div>
        <form id="voteForm" class="space-y-3">
          <label class="block">
            <input type="radio" name="vote" value="fanjan" class="peer sr-only" checked>
            <div class="cursor-pointer rounded-2xl border border-black/10 p-4 peer-checked:border-[#7A5A2E] peer-checked:bg-[#7A5A2E]/5 soft">
              <div class="flex items-center justify-between gap-4"><span class="font-black text-lg">فنجان</span><span class="text-sm px-3 py-1 rounded-full bg-[#7A5A2E]/10 text-[#7A5A2E]">حوار</span></div>
            </div>
          </label>
          <label class="block">
            <input type="radio" name="vote" value="jinaya" class="peer sr-only">
            <div class="cursor-pointer rounded-2xl border border-black/10 p-4 peer-checked:border-[#7A5A2E] peer-checked:bg-[#7A5A2E]/5 soft">
              <div class="flex items-center justify-between gap-4"><span class="font-black text-lg">جناية</span><span class="text-sm px-3 py-1 rounded-full bg-[#7A5A2E]/10 text-[#7A5A2E]">تشويق</span></div>
            </div>
          </label>
          <label class="block">
            <input type="radio" name="vote" value="mosho" class="peer sr-only">
            <div class="cursor-pointer rounded-2xl border border-black/10 p-4 peer-checked:border-[#7A5A2E] peer-checked:bg-[#7A5A2E]/5 soft">
              <div class="flex items-center justify-between gap-4"><span class="font-black text-lg">The Mo Show</span><span class="text-sm px-3 py-1 rounded-full bg-[#7A5A2E]/10 text-[#7A5A2E]">ثقافة</span></div>
            </div>
          </label>
          <label class="block">
            <input type="radio" name="vote" value="sardyat" class="peer sr-only">
            <div class="cursor-pointer rounded-2xl border border-black/10 p-4 peer-checked:border-[#7A5A2E] peer-checked:bg-[#7A5A2E]/5 soft">
              <div class="flex items-center justify-between gap-4"><span class="font-black text-lg">سرديات</span><span class="text-sm px-3 py-1 rounded-full bg-[#7A5A2E]/10 text-[#7A5A2E]">سرد</span></div>
            </div>
          </label>
          <div class="pt-3 flex flex-wrap gap-3">
            <button type="submit" class="bg-[#7A5A2E] text-white px-6 py-3 rounded-2xl font-black hover:scale-[1.03] soft">صوّت</button>
            <button type="button" class="bg-[#7A856F] text-white px-6 py-3 rounded-2xl font-black hover:scale-[1.03] soft" data-close="vote">إغلاق</button>
          </div>
        </form>
        <div id="voteDone" class="hidden mt-6 rounded-2xl bg-[#F4F1EA] border border-[#7A5A2E]/10 p-5">
          <div class="font-black text-2xl text-[#7A5A2E] mb-2">شكراً لصوتك</div>
          <p class="text-[#5d594f] leading-8 mb-4">تم تسجيل التصويت داخل الجلسة الحالية.</p>
          <div class="space-y-2 text-lg">
            <div class="flex justify-between"><span>فنجان</span><span id="resFanjan">0</span></div>
            <div class="flex justify-between"><span>جناية</span><span id="resJinaya">0</span></div>
            <div class="flex justify-between"><span>The Mo Show</span><span id="resMosho">0</span></div>
            <div class="flex justify-between"><span>سرديات</span><span id="resSardyat">0</span></div>
          </div>
        </div>
      </div>
    </div>
  </div>

<script>
document.addEventListener('DOMContentLoaded', () => {
  const htmlEscape = (s='') => String(s).replace(/[&<>"']/g, m => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[m]));
  const textToParagraphs = (txt='') => String(txt)
    .split(/\n+/)
    .map(s => s.trim())
    .filter(Boolean)
    .map(p => `<p>${htmlEscape(p)}</p>`)
    .join('');
  const listToChips = (arr=[]) => arr.map(b => `<span class="px-3 py-1 rounded-full text-sm font-bold chip">${htmlEscape(b)}</span>`).join('');
  const galleryImg = (url, caption='') => `
    <figure class="gallery-card">
      <img src="${url}" alt="">
      ${caption ? `<figcaption>${htmlEscape(caption)}</figcaption>` : ''}
    </figure>
  `;

  const data = {
    news: [
      {
        id:'n1', section:'news', title:'كيف أصبح البودكاست جزءًا من الحياة اليومية السعودية؟', label:'خبر صحفي',
        image:'https://images.unsplash.com/photo-1516280440614-37939bbacd81?auto=format&fit=crop&q=80&w=1400',
        excerpt:'شهد البودكاست في السعودية انتشارًا واسعًا خلال السنوات الأخيرة، بعدما تحوّل من تجربة جانبية إلى عادة يومية لدى كثير من الناس.',
        lead:'شهد البودكاست في السعودية انتشارًا واسعًا خلال السنوات الأخيرة، بعدما تحوّل من تجربة جانبية إلى عادة يومية لدى كثير من الناس، خاصة أثناء القيادة والعمل وقبل النوم.',
        summary:[
          'شهد البودكاست في السعودية انتشارًا واسعًا خلال السنوات الأخيرة، بعدما تحوّل من تجربة جانبية إلى عادة يومية لدى كثير من الناس، خاصة أثناء القيادة والعمل وقبل النوم.',
          'ويرى متابعون أن سهولة الاستماع وتنوع المحتوى أسهما في زيادة الإقبال عليه، ليصبح وسيلة تجمع بين الترفيه والمعرفة في وقت واحد.',
          'كما أسهمت البرامج السعودية الناجحة في ترسيخ هذا الحضور، بعدما قدّمت حوارات وسرديات تتناسب مع اهتمامات جمهور واسع.'
        ],
        bullets:['استماع يومي','مرونة عالية','صوت ومعرفة'],
        sources:[
          {title:'فنجان - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827'},
          {title:'بحث عن بودكاست سعودي', url:'https://podcasts.apple.com/us/search?term=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%B3%D8%B9%D9%88%D8%AF%D9%8A'}
        ],
        more:{
          intro:'البودكاست السعودي لم يعد محتوى جانبيًا، بل صار جزءًا من حياة كثير من المستمعين اليومية، وهو ما توضحه هذه الصياغة الكاملة.',
          body:[
            { paragraphs:[
              'شهد البودكاست في السعودية انتشارًا واسعًا خلال السنوات الأخيرة، بعدما تحوّل من تجربة جانبية إلى عادة يومية لدى كثير من الناس، خاصة أثناء القيادة والعمل وقبل النوم.'
            ]},
            { paragraphs:[
              'ويرى متابعون أن سهولة الاستماع وتنوع المحتوى أسهما في زيادة الإقبال عليه، ليصبح وسيلة تجمع بين الترفيه والمعرفة في وقت واحد.',
              'كما ساعدت البرامج السعودية الناجحة في تثبيت هذا الحضور من خلال حوارات واضحة وسرد متقن وموضوعات تلامس الاهتمام اليومي للمستمع.'
            ]},
            { paragraphs:[
              'ويظهر أثر ذلك في تنوع أوقات الاستماع، إذ لم يعد البودكاست مرتبطًا بوقت محدد، بل أصبح رفيقًا لحظات مختلفة من اليوم.',
              'ويحافظ الخبر هنا على الدقة والموضوعية، ويجيب عن الأسئلة الأساسية بوضوح من دون حشو أو خاتمة إنشائية.'
            ]}
          ],
          images:[
            'https://images.unsplash.com/photo-1501386761578-eac5c94b800a?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'ينتهي الخبر هنا بصياغة خبرية متوازنة تتدرج من الأهم إلى الأقل أهمية، من دون إضافات خارج سياق الخبر.'
        }
      },
      {
        id:'n2', section:'news', title:'لماذا تجذب الحلقات المرئية جمهورًا أكبر؟', label:'خبر صحفي',
        image:'https://images.unsplash.com/photo-1524504388940-b1c1722653e1?auto=format&fit=crop&q=80&w=1400',
        excerpt:'الصورة صارت تكمل الصوت في كثير من البرامج، والجمهور صار يفضّل التجربة المزدوجة عندما تخدم الفكرة.',
        lead:'الصورة في البودكاست المرئي صارت عنصراً مساعدًا يضيف سياقًا وحضورًا، من دون أن يلغي قيمة الصوت.',
        summary:[
          'أصبح البودكاست المرئي جذابًا لأنه يضيف الصورة إلى الصوت، فيرى المتابع لغة الجسد والجو العام للحوار.',
          'ورغم أهمية الصورة، يبقى نجاح الحلقة مرتبطًا بجودة الفكرة وطريقة تقديمها.',
          'وهذا ما جعل البودكاست المرئي خيارًا مناسبًا للجمهور الذي ينتقل بين المشاهدة والاستماع بسهولة.'
        ],
        bullets:['صوت + صورة','حضور بصري','إخراج متوازن'],
        sources:[
          {title:'YouTube search - بودكاست مرئي سعودي', url:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D9%85%D8%B1%D8%A6%D9%8A+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A'}
        ],
        more:{
          intro:'هذا الخبر يعرض أثر الصورة في تعزيز التجربة الصوتية، ثم يشرح لماذا ينجح الشكل المرئي حين يكون في خدمة الفكرة.',
          body:[
            { paragraphs:['الصورة صارت تكمل الصوت في كثير من البرامج، والجمهور صار يفضّل التجربة المزدوجة عندما تخدم الفكرة.']},
            { paragraphs:[
              'في الحلقات المرئية، يكتسب المتابع تفاصيل إضافية من الإضاءة والديكور وحركة الضيف ونبرة التقديم.',
              'لكن هذا كله لا يكفي وحده، لأن الفكرة والحوار يظلان أساس النجاح.'
            ]},
            { paragraphs:[
              'ويعكس انتشار هذا الشكل في السعودية رغبة الجمهور في تنويع التجربة بين السماع والمشاهدة.',
              'والخبر هنا يلتزم بالترتيب الخبرى الصحيح: أهم معلومة ثم أبرز واقعة ثم التفاصيل المساندة.'
            ]}
          ],
          images:[
            'https://images.unsplash.com/photo-1516280028089-67cf7ed8f8bb?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1511988617509-a57c8a288659?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1478737270239-2f02b77fc618?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'ينتهي الخبر عند هذه النقطة لأن الصياغة الخبرية تكتفي بعرض الوقائع بشكل متدرج ومباشر.'
        }
      },
      {
        id:'n3', section:'news', title:'هل المقاطع القصيرة تصنع الترند أم الحلقة الكاملة؟', label:'خبر صحفي',
        image:'https://images.unsplash.com/photo-1515041219749-89347f83291a?auto=format&fit=crop&q=80&w=1400',
        excerpt:'مقاطع قصيرة من حلقات طويلة صارت مادة للنقاش والتداول، ودفعت الجمهور للعودة إلى الحلقة الكاملة.',
        lead:'المقطع البودكاستي القصير صار أداة نشر قوية؛ يلتقط اللحظة ويقود الناس إلى الحلقة الأصلية.',
        summary:[
          'تتصدر بعض المقاطع القصيرة الترند لأنها تختصر لحظة قوية من حلقة أطول.',
          'لكن الحلقة الكاملة تبقى هي المصدر الذي يمنح السياق ويشرح ما وراء المقطع.',
          'وهنا تظهر أهمية التوازن بين التقطيع الذكي والمحتوى الكامل.'
        ],
        bullets:['مقاطع قصيرة','نقاش واسع','عودة للحلقة'],
        sources:[
          {title:'YouTube search - بودكاست سعودي', url:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A'}
        ],
        more:{
          intro:'الخبر هنا يشرح لماذا تنتشر المقاطع القصيرة بسرعة، ثم يعيد ربطها بالحلقة الكاملة التي تمنح السياق والمعنى.',
          body:[
            { paragraphs:['هل المقاطع القصيرة تصنع الترند أم الحلقة الكاملة؟ هذا هو السؤال الذي يفتتح الخبر ويقود القارئ إلى جوهر الموضوع.']},
            { paragraphs:[
              'المقطع الناجح هو الذي يثير الفضول ويجذب الانتباه، ثم يدفع المستمع للعودة إلى الأصل الكامل.',
              'وهذا يفسر لماذا يهتم صناع المحتوى باختيار اللحظة المناسبة للنشر والتداول.'
            ]},
            { paragraphs:[
              'وتظهر هنا قاعدة خبرية واضحة: المعلومة الأهم أولًا ثم التفاصيل المساندة ثم ما دونها.',
              'وهذا ما يجعل الخبر مباشرًا ومفهومًا ومتماسكًا.'
            ]}
          ],
          images:[
            'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1501386761578-eac5c94b800a?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'ويكتفي الخبر بهذا العرض المتدرج الواضح.'
        }
      },
      {
        id:'n4', section:'news', title:'كيف دخل المسؤولون والشخصيات الكبيرة عالم البودكاست؟', label:'خبر صحفي',
        image:'https://images.unsplash.com/photo-1551818255-e6e10975bc17?auto=format&fit=crop&q=80&w=1400',
        excerpt:'أصبح البودكاست مساحة مناسبة للحديث الطويل والهادئ، فصار خيارًا مفضلاً لعدد من الشخصيات العامة.',
        lead:'أصبح البودكاست مساحة مناسبة للحديث الطويل والهادئ، فصار خيارًا مفضلاً لعدد من الشخصيات العامة.',
        summary:[
          'أصبح البودكاست مساحة مناسبة للحديث الطويل والهادئ، فصار خيارًا مفضلاً لعدد من الشخصيات العامة.',
          'والسبب أن هذه الصيغة تمنح وقتًا أكبر للتفسير والشرح، وتخلق تواصلًا أقرب مع الجمهور.',
          'وفي المشهد السعودي، صار هذا الظهور جزءًا من طريقة جديدة للحوار العام.'
        ],
        bullets:['حوار هادئ','شرح أوضح','ثقة أعلى'],
        sources:[
          {title:'سقراط - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D8%B3%D9%82%D8%B1%D8%A7%D8%B7-%D9%85%D8%B9-%D8%B9%D9%85%D8%B1-%D8%A7%D9%84%D8%AC%D8%B1%D9%8A%D8%B3%D9%8A/id1459232606'}
        ],
        more:{
          intro:'هذا الخبر يبيّن كيف تحوّل البودكاست إلى مساحة مفضلة للشخصيات العامة عندما يتعلق الأمر بالشرح الهادئ والواضح.',
          body:[
            { paragraphs:['أصبح البودكاست مساحة مناسبة للحديث الطويل والهادئ، فصار خيارًا مفضلاً لعدد من الشخصيات العامة.']},
            { paragraphs:[
              'الصيغة الصوتية تمنح المتحدث فرصة لتفصيل الرؤية، وتمنح الجمهور وقتًا لاستيعاب الأفكار بعيدًا عن ضغط التصريحات القصيرة.',
              'وهذا التدرج في الشرح يرفع من جودة التواصل ويزيد من وضوح الرسالة.'
            ]},
            { paragraphs:[
              'الخبر يظل خبرًا لأنه يعرض الواقع كما هو، ثم يضيف التفاصيل الأكثر أهمية إلى الأقل أهمية.',
              'ولا يحتاج إلى خاتمة طويلة حتى ينجز وظيفته الصحفية.'
            ]}
          ],
          images:[
            'https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1528605248644-14dd04022da1?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1515377905703-c4788e51af15?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'بهذا تنتهي الصياغة الخبرية المحكمة.'
        }
      },
      {
        id:'n5', section:'news', title:'ماذا تغيّر بعد ظهور برامج البودكاست السعودي؟', label:'خبر صحفي',
        image:'https://images.unsplash.com/photo-1512872302902-5f4fd2986037?auto=format&fit=crop&q=80&w=1400',
        excerpt:'برامج سعودية كثيرة صارت علامات مألوفة، وأسهمت في بناء جمهور يتابع الصوت بشغف.',
        lead:'برامج البودكاست السعودية أسهمت في تشكيل ذائقة جديدة لدى الجمهور، من الحوار إلى السرد إلى التحليل.',
        summary:[
          'غيّر حضور البرامج السعودية طريقة الاستماع نفسها، لأن الجمهور صار يبحث عن الهوية المحلية والموضوعات القريبة منه.',
          'كما أسهمت بعض البرامج في جعل البودكاست جزءًا من النقاش العام في السعودية.',
          'وهذا الانتقال لم يكن شكليًا، بل كان تحوّلًا فعليًا في الاستهلاك الإعلامي.'
        ],
        bullets:['هوية سعودية','تأثير واضح','جمهور متابع'],
        sources:[
          {title:'فنجان - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827'}
        ],
        more:{
          intro:'الخبر هنا يلتقط أثر البرامج السعودية على الذائقة الإعلامية، ثم يشرح لماذا أصبحت هذه البرامج جزءًا من المشهد اليومي.',
          body:[
            { paragraphs:['ماذا تغيّر بعد ظهور برامج البودكاست السعودي؟ تغيّر كثير، لأن الجمهور صار يملك خيارات صوتية محلية أكثر قربًا من اهتمامه.']},
            { paragraphs:[
              'تنوّعت الموضوعات بين الحوار والاقتصاد والثقافة والسرد، فصار لكل فئة من المستمعين ما يناسبها.',
              'كما أن البرامج الناجحة أسهمت في رفع مستوى التوقع من المحتوى الصوتي داخل السعودية.'
            ]},
            { paragraphs:['الخبر يثبت أنه كلما كان المحتوى محليًا وواضح الهوية، زادت فرص حضوره واستمراره.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1492691527719-9e3adfcfdbd6?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وينتهي الخبر هنا دون خروج عن القالب الصحفي.'
        }
      }
    ],
    reports: [
      {
        id:'r1', section:'reports', title:'تقرير: كيف يعيش السعوديون مع البودكاست أثناء الدوام والسفر؟', label:'تقرير صحفي',
        image:'https://images.unsplash.com/photo-1518676590629-3dcbd9c5a5c9?auto=format&fit=crop&q=80&w=1400',
        excerpt:'من العادة العارضة إلى الرفيق اليومي، أصبح البودكاست حاضرًا في أكثر من لحظة من لحظات اليوم.',
        lead:'تقرير يقرأ انتقال الاستماع من لحظة عابرة إلى روتين متكرر يرافق الناس في الحركة والهدوء والعمل.',
        summary:[
          'من مشهد بسيط في السيارة أو أثناء العمل، ينطلق التقرير ليفسر كيف تحولت العادة إلى سلوك متكرر.',
          'كما يربط بين المرونة في الاستخدام وبين توسع دائرة المستمعين، ويعرض أثر ذلك على الإيقاع اليومي.',
          'وتظهر في النهاية صورة واضحة: البودكاست صار جزءًا من نمط الحياة لا مجرد محتوى عابر.'
        ],
        bullets:['سلوك يومي','مرونة الاستماع','تحول واضح'],
        sources:[
          {title:'جناية - الصفحة الرسمية', url:'https://podcasts.apple.com/sa/podcast/%D8%AC%D9%86%D8%A7%D9%8A%D8%A9/id1529103794'}
        ],
        more:{
          intro:'التقرير هنا يعتمد التمهيد الجذاب ثم المعلومات والشواهد ثم الخاتمة التقييمية التي تترك أثرًا في ذهن القارئ.',
          body:[
            { paragraphs:['الزاوية الجديدة في هذا التقرير هي مشهد الاستماع اليومي نفسه: شخص يختار البودكاست لأنه يرافقه دون أن يطلب منه التفرغ الكامل.']},
            { paragraphs:[
              'تسند الشواهد الفكرة الأساسية: البودكاست مرن، ويعمل في مساحات زمنية متنوعة، ويمنح المستمع إحساسًا بالاختيار.',
              'كما أن البرامج السعودية الناجحة أسهمت في جعل المحتوى الصوتي أكثر حضورًا، لأن الجمهور يجد فيه ما يشبهه ويهمه.'
            ]},
            { paragraphs:[
              'الخلاصة أن البودكاست السعودي صار جزءًا من حياة المستمع اليومية، وهذه النتيجة تفتح المجال للتفكير في مستقبل الصوت داخل الإعلام المحلي.'
            ]}
          ],
          images:[
            'https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'الخاتمة هنا تقييمية وتترك صدىً واضحًا في ذهن القارئ.'
        }
      },
      {
        id:'r2', section:'reports', title:'تقرير: لماذا نجحت بعض البرامج السعودية أكثر من غيرها؟', label:'تقرير صحفي',
        image:'https://images.unsplash.com/photo-1519731680124-4191f35d2f02?auto=format&fit=crop&q=80&w=1400',
        excerpt:'الفكرة الواضحة والهوية المحلية واللغة القريبة والتوقيت الذكي: عناصر تكرر حضورها في البرامج الناجحة.',
        lead:'نجاح البرامج السعودية لا يبدو صدفة؛ بل حصيلة خيارات تحريرية وسردية مدروسة.',
        summary:[
          'لا يحاول التقرير أن يعدد النجاحات فقط، بل يسأل: لماذا نجحت؟ وكيف صنعت هويتها؟',
          'ثم يبين أن الفكرة الواضحة واللغة القريبة والتوزيع الذكي هي عوامل تتكرر في البرامج الأبرز.',
          'ومن هنا يتشكل تفسير منطقي لهذا الحضور المستمر.'
        ],
        bullets:['هوية واضحة','لغة قريبة','توزيع ذكي'],
        sources:[
          {title:'سوالف بزنس - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D8%B3%D9%88%D8%A7%D9%84%D9%81-%D8%A8%D8%B2%D9%86%D8%B3-%D9%85%D8%B9-%D9%85%D8%B4%D9%87%D9%88%D8%B1-%D8%A7%D9%84%D8%AF%D8%A8%D9%8A%D8%A7%D9%86/id1239234534'}
        ],
        more:{
          intro:'يستخدم التقرير هنا قالب الهرم المعتدل؛ يفتتح بزواية جذابة ثم يقدّم الأدلة والوقائع ثم يغلق بخلاصة موضوعية.',
          body:[
            { paragraphs:['تبدأ الزاوية الجديدة من سؤال بسيط وعميق في آن واحد: لماذا يبقى بعض البرامج حاضرًا بينما تتراجع أخرى؟']},
            { paragraphs:[
              'تتكرر عوامل النجاح في البرامج السعودية الواضحة: هوية مفهومة، وضيف مناسب، ونبرة لا تتكلف، وتوزيع يلتقط اللحظة المناسبة.',
              'كما أن البرامج التي تبني علاقة ثقة مع الجمهور تميل إلى البقاء، لأنها لا تعتمد على الصدفة بل على الاستمرارية.'
            ]},
            { paragraphs:['النتيجة أن النجاح ليس رقمًا فقط، بل قدرة على البقاء وعلى أن يصير البرنامج مرجعًا داخل خريطته.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'الخاتمة تقدم تقييمًا موضوعيًا وتعميمًا منضبطًا لا يخرج عن محتوى التقرير.'
        }
      },
      {
        id:'r3', section:'reports', title:'تقرير: هل يطول عمر الحلقة عندما توازن بين السرد والحوار؟', label:'تقرير صحفي',
        image:'https://images.unsplash.com/photo-1511379938547-c1f69419868d?auto=format&fit=crop&q=80&w=1400',
        excerpt:'تجربة سمعية أطول لا تعني مللًا بالضرورة؛ الإيقاع والتوزيع هما ما يحفظان الاهتمام.',
        lead:'المدة وحدها لا تكفي؛ إنما الإيقاع والتصاعد والسرد هما ما يحفظ المستمع حتى آخر دقيقة.',
        summary:[
          'يبدأ التقرير من سؤال واضح: هل الطول مفيد دائمًا؟ ثم يربط بين الطول والإيقاع وجودة السرد.',
          'كما يبين أن الحلقة الطويلة تنجح حين تعرف كيف توزع أفكارها وتحفظ انتباه المستمع.',
          'وبهذا يصل إلى نتيجة أقرب إلى التقييم المهني منها إلى الانطباع.'
        ],
        bullets:['الإيقاع أهم','المدة تخدم الفكرة','تنوع الأطوال'],
        sources:[
          {title:'فنجان - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827'}
        ],
        more:{
          intro:'يتعامل التقرير هنا مع الزمن بوصفه عنصرًا تحريريًا، لا بوصفه رقمًا فقط.',
          body:[
            { paragraphs:['السؤال الرئيسي يختصر القضية: هل يطول عمر الحلقة عندما توازن بين السرد والحوار؟']},
            { paragraphs:[
              'الحلقة الطويلة تنجح إذا كانت تعرف كيف تنتقل من فكرة إلى أخرى بلا قفزات مربكة.',
              'أما الحلقة المختصرة فتنفع حين تكون مكثفة ومحددة ولا تترك المعنى ناقصًا.'
            ]},
            { paragraphs:['الخلاصة أن الطول ليس ميزة تلقائية، وإنما قيمة تتحقق عندما ينجح السرد في حمل المستمع حتى النهاية.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1515041219749-89347f83291a?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1501386761578-eac5c94b800a?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516280440614-37939bbacd81?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'النتيجة تقريرية وتعيد القارئ إلى قاعدة واضحة في صناعة البودكاست.'
        }
      },
      {
        id:'r4', section:'reports', title:'تقرير: كيف أصبح البودكاست جزءًا من حياة السعوديين؟', label:'تقرير صحفي',
        image:'https://images.unsplash.com/photo-1500634245200-e5245c7574ef?auto=format&fit=crop&q=80&w=1400',
        excerpt:'قراءة في أثر البودكاست على الروتين اليومي، وكيف انتقل من خيار فردي إلى ممارسة جماعية متكررة.',
        lead:'البودكاست صار جزءًا من الحياة اليومية لأنه ينسجم مع الوقت والمرونة والحاجة إلى المحتوى الهادئ.',
        summary:[
          'يوضح التقرير أن البودكاست السعودي اكتسب حضوره من قدرته على التكيف مع إيقاع الحياة اليومية.',
          'وأن الجمهور وجد فيه مساحة خاصة للمعرفة والاستماع في أوقات لا يناسبها التلفزيون أو الشاشة.',
          'وهنا تتضح قيمة هذا الشكل الإعلامي.'
        ],
        bullets:['روتين يومي','مرافقة صوتية','إيقاع حديث'],
        sources:[
          {title:'أبجورة - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA-%D8%A3%D8%A8%D8%AC%D9%88%D8%B1%D8%A9/id1272687671'}
        ],
        more:{
          intro:'هذا التقرير يلخص الظاهرة ويعرض نتائجها بعرض متدرج، مع خاتمة تعكس تقييمًا مهنيًا واضحًا.',
          body:[
            { paragraphs:['من خلال مشهد يومي بسيط، يشرح التقرير كيف أصبح البودكاست جزءًا من حياة السعوديين.']},
            { paragraphs:['تأتي المرونة في الاستماع كعامل رئيسي، ثم يضاف إليها تنوع المحتوى المحلي والتفاعل معه.']},
            { paragraphs:['الخلاصة أن البودكاست لم يعد ضيفًا على الحياة اليومية، بل صار جزءًا منها.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1492691527719-9e3adfcfdbd6?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وهكذا يكتمل التقرير بموضوعية واضحة وتقييم نهائي.'
        }
      }
    ],
    articles: [
      {
        id:'a1', section:'articles', title:'حديث بلا قيود… لماذا نجح البودكاست في السعودية؟', label:'مقال',
        image:'https://images.unsplash.com/photo-1455390582262-044cdead277a?auto=format&fit=crop&q=80&w=1400',
        excerpt:'مقال يقرأ نجاح البودكاست عبر الحرية في الحديث، والعمق في الطرح، والاتصال المباشر بالجمهور.',
        lead:'نجاح البودكاست في السعودية مرتبط بكونه مساحة تتيح الحديث الطويل دون ضجيج بصري أو إيقاع متعجل.',
        summary:[
          'نجح البودكاست لأنه أعاد الاعتبار للفكرة الطويلة والسرد المتدرج، ومنح المستمع تجربة اختيار حقيقية.',
          'كما أن قربه من الجمهور جعله وسيلة للمعرفة والرفقة في الوقت نفسه.',
          'وهذه الخصائص جعلته منافسًا مهمًا في المشهد الإعلامي.'
        ],
        bullets:['حرية في الطرح','عمق أكبر','جمهور متفاعل'],
        sources:[
          {title:'سقراط - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D8%B3%D9%82%D8%B1%D8%A7%D8%B7-%D9%85%D8%B9-%D8%B9%D9%85%D8%B1-%D8%A7%D9%84%D8%AC%D8%B1%D9%8A%D8%B3%D9%8A/id1459232606'}
        ],
        more:{
          intro:'هذا المقال يطرح قضية واضحة: لماذا نجح البودكاست؟ ثم يوسع الجواب عبر الحجج والحقائق والخاتمة الفكرية.',
          body:[
            { paragraphs:['نجح البودكاست في السعودية لأنه أعاد للفكرة الطويلة قيمتها، وللحديث المتأني حضوره الطبيعي.']},
            { paragraphs:[
              'الحرية في الحديث، والعمق في الطرح، والاتصال المباشر بالجمهور، كلها عوامل جعلت البودكاست مساحة مفضلة.',
              'كما أن المستمع صار أكثر نضجًا في اختيار ما يسمع، وهذا يرفع من قيمة المحتوى الجيد ويكشف ضعف المحتوى السطحي.'
            ]},
            { paragraphs:['الخلاصة أن البودكاست ليس موضة عابرة بل تعبير عن حاجة ثقافية واضحة إلى الحديث المتأني والمعنى.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1501386761578-eac5c94b800a?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وتبقى دعوة القارئ هنا ضمنية: أن يتأمل لماذا يعود لصوت دون آخر.'
        }
      },
      {
        id:'a2', section:'articles', title:'البودكاست النسائي في السعودية… صوتٌ جديد بقوة لافتة', label:'مقال',
        image:'https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&q=80&w=1400',
        excerpt:'قراءة في دور الأصوات النسائية في تشكيل ذائقة مختلفة، وإضافة موضوعات أوسع للمشهد.',
        lead:'البودكاست النسائي في السعودية لم يعد هامشيًا، بل صار جزءًا من مشهد أوسع وأكثر تنوعًا.',
        summary:[
          'الأصوات النسائية أضافت للمشهد موضوعات تمس الحياة اليومية وتفتح أبوابًا جديدة للفهم.',
          'كما أن حضورها منح البودكاست السعودي تنوعًا أكبر وعمقًا اجتماعيًا وثقافيًا.',
          'وهذا ما جعل هذا الصوت جزءًا أساسيًا من الخريطة الحالية.'
        ],
        bullets:['صوت نسائي','تنوع موضوعات','تجربة مختلفة'],
        sources:[
          {title:'كنبة السبت - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D9%83%D9%86%D8%A8%D8%A9-%D8%A7%D9%84%D8%B3%D8%A8%D8%AA/id1541797253'}
        ],
        more:{
          intro:'هذا المقال يعرض قضية ثقافية واضحة، ثم يضيف الحجج والحقائق، وينتهي بخلاصة فكرية متزنة.',
          body:[
            { paragraphs:['البودكاست النسائي في السعودية لم يعد صوتًا ثانويًا، بل أصبح حضورًا واضحًا في المشهد الصوتي.']},
            { paragraphs:[
              'أضاف هذا الحضور موضوعات عن التجربة اليومية، والنفس، والعلاقات، والوعي الذاتي، وغير ذلك من المساحات التي لاقت تفاعلًا واسعًا.',
              'كما أن النبرة الهادئة واللغة القريبة ساعدتا في بناء جمهور وفيّ لهذا اللون من المحتوى.'
            ]},
            { paragraphs:['الخلاصة أن هذا الصوت أسهم في توسيع المشهد لا في تكراره، وهو ما يمنحه قيمة مستمرة.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1488426862026-3ee34a7d66df?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1524504388940-b1c1722653e1?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1488972685288-c3fd157d7c7a?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'المقال هنا يقدّم خلاصة واضحة ويترك أثرًا يمكن للقارئ البناء عليه.'
        }
      },
      {
        id:'a3', section:'articles', title:'لماذا يفضّل الشباب البودكاست على التلفزيون؟', label:'مقال',
        image:'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1400',
        excerpt:'قراءة في تغيّر العادات الإعلامية لدى الجيل الجديد، ولماذا صار الصوت أقرب من الشاشة.',
        lead:'الشباب لا يهرب من الشاشة فقط، بل يبحث عن محتوى يسمح له بالحركة ويعيش معه في أكثر من سياق.',
        summary:[
          'يفضّل كثير من الشباب البودكاست لأنه يناسب المرونة التي يبحثون عنها في يومهم المتعدد المهام.',
          'كما أن المحتوى الصوتي يترك لهم حرية الاختيار والعودة والاستماع على وتيرتهم الخاصة.',
          'وهذا يفسر قربه من الجيل الجديد.'
        ],
        bullets:['مرونة عالية','اختيار شخصي','محتوى طويل'],
        sources:[
          {title:'أبجورة - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA-%D8%A3%D8%A8%D8%AC%D9%88%D8%B1%D8%A9/id1272687671'}
        ],
        more:{
          intro:'مقال يشرح تغيير الذائقة ويعرض الأسباب التي جعلت الشباب يميلون إلى البودكاست أكثر من التلفزيون التقليدي.',
          body:[
            { paragraphs:['السؤال واضح: لماذا يفضّل الشباب البودكاست؟ لأنه أكثر انسجامًا مع حياتهم المتحركة.']},
            { paragraphs:[
              'يتيح البودكاست حرية في التلقي، ويمنح المستمع مساحة للاختيار والتوقف والعودة.',
              'كما أن البرامج السعودية نجحت في صياغة محتوى يقترب من تجربة الشباب واهتماماتهم اليومية.'
            ]},
            { paragraphs:['الخلاصة أن الصوت لم يفز على الشاشة صدفة، بل لأنه وجد مكانه الطبيعي في حياة الجيل الجديد.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1501386761578-eac5c94b800a?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516321497487-e288fb19713f?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1478737270239-2f02b77fc618?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وهنا يبقى المقال مفتوحًا للتفكير أكثر من كونه حكمًا نهائيًا.'
        }
      },
      {
        id:'a4', section:'articles', title:'كيف دخلت الشخصيات الكبيرة عالم البودكاست؟', label:'مقال',
        image:'https://images.unsplash.com/photo-1551818255-e6e10975bc17?auto=format&fit=crop&q=80&w=1400',
        excerpt:'المساحة الصوتية أفسحت المجال للحوار الهادئ والمطوّل، فصارت خيارًا مناسبًا للشخصيات المؤثرة.',
        lead:'أصبح البودكاست وسيلة مناسبة للحوار الطويل والهادئ، لذلك جذبت بعض الشخصيات الكبيرة هذا الشكل.',
        summary:[
          'دخلت الشخصيات الكبيرة عالم البودكاست لأنها وجدت فيه مساحة أوسع للتفسير والحديث غير المتعجل.',
          'كما أن هذا الشكل يمنحها فرصة لشرح الأفكار بدل الاكتفاء بجمل قصيرة.',
          'وهذا الانتقال أعاد تعريف الظهور العام.'
        ],
        bullets:['حوار مطول','شرح أوضح','قرب من الجمهور'],
        sources:[
          {title:'سقراط - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D8%B3%D9%82%D8%B1%D8%A7%D8%B7-%D9%85%D8%B9-%D8%B9%D9%85%D8%B1-%D8%A7%D9%84%D8%AC%D8%B1%D9%8A%D8%B3%D9%8A/id1459232606'}
        ],
        more:{
          intro:'مقال يشرح سبب توجه الشخصيات المؤثرة إلى البودكاست بوصفه مساحة حوار أهدأ وأوضح وأكثر قربًا من الجمهور.',
          body:[
            { paragraphs:['البودكاست وفّر للشخصيات الكبيرة مساحة حديث مختلفة، أقل صخبًا وأكثر قربًا من المعنى.']},
            { paragraphs:['تمنح هذه الصيغة وقتًا أكبر لتفسير الرأي، وتفتح المجال أمام الجمهور لفهم السياق بدل الحكم السريع.']},
            { paragraphs:['الخلاصة أن المساحة الصوتية لم تعد هامشًا، بل جزءًا من بناء الحضور العام.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1528605248644-14dd04022da1?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1515377905703-c4788e51af15?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'المقال هنا يختم بفكرة واضحة ومباشرة دون خروج عن الموضوع.'
        }
      },
      {
        id:'a5', section:'articles', title:'حديث بلا قيود… لماذا ينجح البودكاست في السعودية؟', label:'مقال',
        image:'https://images.unsplash.com/photo-1501386761578-eac5c94b800a?auto=format&fit=crop&q=80&w=1400',
        excerpt:'نجاح البودكاست يرتبط بالحرية في الطرح، واللغة القريبة، والقدرة على صنع وقت خاص للمستمع.',
        lead:'ينجح البودكاست لأنه يمنح المستمع وقتًا خاصًا، وصوتًا قريبًا، ومعنى يمكن العودة إليه.',
        summary:[
          'يقدّم هذا المقال قراءة جديدة لنجاح البودكاست عبر فكرة الحرية الصوتية والقرب من الجمهور.',
          'كما يبيّن أن نجاحه ليس تقنيًا فقط، بل تحريري ومعنوي أيضًا.',
          'وهذا ما يجعل حضوره ثابتًا في المشهد.'
        ],
        bullets:['حرية','قرب','معنى'],
        sources:[
          {title:'فنجان - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827'}
        ],
        more:{
          intro:'هذا المقال يقدّم خلاصة أوضح لسبب النجاح ويضيف إليها بعدًا تحريريًا يفهمه القارئ بسهولة.',
          body:[
            { paragraphs:['نجاح البودكاست في السعودية يرتبط بالحرية في الطرح والقرب من المستمع.']},
            { paragraphs:['حين يشعر المستمع أن المحتوى يخاطبه مباشرة، تتكون علاقة استماع أقوى وأكثر استمرارية.']},
            { paragraphs:['الخلاصة أن النجاح هنا ليس عابرًا، بل قائم على حاجة حقيقية إلى الحديث المتأني.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'ويكمل المقال وظيفته حين يربط بين الفكرة والنتيجة بوضوح.'
        }
      }
    ],
    investigations: [
      {
        id:'i1', section:'investigations', title:'ليه الجيل الحالي يفضّل البودكاست على التلفزيون التقليدي؟', label:'تحقيق صحفي',
        image:'https://images.unsplash.com/photo-1520975916090-3105956dac38?auto=format&fit=crop&q=80&w=1400',
        excerpt:'تحقيق يشرح كيف تغيّرت العادات السمعية، ولماذا صار الصوت أكثر ملاءمة من البث التلفزيوني التقليدي.',
        lead:'تحقيق يقرأ علاقة الجيل الحالي بالمحتوى: لماذا الصوت أقرب، ولماذا صار التلفزيون أقل حضورًا عند بعض الفئات؟',
        summary:[
          'يطرح التحقيق سؤال التفضيل بين البودكاست والتلفزيون، ثم يجيب عنه عبر المرونة والاختيار والإيقاع.',
          'كما يوضح أن الجيل الحالي يبحث عن محتوى يتماشى مع يومه المتحرك.',
          'وهذا ما جعل البودكاست يتقدم في كثير من الحالات.'
        ],
        bullets:['سؤال واضح','إجابات مباشرة','شواهد واقعية'],
        sources:[
          {title:'كنبة السبت - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D9%83%D9%86%D8%A8%D8%A9-%D8%A7%D9%84%D8%B3%D8%A8%D8%AA/id1541797253'}
        ],
        more:{
          intro:'التحقيق يبدأ بسؤال ويجيب عنه خلال النص كله، ثم ينتهي بخلاصة واضحة مبنية على الشواهد.',
          body:[
            { paragraphs:['السؤال الأساسي يختصر موضوع التحقيق: لماذا يفضّل الجيل الحالي البودكاست على التلفزيون التقليدي؟']},
            { paragraphs:[
              'الإجابة ترتبط بالمرونة: يمكن الاستماع أثناء الحركة والعمل والراحة، بينما يطلب التلفزيون وقتًا أكثر ثباتًا.',
              'كما أن البودكاست ينسجم مع الذائقة التي تريد محتوى أقرب وأكثر تخصيصًا.'
            ]},
            { paragraphs:['النتيجة أن الصوت أصبح أقرب إلى الجيل الجديد لأنه ينسجم مع نمط حياته.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1518676590629-3dcbd9c5a5c9?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1501386761578-eac5c94b800a?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'الخاتمة هنا خلاصة واضحة لأسئلة التحقيق.'
        }
      },
      {
        id:'i2', section:'investigations', title:'تأثير ظهور المسؤولين في البودكاست على الثقة؟', label:'تحقيق صحفي',
        image:'https://images.unsplash.com/photo-1551818255-e6e10975bc17?auto=format&fit=crop&q=80&w=1400',
        excerpt:'كيف يغيّر الظهور الصوتي الرسمي مزاج الجمهور؟ وما الذي يجعله أقرب من اللقاءات التقليدية؟',
        lead:'حين يتحول الخطاب الرسمي إلى حوار هادئ طويل، تتغير آلية الفهم والتفاعل بشكل واضح.',
        summary:[
          'يعرض التحقيق كيف يمنح البودكاست المسؤولين مساحة أهدأ للشرح والتفسير.',
          'كما يوضح أن الجمهور يتفاعل أكثر مع الحوار المطوّل الذي يترك مساحة للسؤال والإجابة.',
          'وهذا يرفع الثقة ويخفف من حدة التلقي.'
        ],
        bullets:['ثقة أعلى','حوار مباشر','مساحة هادئة'],
        sources:[
          {title:'سقراط - الصفحة الرسمية', url:'https://podcasts.apple.com/us/podcast/%D8%B3%D9%82%D8%B1%D8%A7%D8%B7-%D9%85%D8%B9-%D8%B9%D9%85%D8%B1-%D8%A7%D9%84%D8%AC%D8%B1%D9%8A%D8%B3%D9%8A/id1459232606'}
        ],
        more:{
          intro:'التحقيق يبيّن أثر الوسيط على الثقة، ثم يوضح كيف يتحول الحوار إلى مساحة أوضح وأهدأ.',
          body:[
            { paragraphs:['البودكاست يمنح الخطاب الرسمي مساحة أهدأ وأكثر وضوحًا.']},
            { paragraphs:['يتلقى الجمهور الرسائل بشكل أفضل حين يسمع الشرح والتفصيل بدل العناوين القصيرة فقط.']},
            { paragraphs:['الخلاصة أن الثقة ترتبط بجودة الحوار وبطبيعة الوسيط نفسه.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1528605248644-14dd04022da1?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1515377905703-c4788e51af15?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وهذا يجعل التحقيق متماسكًا ومبنيًا على نتائج واضحة.'
        }
      },
      {
        id:'i3', section:'investigations', title:'كيف دخلت الشخصيات الكبيرة عالم البودكاست بدل اللقاءات التقليدية؟', label:'تحقيق صحفي',
        image:'https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&q=80&w=1400',
        excerpt:'لماذا أصبح البودكاست خيارًا مفضلًا للحديث الهادئ والواضح بدل التصريحات السريعة؟',
        lead:'اللقاءات التقليدية غالبًا ما تختصر الكلام، بينما البودكاست يسمح للفكرة بأن تُبنى على مراحل.',
        summary:[
          'يشرح التحقيق لماذا يفضّل بعض الشخصيات الكبيرة البودكاست بوصفه مساحة شرح أوسع.',
          'كما يبين أن الحوار الطويل يساعد على بناء صورة أكثر إنسانية وأقرب للجمهور.',
          'وهذا ما يفسر هذا التحول.'
        ],
        bullets:['شرح أطول','إنسانية أعلى','بديل هادئ'],
        sources:[
          {title:'The Mo Show - الصفحة الرسمية', url:'https://podcasts.apple.com/sa/podcast/the-mo-show-presented-by-bsf/id1529888455'}
        ],
        more:{
          intro:'هذا التحقيق يضع اللقاء التقليدي في مواجهة المساحة الصوتية الهادئة، ثم يخلص إلى النتيجة بوضوح.',
          body:[
            { paragraphs:['الظهور في البودكاست صار خيارًا مفضلًا لأنه يتيح للمتحدث أن يشرح بدل أن يختصر فقط.']},
            { paragraphs:[
              'الإيقاع الهادئ والمطوّل يجعل الرسالة أقرب وأوضح، ويمنح الجمهور فهمًا أعمق.'
            ]},
            { paragraphs:['الخلاصة أن التحول هنا ليس شكليًا، بل في طريقة الحديث وطريقة التلقي.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1516280440614-37939bbacd81?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516542076529-1ea3854896b1?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'ويغلق التحقيق موضوعه بحصيلة واضحة ومهنية.'
        }
      }
    ],
    programs: [
      {
        id:'fanjan', section:'programs', title:'فنجان مع عبدالرحمن أبومالح', label:'برنامج سعودي حواري', kind:'حوارات عميقة',
        image:'https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?auto=format&fit=crop&q=80&w=1400',
        excerpt:'من أشهر البرامج الحوارية السعودية، يقدّم مساحة واسعة للنقاش مع ضيوف من مجالات متعددة.',
        lead:'فنجان يبني الحوار بهدوء، ويمنح الضيف مساحة كافية لتوضيح فكرته وتجربته.',
        summary:[
          'برنامج معروف بحواراته الطويلة الهادئة التي تحترم عقل المستمع.',
          'ويمتاز بأنه يركز على الفكرة والتجربة والسياق لا على العنوان السريع فقط.',
          'لذلك يظل من العناوين الأساسية في المشهد السعودي.'
        ],
        bullets:['حوار أسبوعي','من ثمانية','نبرة هادئة','مناسب للتفكير'],
        sources:[
          {title:'البرنامج الرسمي', url:'https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827'},
          {title:'بحث يوتيوب', url:'https://www.youtube.com/results?search_query=%D9%81%D9%86%D8%AC%D8%A7%D9%86+%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86+%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD'}
        ],
        more:{
          intro:'وصف كامل للبرنامج يشرح هويته الحوارية ومكانته وتفصيله التحريري بطريقة متصلة وواضحة.',
          body:[
            { paragraphs:['فنجان برنامج حواري هادئ يعامل الفكرة بوقت كافٍ ويمنح الضيف مساحته الطبيعية.']},
            { paragraphs:['البرنامج يقدّم حوارات طويلة ومبنية على الإعداد، لذلك يشعر المستمع أن الفكرة تُبنى أمامه خطوة خطوة.']},
            { paragraphs:['الخلاصة أن فنجان بقي حاضرًا لأنه لم يتنازل عن هويته الأساسية.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1504384308090-c894fdcc538d?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وهكذا يكتمل الوصف الكامل للبرنامج.'
        }
      },
      {
        id:'jinaya', section:'programs', title:'جناية', label:'برنامج سعودي سردي', kind:'تشويق وتحقيق',
        image:'https://images.unsplash.com/photo-1455390582262-044cdead277a?auto=format&fit=crop&q=80&w=1400',
        excerpt:'بودكاست بطابع تشويقي ونفسي يتتبع خيوط الجرائم ويحللها، فيأخذ المستمع إلى مسارات متعددة من الإثارة والتفكير.',
        lead:'جناية يعتمد على السرد المشدود والتحليل المتدرج، لذلك ينجح في شد المستمع حتى النهاية.',
        summary:[
          'جناية برنامج سردي تشويقي يعتمد على قصة واقعية وتحليل متدرج.',
          'ويجمع بين التشويق والفهم في قالب واضح ومتماسك.',
          'ولهذا يحظى بحضور واسع عند جمهور يحب السرد.'
        ],
        bullets:['قصص واقعية','إيقاع سردي','تشويق عالي','تحليل نفسي'],
        sources:[
          {title:'البرنامج الرسمي', url:'https://podcasts.apple.com/sa/podcast/%D8%AC%D9%86%D8%A7%D9%8A%D8%A9/id1529103794'},
          {title:'بحث يوتيوب', url:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%AC%D9%86%D8%A7%D9%8A%D8%A9'}
        ],
        more:{
          intro:'وصف كامل للبرنامج مع لغة متصلة، دون حشو أو تفاصيل خارجة عن طبيعته السردية.',
          body:[
            { paragraphs:['جناية يبدأ من القصة ثم يتقدم نحو التحليل، لذلك يلتقط المستمع من اللحظة الأولى.']},
            { paragraphs:['يعتمد البرنامج على التدرج في السرد وإعادة تركيب الحكاية، وهو ما يعطيه قيمة سردية عالية.']},
            { paragraphs:['الخلاصة أن قوة البرنامج تأتي من اتساقه السردي ومن حسن بناء الإيقاع.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1511379938547-c1f69419868d?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1520975916090-3105956dac38?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وبذلك يكتمل الوصف الكامل للبرنامج.'
        }
      },
      {
        id:'mosho', section:'programs', title:'The Mo Show Presented by BSF', label:'برنامج سعودي باللغة الإنجليزية', kind:'حوارات عالمية',
        image:'https://images.unsplash.com/photo-1516280440614-37939bbacd81?auto=format&fit=crop&q=80&w=1400',
        excerpt:'بودكاست باللغة الإنجليزية يقدّم حوارات مع ضيوف من مجالات مختلفة، ويعكس حضورًا سعوديًا معاصرًا.',
        lead:'The Mo Show يفتح نافذة سعودية باللغة الإنجليزية، ويقدم حوارات تجمع بين الثقافة والحضور العالمي.',
        summary:[
          'برنامج سعودي باللغة الإنجليزية يقدّم حوارات منظمة ومهنية.',
          'ويعكس قدرة البودكاست السعودي على الوصول إلى جمهور أوسع.',
          'كما يحافظ على هوية واضحة داخل القالب الدولي.'
        ],
        bullets:['لغة إنجليزية','هوية سعودية','جمهور عالمي'],
        sources:[
          {title:'البرنامج الرسمي', url:'https://podcasts.apple.com/sa/podcast/the-mo-show-presented-by-bsf/id1529888455'},
          {title:'بحث يوتيوب', url:'https://www.youtube.com/results?search_query=The+Mo+Show+Presented+by+BSF'}
        ],
        more:{
          intro:'وصف كامل يشرح لماذا يلفت البرنامج جمهورًا محليًا وعالميًا في الوقت نفسه.',
          body:[
            { paragraphs:['The Mo Show يوسّع دائرة الوصول من خلال الإنجليزية من دون أن يفقد هويته السعودية.']},
            { paragraphs:['الحوارات هنا مهنية وواضحة، وتتيح للمستمع فهم الضيف والفكرة والسياق.']},
            { paragraphs:['الخلاصة أن اللغة هنا أداة توسعة لا خروج عن الموضوع.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1511988617509-a57c8a288659?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1524504388940-b1c1722653e1?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1478737270239-2f02b77fc618?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وهكذا يكتمل الوصف بشكل مرتب ومفهوم.'
        }
      },
      {
        id:'sardyat', section:'programs', title:'سرديات', label:'برنامج سعودي ثقافي', kind:'أدب وفكر',
        image:'https://images.unsplash.com/photo-1512872302902-5f4fd2986037?auto=format&fit=crop&q=80&w=1400',
        excerpt:'بودكاست يحاور كتّابًا وأدباء ومفكرين لمناقشة قضايا الفكر والأدب العربي والتحولات الاجتماعية والثقافية.',
        lead:'سرديات يعتمد على الجملة الواضحة والسؤال الثقافي الهادئ، لذلك يشبه جلسة معرفة مفتوحة على التأويل.',
        summary:[
          'برنامج ثقافي يركّز على الفكرة والمعنى واللغة الجميلة.',
          'ويمنح المستمع مساحة هادئة للتأمل والقراءة الأوسع.',
          'لذلك يعد من البرامج الثقافية المهمة.'
        ],
        bullets:['فكر وأدب','سرد ثقافي','محتوى عربي'],
        sources:[
          {title:'البرنامج الرسمي', url:'https://podcasts.apple.com/sa/podcast/sardyat-%D8%B3%D8%B1%D8%AF%D9%8A%D8%A7%D8%AA/id1647955514'},
          {title:'بحث يوتيوب', url:'https://www.youtube.com/results?search_query=%D8%B3%D8%B1%D8%AF%D9%8A%D8%A7%D8%AA+%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA'}
        ],
        more:{
          intro:'وصف كامل للبرنامج الثقافي بصياغة مرتبة ومتناسقة مع طبيعته الهادئة.',
          body:[
            { paragraphs:['سرديات برنامج يختار السؤال الثقافي الهادئ ويمنحه زمنًا كافيًا.']},
            { paragraphs:['يتمحور البرنامج حول الفكر والأدب والتجربة الإنسانية، لذلك يخاطب جمهورًا يحب التعمق.']},
            { paragraphs:['الخلاصة أن البرنامج يضيف للمشهد السعودي بعدًا ثقافيًا مهمًا.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1545239351-1141bd82e8a6?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516542076529-1ea3854896b1?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وهكذا يكتمل الوصف الكامل للبرنامج.'
        }
      }
    ],
    extraPrograms: [
      {
        id:'kanbat', section:'extraPrograms', title:'كنبة السبت', label:'برنامج نفسي/اجتماعي', kind:'راحة وتفكير',
        image:'https://images.unsplash.com/photo-1529156069898-49953e39b3ac?auto=format&fit=crop&q=80&w=1400',
        excerpt:'بودكاست هادئ يمزج النفس والاجتماع والفلسفة، ويمنح المستمع جلسة دافئة ومعنى أبعد.',
        lead:'كنبة السبت من البرامج التي تعطي المستمع شعور الجلسة الدافئة التي تجمع بين الراحة والعمق.',
        summary:['برنامج هادئ يقرّب الأسئلة اليومية من الإنسان.', 'ويمزج النفس والاجتماع والفلسفة بطريقة سهلة.', 'لذلك يناسب المود الهادئ والتأمل.'],
        bullets:['نفسي','اجتماعي','مريح'],
        sources:[
          {title:'البرنامج الرسمي', url:'https://podcasts.apple.com/us/podcast/%D9%83%D9%86%D8%A8%D8%A9-%D8%A7%D9%84%D8%B3%D8%A8%D8%AA/id1541797253'}
        ],
        more:{
          intro:'وصف كامل لبرنامج هادئ يعتمد على الجو العام واللغة المريحة.',
          body:[
            { paragraphs:['كنبة السبت يقدم مساحة دافئة للحديث والتفكير من دون تكلف.']},
            { paragraphs:['يناقش موضوعات اجتماعية ونفسية بلغة قريبة، لذلك يخلق شعورًا بالراحة لدى المستمع.']},
            { paragraphs:['الخلاصة أن البرنامج ينجح لأنه يراهن على الهدوء والصدق.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1529156069898-49953e39b3ac?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1488972685288-c3fd157d7c7a?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وهكذا يكتمل الوصف الكامل.'
        }
      },
      {
        id:'abjora', section:'extraPrograms', title:'بودكاست أبجورة', label:'برنامج ثقافي', kind:'فكر وإلهام',
        image:'https://images.unsplash.com/photo-1516542076529-1ea3854896b1?auto=format&fit=crop&q=80&w=1400',
        excerpt:'بودكاست بصوت هادئ ولغة جميلة، يقدم مساحات تأملية وثقافية تترك أثرًا واضحًا.',
        lead:'أبجورة يقدّم لغة رقيقة وموضوعات تأملية تجعل المستمع يشعر أنه في مساحة فهم وهدوء.',
        summary:['يتميز بقدرته على تحويل المعنى إلى إحساس لغوي جميل.', 'ويخاطب جمهورًا يحب التأمل والصدق والهدوء.', 'وهو من العلامات الثقافية المحبوبة.'],
        bullets:['لغة جميلة','تأمل','ثقافة'],
        sources:[
          {title:'البرنامج الرسمي', url:'https://podcasts.apple.com/us/podcast/%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA-%D8%A3%D8%A8%D8%AC%D9%88%D8%B1%D8%A9/id1272687671'}
        ],
        more:{
          intro:'أبجورة برنامج يحتاج إلى صور هادئة ونص طويل لأن هويته تقوم على الرقة والتأمل أكثر من أي شيء آخر.',
          body:[
            { paragraphs:['البرنامج يفتح الباب أمام التأمل من أول لحظة، ويبتعد عن التكلف والضجيج.']},
            { paragraphs:['يعتمد على لغة جميلة وعلى معنى يُقال بهدوء، ويمنح المستمع فرصة لأن يفكر ويستعيد نفسه.']},
            { paragraphs:['الخلاصة أن أبجورة يظل مهمًا لأنه يربط بين الجمال اللغوي والعمق الإنساني.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1516542076529-1ea3854896b1?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1512872302902-5f4fd2986037?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1545239351-1141bd82e8a6?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'ويكتمل هنا الوصف الكامل للبرنامج.'
        }
      },
      {
        id:'sawalif', section:'extraPrograms', title:'سوالف بزنس مع مشهور الدبيان', label:'برنامج أعمال', kind:'ريادة ونمو',
        image:'https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&q=80&w=1400',
        excerpt:'برنامج عن الأعمال والريادة وقصص النمو، يقدّم التجارب العملية بعيدًا عن المجاملة.',
        lead:'سوالف بزنس يحكي قصص تأسيس ونمو وتحديات، لذلك يعد مرجعًا ممتعًا للمهتمين بريادة الأعمال.',
        summary:['يعرض التجارب العملية بوضوح.', 'ويربط بين الفشل والنجاح والتعلم.', 'ويمنح المستمع مادة مفيدة وواقعية.'],
        bullets:['بزنس','ريادة','قصص نجاح'],
        sources:[
          {title:'البرنامج الرسمي', url:'https://podcasts.apple.com/us/podcast/%D8%B3%D9%88%D8%A7%D9%84%D9%81-%D8%A8%D8%B2%D9%86%D8%B3-%D9%85%D8%B9-%D9%85%D8%B4%D9%87%D9%88%D8%B1-%D8%A7%D9%84%D8%AF%D8%A8%D9%8A%D8%A7%D9%86/id1239234534'}
        ],
        more:{
          intro:'وصف كامل لبرنامج أعمال عملي ومباشر.',
          body:[
            { paragraphs:['يعرض البرنامج سؤال الأعمال والريادة بوضوح منذ البداية.']},
            { paragraphs:['يستعرض التجارب الحقيقية ويُظهر الدروس المتراكمة وراء النجاح.']},
            { paragraphs:['الخلاصة أنه برنامج يفيد المهتم بالتجربة العملية.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516280030429-27679e5f8e4b?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وهكذا يكتمل الوصف الكامل.'
        }
      },
      {
        id:'socrates', section:'extraPrograms', title:'سقراط مع عمر الجريسي', label:'برنامج تحليلي', kind:'فكر وتحول',
        image:'https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&q=80&w=1400',
        excerpt:'برنامج يفتح أسئلة كبيرة حول التحولات في السعودية، ويضع قضايا المجتمع والاقتصاد على طاولة الحوار.',
        lead:'سقراط يقدّم أسئلة كبيرة، ويعطي مساحة تحليل لا مجرد تبادل إجابات.',
        summary:['برنامج تحليلي واضح.', 'يناقش التحولات والأفكار الكبرى.', 'وهو مناسب للمتابع المهتم بالفهم العميق.'],
        bullets:['تحليل','أسئلة كبيرة','وضوح'],
        sources:[
          {title:'البرنامج الرسمي', url:'https://podcasts.apple.com/us/podcast/%D8%B3%D9%82%D8%B1%D8%A7%D8%B7-%D9%85%D8%B9-%D8%B9%D9%85%D8%B1-%D8%A7%D9%84%D8%AC%D8%B1%D9%8A%D8%B3%D9%8A/id1459232606'}
        ],
        more:{
          intro:'وصف كامل لبرنامج تحليلي يشرح التحولات ويعرض الفكرة بعمق.',
          body:[
            { paragraphs:['سقراط برنامج يفتح أسئلة التحول بوضوح ويمنحها زمنًا كافيًا.']},
            { paragraphs:['يعتمد على التحليل الهادئ والشرح المبني على الفكرة والسياق.']},
            { paragraphs:['الخلاصة أنه يضيف للمشهد قيمة معرفية مهمة.']}
          ],
          images:[
            'https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1504384308090-c894fdcc538d?auto=format&fit=crop&q=80&w=1200',
            'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1200'
          ],
          closing:'وهكذا يكتمل الوصف الكامل.'
        }
      }
    ],
    videos: [
      { title:'قصص من أيام العرب مع حمود الصاهود في مخيال | مع عبدالله البندر', desc:'حلقة مرتبطة بعالم البودكاست والقصص العربية، وتظهر في صفحة الفيديو بشكل مباشر.', embed:'https://www.youtube.com/embed/ulDugCU4L1M' },
      { title:'كلامك يقلب موازين حياتك | د. سعد العريفي', desc:'حلقة تتناول أثر الكلمات وكيفية توظيفها في الحياة والعلاقات وصناعة التأثير.', embed:'https://www.youtube.com/embed/OJ2_PLte5nk' },
      { title:'مذكرات رجل أمن سعودي | بودكاست فنجان', desc:'حلقة من فنجان تظهر داخل صفحة الفيديو مع بطاقة ومشغل مباشر.', embed:'https://www.youtube.com/embed/OetssqWJycg' }
    ]
  };

  const allItems = [
    ...data.news,
    ...data.reports,
    ...data.articles,
    ...data.investigations,
    ...data.programs,
    ...data.extraPrograms
  ];

  const panels = {
    home: document.getElementById('panel-home'),
    news: document.getElementById('panel-news'),
    reports: document.getElementById('panel-reports'),
    articles: document.getElementById('panel-articles'),
    investigations: document.getElementById('panel-investigations'),
    programs: document.getElementById('panel-programs'),
    references: document.getElementById('panel-references'),
    interactive: document.getElementById('panel-interactive'),
    videos: document.getElementById('panel-videos'),
    detail: document.getElementById('panel-detail'),
    more: document.getElementById('panel-more')
  };

  const els = {
    toastContainer: document.getElementById('toastContainer'),
    devBtn: document.getElementById('devBtn'),
    devModal: document.getElementById('devModal'),
    voteModal: document.getElementById('voteModal'),
    newsGrid: document.getElementById('newsGrid'),
    reportsGrid: document.getElementById('reportsGrid'),
    articlesGrid: document.getElementById('articlesGrid'),
    investigationsGrid: document.getElementById('investigationsGrid'),
    programGrid: document.getElementById('programGrid'),
    extraGrid: document.getElementById('extraGrid'),
    extraWrap: document.getElementById('extraWrap'),
    videoGrid: document.getElementById('videoGrid'),
    referencesGrid: document.getElementById('referencesGrid'),
    programSearch: document.getElementById('programSearch'),
    toggleExtraBtn: document.getElementById('toggleExtraBtn'),
    recommendBtn: document.getElementById('recommendBtn'),
    recommendBox: document.getElementById('recommendBox'),
    recommendTitle: document.getElementById('recommendTitle'),
    recommendText: document.getElementById('recommendText'),
    openRecommended: document.getElementById('openRecommended'),
    currentMood: document.getElementById('currentMood'),
    moodRecommendation: document.getElementById('moodRecommendation'),
    hoursSlider: document.getElementById('hoursSlider'),
    hoursValue: document.getElementById('hoursValue'),
    quoteBox: document.getElementById('quoteBox'),
    nextQuoteBtn: document.getElementById('nextQuoteBtn'),
    quizResult: document.getElementById('quizResult'),
    openVoteBtn: document.getElementById('openVoteBtn'),
    voteForm: document.getElementById('voteForm'),
    voteDone: document.getElementById('voteDone'),
    voteFanjan: document.getElementById('voteFanjan'),
    voteJinaya: document.getElementById('voteJinaya'),
    voteMosho: document.getElementById('voteMosho'),
    voteSardyat: document.getElementById('voteSardyat'),
    resFanjan: document.getElementById('resFanjan'),
    resJinaya: document.getElementById('resJinaya'),
    resMosho: document.getElementById('resMosho'),
    resSardyat: document.getElementById('resSardyat'),
    detailBackBtn: document.getElementById('detailBackBtn'),
    detailTopFlag: document.getElementById('detailTopFlag'),
    detailHero: document.getElementById('detailHero'),
    detailLabel: document.getElementById('detailLabel'),
    detailMeta: document.getElementById('detailMeta'),
    detailType: document.getElementById('detailType'),
    detailTitle: document.getElementById('detailTitle'),
    detailLead: document.getElementById('detailLead'),
    detailBody: document.getElementById('detailBody'),
    detailBullets: document.getElementById('detailBullets'),
    detailLinks: document.getElementById('detailLinks'),
    expandBtn: document.getElementById('expandBtn'),
    moreBackBtn: document.getElementById('moreBackBtn'),
    moreHero: document.getElementById('moreHero'),
    moreLabel: document.getElementById('moreLabel'),
    moreMeta: document.getElementById('moreMeta'),
    moreTitle: document.getElementById('moreTitle'),
    moreIntro: document.getElementById('moreIntro'),
    moreBody: document.getElementById('moreBody')
  };

  const state = {
    currentPanel:'home',
    previousPanel:'home',
    activeGroup:null,
    activeId:null,
    activeItem:null,
    detailScroll:0,
    summaryScroll:0,
    extraVisible:false,
    currentMood:'ضحك',
    quoteIndex:0,
    votes: JSON.parse(localStorage.getItem('mulham_votes_v19') || 'null') || { fanjan:0, jinaya:0, mosho:0, sardyat:0 }
  };

  const hideEl = el => {
    el.classList.add('overlay-hidden');
    el.classList.remove('overlay-visible');
    setTimeout(() => el.classList.add('hidden'), 180);
  };
  const showEl = el => {
    el.classList.remove('hidden');
    el.classList.remove('overlay-hidden');
    el.classList.add('overlay-visible');
  };

  function toast(message){
    const el = document.createElement('div');
    el.className = 'bg-white border border-black/5 shadow-2xl rounded-2xl px-4 py-3 font-bold text-[#4E4A43] min-w-[220px] soft';
    el.textContent = message;
    els.toastContainer.appendChild(el);
    setTimeout(() => {
      el.style.opacity='0';
      el.style.transform='translateY(8px)';
      el.style.transition='all .25s ease';
      setTimeout(() => el.remove(), 250);
    }, 1600);
  }

  function setActiveNav(panelName){
    document.querySelectorAll('.nav-btn').forEach(btn => btn.classList.toggle('active', btn.dataset.panel === panelName));
  }

  function openPanel(panelName){
    state.previousPanel = state.currentPanel;
    state.currentPanel = panelName;
    Object.values(panels).forEach(p => p.classList.remove('active'));
    panels[panelName].classList.add('active');
    setActiveNav(panelName);
    window.scrollTo({ top:0, behavior:'smooth' });
  }

  function renderCards(items, target, section){
    target.innerHTML = items.map(item => `
      <article class="bg-white rounded-[2rem] overflow-hidden shadow-xl border border-black/5 card-hover soft" data-id="${item.id}" data-section="${section}">
        <div class="relative h-56 overflow-hidden bg-[#F4F1EA]">
          <img src="${item.image}" alt="${htmlEscape(item.title)}" class="w-full h-full object-cover" loading="lazy">
          <div class="wm"><span>مُلهم</span></div>
          ${item.title.includes('؟') ? '<div class="question-badge">؟</div>' : ''}
          <div class="absolute inset-0 bg-gradient-to-t from-black/35 via-transparent to-transparent"></div>
          <div class="absolute top-4 right-4 px-3 py-1 rounded-full bg-white/90 text-[#7A5A2E] font-black text-sm">${htmlEscape(item.label)}</div>
        </div>
        <div class="p-6">
          <h3 class="text-2xl font-black text-[#7A5A2E] leading-tight mb-3">${htmlEscape(item.title)}</h3>
          <p class="text-[#5d594f] leading-8 mb-5">${htmlEscape(item.excerpt)}</p>
          <div class="flex flex-wrap gap-2 mb-5">${listToChips(item.bullets.slice(0,3))}</div>
          <button class="open-btn w-full bg-[#7A5A2E] text-white px-4 py-3 rounded-2xl font-black soft hover:scale-[1.02]" data-section="${section}" data-id="${item.id}">فتح</button>
        </div>
      </article>
    `).join('');
  }

  function renderVideos(){
    els.videoGrid.innerHTML = data.videos.map(v => `
      <div class="bg-white rounded-[2rem] overflow-hidden shadow-xl border border-black/5 card-hover soft">
        <div class="hero-cover">
          <iframe class="w-full h-64" src="${v.embed}" title="${htmlEscape(v.title)}" allowfullscreen></iframe>
          <div class="wm"><span>مُلهم</span></div>
        </div>
        <div class="p-5">
          <h3 class="font-black text-xl text-[#7A5A2E] mb-2">${htmlEscape(v.title)}</h3>
          <p class="text-[#5d594f] leading-7">${htmlEscape(v.desc)}</p>
          <a href="${v.embed.replace('/embed/','/watch?v=')}" target="_blank" rel="noopener noreferrer" class="mt-4 inline-flex px-4 py-3 rounded-2xl bg-[#7A856F] text-white font-black soft hover:scale-[1.03]">فتح في يوتيوب</a>
        </div>
      </div>
    `).join('');
  }

  function renderReferences(){
    const blocks = allItems.map(item => `
      <article class="bg-white rounded-[2rem] border border-black/5 shadow-xl overflow-hidden">
        <div class="grid md:grid-cols-4 gap-0">
          <div class="md:col-span-1">
            <img src="${item.image}" alt="${htmlEscape(item.title)}" class="w-full h-full object-cover min-h-56">
          </div>
          <div class="md:col-span-3 p-6 md:p-7">
            <div class="flex flex-wrap gap-2 items-center mb-3">
              <span class="px-3 py-1 rounded-full bg-[#7A5A2E]/10 text-[#7A5A2E] text-sm font-black">${htmlEscape(item.label)}</span>
              <span class="text-sm text-[#7A856F] font-bold">${item.section === 'news' ? 'خبر' : item.section === 'reports' ? 'تقرير' : item.section === 'articles' ? 'مقال' : item.section === 'investigations' ? 'تحقيق' : 'برنامج'}</span>
            </div>
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">${htmlEscape(item.title)}</h3>
            <p class="text-[#5d594f] leading-8 mb-5">${htmlEscape(item.excerpt)}</p>
            <div class="grid sm:grid-cols-2 gap-3">
              ${item.sources.map(src => `
                <a href="${src.url}" target="_blank" rel="noopener noreferrer" class="rounded-2xl bg-[#F4F1EA] border border-black/5 p-4 block soft hover:shadow-md">
                  <div class="font-black text-[#7A5A2E]">${htmlEscape(src.title)}</div>
                  <div class="text-sm text-[#5d594f] mt-2 break-words">${htmlEscape(src.url)}</div>
                </a>
              `).join('')}
            </div>
          </div>
        </div>
      </article>
    `).join('');
    els.referencesGrid.innerHTML = blocks;
  }

  function renderVotes(){
    ['fanjan','jinaya','mosho','sardyat'].forEach(key => {
      const pretty = key.charAt(0).toUpperCase() + key.slice(1);
      els[`vote${pretty}`].textContent = state.votes[key];
      els[`res${pretty}`].textContent = state.votes[key];
    });
  }

  function renderHours(){ els.hoursValue.textContent = `${els.hoursSlider.value} ساعة`; }

  function renderQuote(){
    const quotes = ['“مو كل صمت راحة.”','“أحيانًا الصوت يغيّر طريقة تفكيرك.”','“من هنا نُعيد تعريف المستحيل.”','“مُلهم.. نبض البودكاست السعودي.”','“صوت السعودية المسموع.. يرويه لكم مُلهم.”'];
    els.quoteBox.textContent = quotes[state.quoteIndex];
  }

  function updateMood(){
    const map = { ضحك:'mosho', تفكير:'fanjan', نفسي:'kanbat', تشويق:'jinaya' };
    const item = data.programs.concat(data.extraPrograms).find(p => p.id === map[state.currentMood]) || data.programs[0];
    els.currentMood.textContent = state.currentMood;
    els.recommendBox.classList.remove('hidden');
    els.recommendTitle.textContent = item.title;
    els.recommendText.textContent = item.excerpt;
    els.moodRecommendation.innerHTML = `
      <div class="font-black text-2xl text-[#7A5A2E] mb-2">${htmlEscape(item.title)}</div>
      <p class="text-[#5d594f] leading-8">${htmlEscape(item.excerpt)}</p>
      <div class="mt-4 flex flex-wrap gap-2">${listToChips(item.bullets.slice(0,3))}</div>
    `;
  }

  function searchPrograms(q){
    const term = q.trim().toLowerCase();
    document.querySelectorAll('[data-section="programs"], [data-section="extraPrograms"]').forEach(card => {
      const id = card.dataset.id;
      const item = data.programs.concat(data.extraPrograms).find(p => p.id === id);
      if (!item) return;
      const text = `${item.title} ${item.excerpt} ${item.kind} ${(item.summary||[]).join(' ')} ${(item.bullets||[]).join(' ')}`.toLowerCase();
      card.style.display = text.includes(term) ? '' : 'none';
    });
  }

  function renderDetail(item){
    els.detailTopFlag.classList.toggle('hidden', !item.title.includes('؟'));
    els.detailHero.src = item.image;
    els.detailHero.alt = item.title;
    els.detailLabel.textContent = item.label;
    els.detailMeta.textContent = item.kind || '';
    els.detailType.textContent = item.section === 'news' ? 'خبر صحفي' : item.section === 'reports' ? 'تقرير' : item.section === 'articles' ? 'مقال' : item.section === 'investigations' ? 'تحقيق' : 'بطاقة برنامج';
    els.detailTitle.textContent = item.title;
    els.detailLead.textContent = item.lead;
    els.detailBody.innerHTML = textToParagraphs(item.summary.join('\n'));
    els.detailBullets.innerHTML = listToChips(item.bullets);
    els.detailLinks.innerHTML = item.sources.map(src => `<a href="${src.url}" target="_blank" rel="noopener noreferrer" class="px-4 py-3 rounded-2xl bg-[#7A5A2E] text-white font-black soft hover:scale-[1.03]">${htmlEscape(src.title)}</a>`).join('');
  }

  function getMoreGallery(item){
    return item.more.images || [item.image, item.image, item.image];
  }

  function openDetail(section, id){
    const item = data[section].find(x => x.id === id);
    if (!item) return;
    state.activeGroup = section;
    state.activeId = id;
    state.activeItem = item;
    state.summaryScroll = window.scrollY;

    renderDetail(item);
    panels.detail.classList.add('active');
    Object.entries(panels).forEach(([name, panel]) => {
      if (name !== 'detail') panel.classList.remove('active');
    });
    setActiveNav(null);
    window.scrollTo({ top:0, behavior:'smooth' });
  }

  function openMore(){
    const item = state.activeItem;
    if (!item) return;
    state.detailScroll = window.scrollY;

    els.moreHero.src = item.image;
    els.moreHero.alt = item.title;
    els.moreLabel.textContent = item.label;
    els.moreMeta.textContent = item.kind || '';
    els.moreTitle.textContent = item.title;
    els.moreIntro.textContent = item.more.intro;

    const allText = [
      ...item.summary,
      ...item.more.body.flatMap(part => part.paragraphs),
      item.more.closing
    ];

    els.moreBody.innerHTML = `
      <div class="bg-white rounded-[2rem] p-6 md:p-8 shadow-xl border border-black/5">
        <div class="detail-rich">
          ${allText.map(p => `<p>${htmlEscape(p)}</p>`).join('')}
        </div>
      </div>
      <div class="mt-8 grid md:grid-cols-3 gap-6">
        ${getMoreGallery(item).map((img) => galleryImg(img, 'صورة مرتبطة بالموضوع')).join('')}
      </div>
    `;
    panels.more.classList.add('active');
    panels.detail.classList.remove('active');
    setActiveNav(null);
    window.scrollTo({ top:0, behavior:'smooth' });
  }

  function backToDetail(){
    panels.more.classList.remove('active');
    panels.detail.classList.add('active');
    setTimeout(() => window.scrollTo({ top: state.detailScroll || 0, behavior:'instant' }), 0);
  }

  function backToSummary(){
    panels.detail.classList.remove('active');
    panels[state.previousPanel || 'home'].classList.add('active');
    setActiveNav(state.previousPanel || 'home');
    setTimeout(() => window.scrollTo({ top: state.summaryScroll || 0, behavior:'instant' }), 0);
  }

  renderCards(data.news, els.newsGrid, 'news');
  renderCards(data.reports, els.reportsGrid, 'reports');
  renderCards(data.articles, els.articlesGrid, 'articles');
  renderCards(data.investigations, els.investigationsGrid, 'investigations');
  renderCards(data.programs, els.programGrid, 'programs');
  renderVideos();
  renderReferences();
  renderVotes();
  renderHours();
  renderQuote();
  updateMood();

  document.querySelectorAll('.nav-btn, .jump-btn').forEach(btn => btn.addEventListener('click', () => openPanel(btn.dataset.panel)));

  document.addEventListener('click', e => {
    const open = e.target.closest('.open-btn');
    if (open){
      openDetail(open.dataset.section, open.dataset.id);
      return;
    }
    const close = e.target.closest('[data-close]');
    if (close){
      const id = close.dataset.close;
      if (id === 'dev') hideEl(els.devModal);
      if (id === 'vote') hideEl(els.voteModal);
    }
  });

  els.devBtn.addEventListener('click', () => showEl(els.devModal));

  els.expandBtn.addEventListener('click', openMore);
  els.moreBackBtn.addEventListener('click', backToDetail);
  els.detailBackBtn.addEventListener('click', backToSummary);

  els.toggleExtraBtn.addEventListener('click', () => {
    state.extraVisible = !state.extraVisible;
    els.extraWrap.classList.toggle('hidden', !state.extraVisible);
    if (state.extraVisible && !els.extraGrid.innerHTML.trim()) {
      renderCards(data.extraPrograms, els.extraGrid, 'extraPrograms');
    }
    els.toggleExtraBtn.textContent = state.extraVisible ? 'إخفاء المزيد' : 'إظهار المزيد';
    toast(state.extraVisible ? 'تم عرض البرامج الإضافية' : 'تم إخفاء البرامج الإضافية');
  });
  els.programSearch.addEventListener('input', e => searchPrograms(e.target.value));

  els.recommendBtn.addEventListener('click', () => { updateMood(); toast('تم اقتراح برنامج مناسب'); });
  els.openRecommended.addEventListener('click', () => openDetail(state.activeGroup === 'extraPrograms' ? 'extraPrograms' : 'programs', state.activeId));
  els.openVoteBtn.addEventListener('click', () => {
    els.voteDone.classList.add('hidden');
    els.voteForm.classList.remove('hidden');
    showEl(els.voteModal);
    toast('اختر برنامجك وصوّت');
  });
  els.hoursSlider.addEventListener('input', renderHours);
  els.nextQuoteBtn.addEventListener('click', () => { state.quoteIndex = (state.quoteIndex + 1) % 5; renderQuote(); });

  document.querySelectorAll('.mood-btn').forEach(btn => btn.addEventListener('click', () => {
    state.currentMood = btn.dataset.mood;
    updateMood();
    toast(`المود الحالي: ${state.currentMood}`);
  }));

  document.querySelectorAll('.quiz-btn').forEach(btn => btn.addEventListener('click', () => {
    const key = btn.dataset.result;
    const item = data.programs.concat(data.extraPrograms).find(p => p.id === key);
    if (!item) return;
    els.quizResult.innerHTML = `<div class="font-black text-2xl text-[#7A5A2E] mb-2">${htmlEscape(item.title)}</div><p class="text-[#5d594f] leading-8">${htmlEscape(item.excerpt)}</p>`;
  }));

  els.voteForm.addEventListener('submit', e => {
    e.preventDefault();
    const selected = new FormData(els.voteForm).get('vote') || 'sardyat';
    state.votes[selected] = (state.votes[selected] || 0) + 1;
    localStorage.setItem('mulham_votes_v19', JSON.stringify(state.votes));
    renderVotes();
    els.voteForm.classList.add('hidden');
    els.voteDone.classList.remove('hidden');
    toast('تم تسجيل الصوت');
  });

  document.addEventListener('keydown', e => {
    if (e.key === 'Escape'){
      hideEl(els.devModal);
      hideEl(els.voteModal);
      if (panels.more.classList.contains('active')) backToDetail();
      else if (panels.detail.classList.contains('active')) backToSummary();
    }
  });
});
</script>
</body>
</html>https://discord.com/oauth2/authorize?client_id=1326229573838569564&permissions=8&integration_type=0&scope=bot
