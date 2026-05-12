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
      background:rgba(255,255,255,.74);
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
    .quote{animation:move 16s linear infinite}
    @keyframes move{
      0%{transform:translateX(0)}
      100%{transform:translateX(50%)}
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
    .modal-hidden{
      opacity:0;
      pointer-events:none;
      transform:translateY(12px) scale(.98);
    }
    .modal-visible{
      opacity:1;
      pointer-events:auto;
      transform:translateY(0) scale(1);
    }
    .search::placeholder{color:rgba(78,74,67,.55)}
  </style>
</head>
<body class="min-h-screen">

  <div class="fixed inset-0 pointer-events-none -z-10 overflow-hidden opacity-[0.03]">
    <div class="absolute top-0 left-0 w-full h-full bg-[radial-gradient(circle_at_top_left,#7A856F,transparent_40%)]"></div>
    <div class="absolute bottom-0 right-0 w-full h-full bg-[radial-gradient(circle_at_bottom_right,#7A5A2E,transparent_40%)]"></div>
  </div>

  <div id="toastContainer" class="fixed bottom-5 left-5 z-[150] space-y-3 pointer-events-none"></div>

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
        <button type="button" class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="home">الرئيسية</button>
        <button type="button" class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="news">أخبار</button>
        <button type="button" class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="reports">تقارير</button>
        <button type="button" class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="articles">مقال</button>
        <button type="button" class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="investigations">تحقيق</button>
        <button type="button" class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="interviews">مقابلة</button>
        <button type="button" class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="programs">البرامج</button>
        <button type="button" class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="interactive">تفاعلي</button>
        <button type="button" class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[#7A5A2E]/10 text-[#7A5A2E] font-bold" data-panel="videos">فيديو</button>
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
                صحيفة إلكترونية فخمة ومقسّمة بوضوح إلى أخبار وتقارير ومقالات وتحقيقات ومقابلات وبرامج وتفاعل وفيديو، وكلها تدور حول البودكاست السعودي فقط.
              </p>

              <div class="mt-10 flex flex-wrap justify-center gap-4">
                <button type="button" class="jump-btn bg-[#7A5A2E] text-white px-7 py-4 rounded-2xl text-lg font-bold shadow-xl hover:scale-[1.03] soft" data-panel="news">تصفّح الأخبار</button>
                <button type="button" class="jump-btn border-2 border-[#7A856F] text-[#7A856F] px-7 py-4 rounded-2xl text-lg font-bold hover:bg-[#7A856F] hover:text-white soft" data-panel="programs">البرامج</button>
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
            <p class="text-lg leading-8 text-[#5d594f]">أخبار، تقارير، مقال، تحقيق، مقابلة، وبرامج داخل تصميم واحد متناسق.</p>
          </div>
          <div class="bg-white rounded-3xl p-6 shadow-xl border border-black/5 card-hover soft">
            <div class="w-14 h-14 rounded-2xl bg-[#7A856F]/10 text-[#7A856F] flex items-center justify-center text-2xl mb-4">🎧</div>
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">برامج سعودية موثوقة</h3>
            <p class="text-lg leading-8 text-[#5d594f]">بطاقات برامج مع وصف كامل وصور وروابط أصلية للمصادر الرسمية.</p>
          </div>
          <div class="bg-white rounded-3xl p-6 shadow-xl border border-black/5 card-hover soft">
            <div class="w-14 h-14 rounded-2xl bg-[#7A5A2E]/10 text-[#7A5A2E] flex items-center justify-center text-2xl mb-4">⚡</div>
            <h3 class="text-2xl font-black text-[#7A5A2E] mb-3">تفاعل حي وسريع</h3>
            <p class="text-lg leading-8 text-[#5d594f]">بودكاست اليوم، المود، التصويت، الاقتباس، والاختبار كلها تعمل مباشرة.</p>
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
          <div class="px-4 py-2 rounded-full bg-white border border-black/5 shadow-sm font-bold text-[#7A5A2E]">تحليل وقياس</div>
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

    <section id="panel-interviews" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="text-4xl md:text-5xl font-black text-[#7A5A2E]">مقابلة</h2>
            <p class="text-[#7A856F] mt-3 text-lg">مقابلات صحفية وصور للمقدمين ووراء المايك.</p>
          </div>
        </div>
        <div class="grid lg:grid-cols-2 gap-8">
          <div id="interviewsGrid" class="grid md:grid-cols-2 gap-6"></div>
          <div class="bg-white rounded-[2rem] p-7 shadow-xl border border-black/5">
            <h3 class="text-3xl font-black text-[#7A5A2E] mb-5">صور المقدمين</h3>
            <div class="grid sm:grid-cols-2 gap-4">
              <div class="rounded-3xl overflow-hidden border border-black/5">
                <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&q=80&w=1200" alt="عبدالرحمن أبومالح" class="h-56 w-full object-cover">
                <div class="p-4 bg-[#F4F1EA]">
                  <div class="font-black text-lg text-[#7A5A2E]">عبدالرحمن أبومالح</div>
                  <div class="text-sm text-[#7A856F] mt-1">فنجان</div>
                </div>
              </div>
              <div class="rounded-3xl overflow-hidden border border-black/5">
                <img src="https://images.unsplash.com/photo-1504593811423-6dd665756598?auto=format&fit=crop&q=80&w=1200" alt="أفنان الغامدي" class="h-56 w-full object-cover">
                <div class="p-4 bg-[#F4F1EA]">
                  <div class="font-black text-lg text-[#7A5A2E]">أفنان الغامدي</div>
                  <div class="text-sm text-[#7A856F] mt-1">كنبة السبت</div>
                </div>
              </div>
              <div class="rounded-3xl overflow-hidden border border-black/5">
                <img src="https://images.unsplash.com/photo-1506277886164-e25aa3f4ef7f?auto=format&fit=crop&q=80&w=1200" alt="Mo Islam" class="h-56 w-full object-cover">
                <div class="p-4 bg-[#F4F1EA]">
                  <div class="font-black text-lg text-[#7A5A2E]">Mo Islam</div>
                  <div class="text-sm text-[#7A856F] mt-1">The Mo Show</div>
                </div>
              </div>
              <div class="rounded-3xl overflow-hidden border border-black/5">
                <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&q=80&w=1200" alt="غدير حسين" class="h-56 w-full object-cover">
                <div class="p-4 bg-[#F4F1EA]">
                  <div class="font-black text-lg text-[#7A5A2E]">غدير حسين</div>
                  <div class="text-sm text-[#7A856F] mt-1">سرديات</div>
                </div>
              </div>
            </div>
            <div class="mt-6 rounded-3xl bg-[#7A5A2E] text-white p-6">
              <h4 class="font-black text-2xl mb-2">وراء المايك</h4>
              <p class="leading-8 text-white/90">هنا تُعرض ملامح الشخصيات التي صنعت حضور البودكاست السعودي: أسلوب التقديم، نبرة الحديث، وكيف تتحول المقدمّة أو المقدم إلى جزء من هوية البرنامج.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="panel-programs" class="panel">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="text-4xl md:text-5xl font-black text-[#7A5A2E]">البرامج</h2>
            <p class="text-[#7A856F] mt-3 text-lg">كل برنامج له صورة ووصف كامل عند الفتح.</p>
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
            <p class="text-[#7A856F] font-bold">بطاقات أكثر داخل نفس الصفحة.</p>
          </div>
          <div id="extraGrid" class="grid sm:grid-cols-2 xl:grid-cols-3 gap-6"></div>
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
        <div id="videoGrid" class="grid lg:grid-cols-4 gap-6"></div>
      </div>
    </section>
  </main>

  <div id="detailModal" class="fixed inset-0 z-[120] flex items-center justify-center p-4 hidden modal-hidden soft">
    <div class="absolute inset-0 bg-black/65 backdrop-blur-sm" data-close="detail"></div>
    <div class="relative z-10 w-full max-w-4xl bg-white rounded-[2rem] shadow-2xl overflow-hidden border border-black/5">
      <div class="grid md:grid-cols-5">
        <div class="md:col-span-2">
          <img id="detailImage" src="" alt="" class="w-full h-full object-cover min-h-[260px] md:min-h-[100%]">
        </div>
        <div class="md:col-span-3 p-6 md:p-8">
          <div class="flex items-start justify-between gap-4">
            <div>
              <div id="detailLabel" class="text-sm text-[#7A856F] font-bold mb-2"></div>
              <h3 id="detailTitle" class="text-3xl md:text-4xl font-black text-[#7A5A2E] leading-tight"></h3>
            </div>
            <button type="button" class="w-11 h-11 rounded-full bg-black/5 hover:bg-black/10 soft text-2xl leading-none" data-close="detail">×</button>
          </div>
          <p id="detailExcerpt" class="mt-5 text-lg md:text-xl leading-loose text-[#5d594f]"></p>
          <div id="detailBody" class="mt-5 space-y-4 text-lg leading-9 text-[#4E4A43]"></div>
          <div id="detailBullets" class="flex flex-wrap gap-2 mt-6"></div>
          <div id="detailLinks" class="flex flex-wrap gap-3 mt-8"></div>
        </div>
      </div>
    </div>
  </div>

  <div id="devModal" class="fixed inset-0 z-[125] flex items-center justify-center p-4 hidden modal-hidden soft">
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

  <div id="voteModal" class="fixed inset-0 z-[122] flex items-center justify-center p-4 hidden modal-hidden soft">
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
  const news = [
    {
      id:'n1',
      title:'السعودية تتحدث… عصر البودكاست يبدأ',
      label:'خبر صحفي',
      image:'https://images.unsplash.com/photo-1501386761578-eac5c94b800a?auto=format&fit=crop&q=80&w=1400',
      excerpt:'كيف تحول الاستماع إلى البودكاست من خيار جانبي إلى عادة يومية عند شريحة واسعة من السعوديين؟',
      body:[
        'لم يعد البودكاست محتوى هامشيًا، بل صار حاضرًا في السيارة والعمل والسفر قبل النوم.',
        'هذا التحول يعكس تغيرًا في ذائقة الجمهور السعودي الذي بات يبحث عن محتوى أطول وأكثر عمقًا ومرونة.'
      ],
      bullets:['استماع يومي','نمو سريع','محتوى طويل'],
      links:[
        ['فنجان','https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827'],
        ['أبجورة','https://podcasts.apple.com/us/podcast/%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA-%D8%A3%D8%A8%D8%AC%D9%88%D8%B1%D8%A9/id1272687671']
      ]
    },
    {
      id:'n2',
      title:'كيف دخل المسؤولون والشخصيات الكبيرة عالم البودكاست؟',
      label:'خبر صحفي',
      image:'https://images.unsplash.com/photo-1551818255-e6e10975bc17?auto=format&fit=crop&q=80&w=1400',
      excerpt:'البودكاست فتح بابًا جديدًا للحوار المباشر، وأصبح مساحة تُفهم فيها القرارات والرسائل بشكل أقرب للجمهور.',
      body:[
        'عندما ينتقل الخطاب من القاعة الرسمية إلى الميكروفون الهادئ، يصبح الوصول إلى الناس أسهل وأكثر وضوحًا.',
        'هذا التحول لا يغيّر فقط أسلوب الحديث، بل يغير أيضًا طريقة التلقي.'
      ],
      bullets:['رسائل مباشرة','حوار هادئ','ثقة أعلى'],
      links:[
        ['سقراط','https://podcasts.apple.com/us/podcast/%D8%B3%D9%82%D8%B1%D8%A7%D8%B7-%D9%85%D8%B9-%D8%B9%D9%85%D8%B1-%D8%A7%D9%84%D8%AC%D8%B1%D9%8A%D8%B3%D9%8A/id1459232606'],
        ['The Mo Show','https://podcasts.apple.com/sa/podcast/the-mo-show-presented-by-bsf/id1529888455']
      ]
    },
    {
      id:'n3',
      title:'أكثر المقاطع البودكاستية التي تصدرت الترند في السعودية',
      label:'ترند',
      image:'https://images.unsplash.com/photo-1516280440614-37939bbacd81?auto=format&fit=crop&q=80&w=1400',
      excerpt:'مقاطع قصيرة من حلقات طويلة صارت مادة للنقاش والتداول، ودفعت الجمهور للعودة إلى الحلقة الكاملة.',
      body:[
        'الترند البودكاستي في السعودية لا يقوم على الصوت وحده، بل على اللحظة التي تصنع الجدل أو الدهشة.',
        'المقطع الناجح هو الذي يدفع الناس إلى النقاش، ثم إلى البحث عن الحلقة الأصلية.'
      ],
      bullets:['مقاطع قصيرة','نقاش واسع','عودة للحلقة'],
      links:[['يوتيوب','https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A']]
    },
    {
      id:'n4',
      title:'ناس صاروا يسمعون بودكاست أثناء الدوام أو السفر أو قبل النوم',
      label:'سلوك جمهور',
      image:'https://images.unsplash.com/photo-1518676590629-3dcbd9c5a5c9?auto=format&fit=crop&q=80&w=1400',
      excerpt:'الاستماع صار جزءًا من الروتين اليومي، والبودكاست أصبح رفيقًا للحركة والهدوء والاسترخاء.',
      body:[
        'لأن البودكاست يرافق المستمع في كل وقت، فهو يناسب فترات لا ينافس فيها المحتوى المرئي.',
        'هذا النوع من الاستخدام اليومي يمنحه قيمة مختلفة؛ فهو ليس فقط مادة للتسلية، بل رفيق متكرر يعاد إليه عند الحاجة.'
      ],
      bullets:['روتين يومي','سهل التلقي','لا يحتاج شاشة'],
      links:[
        ['فنجان','https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827'],
        ['كنبة السبت','https://podcasts.apple.com/us/podcast/%D9%83%D9%86%D8%A8%D8%A9-%D8%A7%D9%84%D8%B3%D8%A8%D8%AA/id1541797253']
      ]
    },
    {
      id:'n5',
      title:'تزايد الاهتمام بالحلقات المرئية في البودكاست السعودي',
      label:'خبر صحفي',
      image:'https://images.unsplash.com/photo-1478737270239-2f02b77fc618?auto=format&fit=crop&q=80&w=1400',
      excerpt:'الصورة بدأت تكمل الصوت في كثير من البرامج، والجمهور صار يفضّل التجربة المزدوجة حين تخدم الفكرة.',
      body:[
        'المرئي لا يلغي الصوت، لكنه يضيف طبقة جديدة من التواصل.',
        'ولهذا ينجح كثير من صناع المحتوى في الجمع بين النسخة المسموعة والمرئية للحلقة نفسها.'
      ],
      bullets:['صوت + صورة','تجربة مزدوجة','جمهور أوسع'],
      links:[['يوتيوب','https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D9%85%D8%B1%D8%A6%D9%8A+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A']]
    },
    {
      id:'n6',
      title:'كيف تصنع الحلقة البودكاستية ترندًا سعوديًا؟',
      label:'خبر صحفي',
      image:'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1400',
      excerpt:'من العنوان إلى المقطع القصير إلى النقاش العام… عناصر تتحول معها الحلقة إلى حديث منتشر.',
      body:[
        'الحلقة التي تصنع الترند عادة تمتلك عنوانًا واضحًا، ولحظة قابلة للاقتطاع، وفكرة قابلة للنقاش.',
        'وعندما تُنشر المقاطع القصيرة بذكاء، تتحول الحلقة من محتوى صوتي إلى موضوع عام.'
      ],
      bullets:['عنوان قوي','مقطع قابل للنشر','نقاش عام'],
      links:[['مقاطع بودكاست سعودي','https://www.youtube.com/results?search_query=%D9%85%D9%82%D8%A7%D8%B7%D8%B9+%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A']]
    },
    {
      id:'n7',
      title:'بودكاست السعودية… من التسجيل البسيط إلى الإنتاج الاحترافي',
      label:'خبر صحفي',
      image:'https://images.unsplash.com/photo-1516387938699-a93567ec168e?auto=format&fit=crop&q=80&w=1400',
      excerpt:'تطور واضح في جودة الصوت والإخراج والهوية البصرية للبرامج السعودية.',
      body:[
        'البرامج السعودية اليوم لم تعد تعتمد على البساطة فقط، بل أصبحت تهتم بالصورة والهوية والأغلفة والملفات التعريفية.',
        'هذا التطور رفع سقف التوقعات لدى الجمهور وفتح مساحة للتنافس بين البرامج.'
      ],
      bullets:['إخراج أفضل','هوية أقوى','جودة أعلى'],
      links:[['أمثلة برامج سعودية','https://podcasts.apple.com/us/search?term=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%B3%D8%B9%D9%88%D8%AF%D9%8A']]
    },
    {
      id:'n8',
      title:'البودكاست كمساحة للهوية السعودية المعاصرة',
      label:'خبر صحفي',
      image:'https://images.unsplash.com/photo-1522202176988-66273c2fd55f?auto=format&fit=crop&q=80&w=1400',
      excerpt:'أصبح البودكاست مساحة تعبّر عن اهتمام الجمهور السعودي بالفكر والقصص والتجربة اليومية.',
      body:[
        'البودكاست السعودي اليوم لا يقدّم الترفيه فقط، بل يعكس أسئلة الناس واهتماماتهم وإيقاع حياتهم.',
        'وهذا ما جعله عنصرًا مهمًا في المشهد الإعلامي الرقمي.'
      ],
      bullets:['هوية محلية','قصص وتجارب','إعلام رقمي'],
      links:[['فنجان','https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827']]
    }
  ];

  const reports = [
    {
      id:'r1',
      title:'كيف أصبح البودكاست جزءًا من حياة السعوديين؟',
      label:'تقرير صحفي',
      image:'https://images.unsplash.com/photo-1500634245200-e5245c7574ef?auto=format&fit=crop&q=80&w=1400',
      excerpt:'من الاستماع العابر إلى العادة اليومية: قراءة في تحوّل العلاقة بين الجمهور السعودي والبودكاست.',
      body:[
        'هذا التقرير يرصد كيف انتقل البودكاست من مساحة تجريبية إلى عادة استماع واضحة.',
        'ما يميز هذه المرحلة أن الجمهور لم يعد يكتفي بالخبر السريع؛ بل يبحث عن سياق وفهم وتفاصيل.'
      ],
      bullets:['من خيار إلى عادة','تنوع الموضوعات','اختيار مرن'],
      links:[['جناية','https://podcasts.apple.com/sa/podcast/%D8%AC%D9%86%D8%A7%D9%8A%D8%A9/id1529103794']]
    },
    {
      id:'r2',
      title:'تقرير عن أسباب نجاح البودكاستات السعودية',
      label:'تقرير صحفي',
      image:'https://images.unsplash.com/photo-1519731680124-4191f35d2f02?auto=format&fit=crop&q=80&w=1400',
      excerpt:'لماذا نجحت بعض البرامج السعودية أكثر من غيرها؟ قراءة في الفكرة والهوية واللغة والتوقيت.',
      body:[
        'يستند نجاح البودكاست السعودي إلى مزيج من عناصر بسيطة لكن مؤثرة: وضوح الفكرة، صدق المقدم، قرب الموضوع من حياة الجمهور.',
        'حين تتقاطع الهوية المحلية مع جودة الإخراج وحسن الإيقاع، يصبح البودكاست أكثر قابلية للانتشار والاستمرار.'
      ],
      bullets:['فكرة واضحة','هوية سعودية','نشر ذكي'],
      links:[['سوالف بزنس','https://podcasts.apple.com/us/podcast/%D8%B3%D9%88%D8%A7%D9%84%D9%81-%D8%A8%D8%B2%D9%86%D8%B3-%D9%85%D8%B9-%D9%85%D8%B4%D9%87%D9%88%D8%B1-%D8%A7%D9%84%D8%AF%D8%A8%D9%8A%D8%A7%D9%86/id1239234534']]
    },
    {
      id:'r3',
      title:'تأثير طول الحلقة على جذب المستمعين',
      label:'تقرير صحفي',
      image:'https://images.unsplash.com/photo-1511379938547-c1f69419868d?auto=format&fit=crop&q=80&w=1400',
      excerpt:'هل يفضّل الجمهور الحلقة الطويلة أم المختصرة؟ وما الذي يجعل المستمع يكمل حتى النهاية؟',
      body:[
        'طول الحلقة ليس مشكلة بحد ذاته؛ المشكلة في الإيقاع.',
        'في الصحافة الصوتية، طول الحلقة ينجح عندما يخدم الفكرة، لا عندما يكون مجرد امتداد زمني.'
      ],
      bullets:['الإيقاع أهم','المدة تخدم الفكرة','تنوع أطوال الحلقات'],
      links:[['فنجان','https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827']]
    },
    {
      id:'r4',
      title:'البودكاست المرئي والمسموع: من يفوز؟',
      label:'تقرير صحفي',
      image:'https://images.unsplash.com/photo-1478737270239-2f02b77fc618?auto=format&fit=crop&q=80&w=1400',
      excerpt:'مقارنة بين التجربة المسموعة والتجربة المرئية، ولماذا يجمع بعض صناع المحتوى بينهما.',
      body:[
        'البودكاست المسموع يمنح حرية أكبر أثناء الحركة والعمل، أما المرئي فيضيف طبقة من التواصل البصري والإيماءات.',
        'النجاح هنا ليس في التفوق المطلق لأحد الشكلين، بل في معرفة متى تخدم الصورة الحديث.'
      ],
      bullets:['صوت فقط','صوت + صورة','مرونة التلقي'],
      links:[['يوتيوب','https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D9%85%D8%B1%D8%A6%D9%8A+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A']]
    },
    {
      id:'r5',
      title:'البودكاست النسائي في السعودية وتطوره',
      label:'تقرير صحفي',
      image:'https://images.unsplash.com/photo-1488426862026-3ee34a7d66df?auto=format&fit=crop&q=80&w=1400',
      excerpt:'حضور نسائي لافت في المحتوى الصوتي السعودي، وصياغة مختلفة تعزز التنوع والعمق.',
      body:[
        'برزت أسماء نسائية سعودية في صناعة البودكاست بوصفهن صانعات محتوى ومقدمات وحلقات ومشاريع كاملة.',
        'هذا الحضور لم يقتصر على موضوع واحد؛ بل امتد إلى النفس والاجتماع والقراءة والفكر والقصص الشخصية.'
      ],
      bullets:['تنوع الموضوعات','حضور قيادي','أصوات نسائية'],
      links:[['كنبة السبت','https://podcasts.apple.com/us/podcast/%D9%83%D9%86%D8%A8%D8%A9-%D8%A7%D9%84%D8%B3%D8%A8%D8%AA/id1541797253']]
    },
    {
      id:'r6',
      title:'البرامج الحوارية السعودية ودورها في توسيع دائرة الاستماع',
      label:'تقرير صحفي',
      image:'https://images.unsplash.com/photo-1504384308090-c894fdcc538d?auto=format&fit=crop&q=80&w=1400',
      excerpt:'البرامج الحوارية صارت من أكثر الأشكال التي تمنح البودكاست السعودي هوية واضحة وقدرة على الاستمرار.',
      body:[
        'الحوار الطويل يسمح بفهم أعمق للضيف والفكرة، ويخلق ألفة بين المستمع والمقدم.',
        'في هذا المجال تبرز قيمة البرامج التي تبني حديثًا متدرجًا وواضحًا.'
      ],
      bullets:['حوارات طويلة','ألفة مع الجمهور','هوية واضحة'],
      links:[['سقراط','https://podcasts.apple.com/us/podcast/%D8%B3%D9%82%D8%B1%D8%A7%D8%B7-%D9%85%D8%B9-%D8%B9%D9%85%D8%B1-%D8%A7%D9%84%D8%AC%D8%B1%D9%8A%D8%B3%D9%8A/id1459232606']]
    }
  ];

  const articles = [
    {
      id:'a1',
      title:'حديث بلا قيود… لماذا نجح البودكاست في السعودية؟',
      label:'مقال',
      image:'https://images.unsplash.com/photo-1455390582262-044cdead277a?auto=format&fit=crop&q=80&w=1400',
      excerpt:'مقال يقرأ نجاح البودكاست عبر الحرية في الحديث، والعمق في الطرح، والاتصال المباشر بالجمهور.',
      body:[
        'نجح البودكاست في السعودية لأنه حرّر الحديث من الازدحام البصري، وأعطى الفكرة مساحة لتتنفس.',
        'هذا النوع من المقالات يشرح لماذا أصبح الصوت منافسًا حقيقيًا في المشهد.'
      ],
      bullets:['حرية في الطرح','عمق أكبر','جمهور متفاعل'],
      links:[['فنجان','https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827']]
    },
    {
      id:'a2',
      title:'لماذا يفضّل الشباب البودكاست على التلفزيون؟',
      label:'مقال',
      image:'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1400',
      excerpt:'قراءة في تغيّر العادات الإعلامية لدى الجيل الجديد، ولماذا صار الصوت أقرب من الشاشة.',
      body:[
        'الشباب لا يرفض التلفزيون فقط، بل يبحث عن تجربة تناسب الحركة والمرونة.',
        'البودكاست يمنحهم ذلك؛ فالمحتوى يرافقهم ولا يطالبهم بالتفرغ الكامل أمام الشاشة.'
      ],
      bullets:['مرونة عالية','اختيار شخصي','محتوى طويل'],
      links:[['أبجورة','https://podcasts.apple.com/us/podcast/%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA-%D8%A3%D8%A8%D8%AC%D9%88%D8%B1%D8%A9/id1272687671']]
    },
    {
      id:'a3',
      title:'صنّاع البودكاست: كيف بدأنا وما سر النجاح؟',
      label:'مقابلة صحفية',
      image:'https://images.unsplash.com/photo-1511988617509-a57c8a288659?auto=format&fit=crop&q=80&w=1400',
      excerpt:'مقابلة تضع صناع المحتوى في قلب الحكاية، من البدايات البسيطة إلى جمهور واسع ومتفاعل.',
      body:[
        'النجاح في عالم البودكاست لا يبدأ من معدات كبيرة، بل من فكرة جيدة وصوت واضح وهدف حقيقي.',
        'المقابلة الصحفية هنا تكشف الكواليس، والكتابة، واختيار الضيوف.'
      ],
      bullets:['بدايات بسيطة','فكرة قبل التقنية','جمهور وفيّ'],
      links:[['The Mo Show','https://podcasts.apple.com/sa/podcast/the-mo-show-presented-by-bsf/id1529888455']]
    },
    {
      id:'a4',
      title:'البودكاست النسائي في السعودية… صوت جديد بقوة لافتة',
      label:'مقال',
      image:'https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&q=80&w=1400',
      excerpt:'قراءة في دور الأصوات النسائية في تشكيل ذائقة مختلفة، وإضافة مواضيع أوسع للمشهد.',
      body:[
        'الحضور النسائي في البودكاست السعودي لم يعد هامشيًا، بل أصبح جزءًا واضحًا من الخريطة الصوتية.',
        'هذا التنوع أضاف للمشهد موضوعات أعمق وأقرب للتجربة اليومية.'
      ],
      bullets:['صوت نسائي','تنوع موضوعات','تجربة مختلفة'],
      links:[['كنبة السبت','https://podcasts.apple.com/us/podcast/%D9%83%D9%86%D8%A8%D8%A9-%D8%A7%D9%84%D8%B3%D8%A8%D8%AA/id1541797253']]
    },
    {
      id:'a5',
      title:'متى تتحول الحلقة إلى حديث عام؟',
      label:'مقال',
      image:'https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?auto=format&fit=crop&q=80&w=1400',
      excerpt:'العنوان، الضيف، المقطع المختصر، وسرعة النشر… كلها تصنع من الحلقة حدثًا متداولًا.',
      body:[
        'الحلقة لا تصبح حديثًا عامًا إلا حين تمتلك فكرة صريحة ولحظة قابلة للالتقاط.',
        'لهذا يركز صناع البودكاست على المقدمات الذكية والختام القوي.'
      ],
      bullets:['لحظة قابلة للنشر','عنوان قوي','نقاش واسع'],
      links:[['فنجان','https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827']]
    },
    {
      id:'a6',
      title:'كيف تبني السعودية حضورها الصوتي اليوم؟',
      label:'مقال',
      image:'https://images.unsplash.com/photo-1516321497487-e288fb19713f?auto=format&fit=crop&q=80&w=1400',
      excerpt:'مقال يشرح كيف صارت الهوية المحلية عنصرًا مهمًا في انتشار البودكاست.',
      body:[
        'الهوية المحلية تمنح البرنامج ملامحه الخاصة، وتجعل المستمع يشعر بقرب الموضوع من حياته.',
        'كلما كانت اللغة طبيعية والأسلوب واضحًا، زاد ارتباط الجمهور بالحلقة.'
      ],
      bullets:['هوية محلية','لغة قريبة','ارتباط أعلى'],
      links:[['سوالف بزنس','https://podcasts.apple.com/us/podcast/%D8%B3%D9%88%D8%A7%D9%84%D9%81-%D8%A8%D8%B2%D9%86%D8%B3-%D9%85%D8%B9-%D9%85%D8%B4%D9%87%D9%88%D8%B1-%D8%A7%D9%84%D8%AF%D8%A8%D9%8A%D8%A7%D9%86/id1239234534']]
    }
  ];

  const investigations = [
    {
      id:'i1',
      title:'ليه الجيل الحالي يفضّل البودكاست على التلفزيون التقليدي؟',
      label:'تحقيق صحفي',
      image:'https://images.unsplash.com/photo-1520975916090-3105956dac38?auto=format&fit=crop&q=80&w=1400',
      excerpt:'تحقيق يشرح كيف تغيّرت العادات السمعية، ولماذا صار الصوت أكثر ملاءمة من البث التلفزيوني التقليدي.',
      body:[
        'هذا التحقيق ينظر إلى البودكاست كاستجابة طبيعية لزمن السرعة والمرونة.',
        'سلاسة الاستماع خلال القيادة والعمل والسفر، إلى جانب تنوع الموضوعات، جعلت البودكاست ينافس التلفزيون.'
      ],
      bullets:['مرونة الاستخدام','إيقاع الحياة','تنوع الموضوعات'],
      links:[['كنبة السبت','https://podcasts.apple.com/us/podcast/%D9%83%D9%86%D8%A8%D8%A9-%D8%A7%D9%84%D8%B3%D8%A8%D8%AA/id1541797253']]
    },
    {
      id:'i2',
      title:'تأثير ظهور ولي العهد أو الوزراء في البودكاست على التفاعل والثقة',
      label:'تحقيق صحفي',
      image:'https://images.unsplash.com/photo-1551818255-e6e10975bc17?auto=format&fit=crop&q=80&w=1400',
      excerpt:'كيف يغيّر الظهور الصوتي الرسمي مزاج الجمهور؟ وما الذي يجعله أقرب من اللقاءات التقليدية؟',
      body:[
        'حين يظهر صانع قرار أو شخصية عامة في حوار بودكاستي، تصبح الرسالة أكثر هدوءًا وأقل صدامًا.',
        'هذه المساحة تعيد تشكيل العلاقة بين المواطن والخطاب العام، لأن البودكاست يسمح بمقدار أكبر من الشرح والتفصيل.'
      ],
      bullets:['مساحة هادئة','تفصيل أوضح','ثقة أعلى'],
      links:[['سقراط','https://podcasts.apple.com/us/podcast/%D8%B3%D9%82%D8%B1%D8%A7%D8%B7-%D9%85%D8%B9-%D8%B9%D9%85%D8%B1-%D8%A7%D9%84%D8%AC%D8%B1%D9%8A%D8%B3%D9%8A/id1459232606']]
    },
    {
      id:'i3',
      title:'كيف دخل المسؤولون والشخصيات الكبيرة عالم البودكاست بدل اللقاءات التقليدية',
      label:'تحقيق صحفي',
      image:'https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&q=80&w=1400',
      excerpt:'لماذا أصبح البودكاست خيارًا مفضلًا للحديث الهادئ والواضح بدل التصريحات السريعة؟',
      body:[
        'اللقاءات التقليدية غالبًا ما تكون مقيدة بالوقت والشكل الرسمي، بينما البودكاست يمنح الحديث مساحة إنسانية.',
        'من هنا أصبح البودكاست قناة مناسبة لتوضيح الأفكار الكبرى.'
      ],
      bullets:['شرح أطول','طبيعة إنسانية','بديل هادئ'],
      links:[['The Mo Show','https://podcasts.apple.com/sa/podcast/the-mo-show-presented-by-bsf/id1529888455']]
    }
  ];

  const interviews = [
    {
      id:'m1',
      title:'صنّاع البودكاست: كيف بدأنا وما سر النجاح؟',
      label:'مقابلة',
      image:'https://images.unsplash.com/photo-1545239351-1141bd82e8a6?auto=format&fit=crop&q=80&w=1400',
      excerpt:'مقابلة صحفية مع صناع البودكاست حول البدايات والأفكار والتحديات التي صنعت النجاح.',
      body:[
        'أسئلة مباشرة على صناع المحتوى: لماذا اخترتم البودكاست؟ ما الذي جعل الجمهور يلتفت إليكم؟',
        'المقابلة تكشف الكواليس، وطريقة التسجيل، والبحث، والكتابة، واختيار الضيوف.'
      ],
      bullets:['البدايات','كواليس الإنتاج','أسئلة مباشرة'],
      links:[['فنجان','https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827']]
    },
    {
      id:'m2',
      title:'وراء المايك: كيف تُصنع الحلقة الجيدة؟',
      label:'مقابلة',
      image:'https://images.unsplash.com/photo-1516280030429-27679e5f8e4b?auto=format&fit=crop&q=80&w=1400',
      excerpt:'حديث عن كتابة الأسئلة، ضبط الإيقاع، والتوازن بين العمق والوضوح في الحلقة الصوتية.',
      body:[
        'الحلقة الجيدة لا تأتي صدفة؛ إنها نتيجة تحضير وكتابة وإصغاء وانتباه للتفاصيل.',
        'صوت المقدم هو جزء من الهوية، ونبرة الحديث قد تساوي أحيانًا نصف النجاح.'
      ],
      bullets:['تحضير دقيق','إيقاع متوازن','هوية صوتية'],
      links:[['كنبة السبت','https://podcasts.apple.com/us/podcast/%D9%83%D9%86%D8%A8%D8%A9-%D8%A7%D9%84%D8%B3%D8%A8%D8%AA/id1541797253']]
    },
    {
      id:'m3',
      title:'ماذا تغيّر في المشهد بعد دخول المسؤولين والشخصيات الكبيرة؟',
      label:'مقابلة',
      image:'https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&q=80&w=1400',
      excerpt:'مقابلة تستعرض أثر البودكاست كمنصة أقرب وأهدأ من المنصات التقليدية.',
      body:[
        'عندما يدخل المسؤول أو الشخصية المؤثرة إلى البودكاست، يصبح الحوار أكثر إنسانية.',
        'هذا التغيّر لا يتعلق بشخصية الضيف فقط، بل بطبيعة المنصة التي تسمح بالحكي الطويل.'
      ],
      bullets:['أقرب للناس','لغة أهدأ','انطباع أقوى'],
      links:[['سقراط','https://podcasts.apple.com/us/podcast/%D8%B3%D9%82%D8%B1%D8%A7%D8%B7-%D9%85%D8%B9-%D8%B9%D9%85%D8%B1-%D8%A7%D9%84%D8%AC%D8%B1%D9%8A%D8%B3%D9%8A/id1459232606']]
    }
  ];

  const programs = [
    {
      id:'fanjan',
      title:'فنجان مع عبدالرحمن أبومالح',
      label:'برنامج سعودي حواري',
      kind:'حوارات عميقة',
      fit:'لمن يحب النقاش الهادئ والعمق',
      image:'https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?auto=format&fit=crop&q=80&w=1400',
      excerpt:'من أشهر البرامج الحوارية السعودية، يقدّم مساحة واسعة للنقاش مع ضيوف من مجالات متعددة، ويعتمد على الحوار الطويل الذي يمنح المستمع وقتًا للفهم والتأمل.',
      body:[
        'فنجان يقدّم الحوار كرحلة كاملة، لا كفقرة سريعة؛ لذلك يناسب المستمع الذي يبحث عن فهم أوسع للسياق.',
        'تنبع قوة البرنامج من إيقاعه المتزن، ومن قدرته على ترك مساحة للفكرة حتى تنضج أمام المستمع.'
      ],
      bullets:['حوار أسبوعي','من ثمانية','نبرة هادئة','مناسب للتفكير'],
      source:'https://podcasts.apple.com/us/podcast/%D9%81%D9%86%D8%AC%D8%A7%D9%86-%D9%85%D8%B9-%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86-%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD/id985515827',
      watch:'https://www.youtube.com/results?search_query=%D9%81%D9%86%D8%AC%D8%A7%D9%86+%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B1%D8%AD%D9%85%D9%86+%D8%A3%D8%A8%D9%88%D9%85%D8%A7%D9%84%D8%AD'
    },
    {
      id:'jinaya',
      title:'جناية',
      label:'برنامج سعودي سردي',
      kind:'تشويق وتحقيق',
      fit:'لمن يفضّل الجرائم والسرد المشوق',
      image:'https://images.unsplash.com/photo-1455390582262-044cdead277a?auto=format&fit=crop&q=80&w=1400',
      excerpt:'بودكاست بطابع تشويقي ونفسي يتتبع خيوط الجرائم ويحللها، فيأخذ المستمع إلى مسارات متعددة من الإثارة والتفكير والتأمل.',
      body:[
        'جناية يقدم سردًا متماسكًا ينطلق من القصة الواقعية ثم يتدرج إلى التحليل والربط.',
        'هذا النوع من البودكاست يلقى قبولًا عند جمهور يحب التفاصيل، ويبحث عن قصة تُروى ببطء وتُفهم من أكثر من زاوية.'
      ],
      bullets:['شبكة مايكس','قصص واقعية','إيقاع سردي','تشويق عالي'],
      source:'https://podcasts.apple.com/sa/podcast/%D8%AC%D9%86%D8%A7%D9%8A%D8%A9/id1529103794',
      watch:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%AC%D9%86%D8%A7%D9%8A%D8%A9'
    },
    {
      id:'mosho',
      title:'The Mo Show Presented by BSF',
      label:'برنامج سعودي باللغة الإنجليزية',
      kind:'حوارات عالمية',
      fit:'للمهتمين بالمحتوى الدولي',
      image:'https://images.unsplash.com/photo-1516280440614-37939bbacd81?auto=format&fit=crop&q=80&w=1400',
      excerpt:'بودكاست باللغة الإنجليزية يقدّم حوارات مع ضيوف من مجالات مختلفة، ويعكس حضورًا سعوديًا معاصرًا بصوت عالمي وإيقاع واضح.',
      body:[
        'The Mo Show يقدم نموذجًا مختلفًا في المشهد السعودي؛ فهو يفتح الباب أمام الجمهور الذي يفضّل الاستماع باللغة الإنجليزية.',
        'يعتمد البرنامج على حوارات متنوعة تلامس مجالات الثقافة والمعرفة والإنجاز الشخصي.'
      ],
      bullets:['English podcast','Saudi voice','حوارات متنوعة','جمهور عالمي'],
      source:'https://podcasts.apple.com/sa/podcast/the-mo-show-presented-by-bsf/id1529888455',
      watch:'https://www.youtube.com/results?search_query=The+Mo+Show+Presented+by+BSF'
    },
    {
      id:'sardyat',
      title:'سرديات',
      label:'برنامج سعودي ثقافي',
      kind:'أدب وفكر',
      fit:'لمن يحب السرد والثقافة',
      image:'https://images.unsplash.com/photo-1512872302902-5f4fd2986037?auto=format&fit=crop&q=80&w=1400',
      excerpt:'بودكاست يحاور كتّابًا وأدباء ومفكرين لمناقشة قضايا الفكر والأدب العربي والتحولات الاجتماعية والثقافية.',
      body:[
        'سرديات يقدّم مساحة فكرية وثقافية تتقاطع فيها القصة مع الفكرة، واللغة مع التحليل.',
        'يبرز البرنامج حين تكون الفكرة هي البطل؛ فهو لا يكتفي بعرض المعلومة، بل يربطها بالنقاش الثقافي.'
      ],
      bullets:['فكر وأدب','سرد ثقافي','حوارات متأنية','محتوى عربي'],
      source:'https://podcasts.apple.com/sa/podcast/sardyat-%D8%B3%D8%B1%D8%AF%D9%8A%D8%A7%D8%AA/id1647955514',
      watch:'https://www.youtube.com/results?search_query=%D8%B3%D8%B1%D8%AF%D9%8A%D8%A7%D8%AA+%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA'
    },
    {
      id:'socrates',
      title:'سقراط مع عمر الجريسي',
      label:'برنامج سعودي تحليلي',
      kind:'فكر وتحول',
      fit:'للمهتمين بالنقاشات العميقة',
      image:'https://images.unsplash.com/photo-1483058712412-4245e9b90334?auto=format&fit=crop&q=80&w=1400',
      excerpt:'برنامج يفتح أسئلة كبيرة حول التحولات في السعودية، ويضع قضايا المجتمع والاقتصاد والإدارة على طاولة الحوار.',
      body:[
        'سقراط يقدّم حوارًا يركّز على الأسئلة الكبيرة، وعلى قراءة التحولات في المجتمع السعودي من زاوية فكرية وإدارية واقتصادية.',
        'يميل البرنامج إلى بناء الفكرة على مراحل، فيُشعر المستمع أنه أمام نقاش طويل لا مجرد ردود قصيرة.'
      ],
      bullets:['من ثمانية','تحليلي','يناقش التحولات','لغة واضحة'],
      source:'https://podcasts.apple.com/us/podcast/%D8%B3%D9%82%D8%B1%D8%A7%D8%B7-%D9%85%D8%B9-%D8%B9%D9%85%D8%B1-%D8%A7%D9%84%D8%AC%D8%B1%D9%8A%D8%B3%D9%8A/id1459232606',
      watch:'https://www.youtube.com/results?search_query=%D8%B3%D9%82%D8%B1%D8%A7%D8%B7+%D8%B9%D9%85%D8%B1+%D8%A7%D9%84%D8%AC%D8%B1%D9%8A%D8%B3%D9%8A'
    },
    {
      id:'kanbat',
      title:'كنبة السبت',
      label:'برنامج سعودي نفسي/اجتماعي',
      kind:'نفس واجتماع',
      fit:'للمساحات الهادئة والحديث اليومي',
      image:'https://images.unsplash.com/photo-1529156069898-49953e39b3ac?auto=format&fit=crop&q=80&w=1400',
      excerpt:'بودكاست بطابع نفسي واجتماعي وفلسفي، يقدّم مساحة هادئة وممتعة للنقاش والفهم الذاتي والحديث عن الحياة اليومية.',
      body:[
        'كنبة السبت من البرامج التي تقدّم مزيجًا من الراحة النفسية والحوار الاجتماعي، وتخاطب المستمع الذي يبحث عن مساحة قريبة من الذات.',
        'يمتاز البرنامج بإيقاعه الهادئ وموضوعاته التي تقترب من التجربة الإنسانية مباشرة.'
      ],
      bullets:['أفنان الغامدي','نفسي واجتماعي','مساحة هادئة','ترشيح مود هادئ'],
      source:'https://podcasts.apple.com/us/podcast/%D9%83%D9%86%D8%A8%D8%A9-%D8%A7%D9%84%D8%B3%D8%A8%D8%AA/id1541797253',
      watch:'https://www.youtube.com/results?search_query=%D9%83%D9%86%D8%A8%D8%A9+%D8%A7%D9%84%D8%B3%D8%A8%D8%AA'
    },
    {
      id:'abjora',
      title:'بودكاست أبجورة',
      label:'برنامج سعودي ثقافي',
      kind:'فكر وإلهام',
      fit:'لمن يحب التأمل واللغة الجميلة',
      image:'https://images.unsplash.com/photo-1516542076529-1ea3854896b1?auto=format&fit=crop&q=80&w=1400',
      excerpt:'بودكاست يتحدث عنك حينًا ويتحدث معك أحيانًا، ويقدّم مساحة ثقافية وصوتًا هادئًا يقترب من المشاعر والأفكار.',
      body:[
        'أبجورة من البرامج التي صنعت حضورًا مميزًا في السعودية والعالم العربي، فهو يعتني باللغة والجو العام.',
        'تظهر قوة البرنامج في حلقاته التأملية التي تتناول الإنسان والذاكرة والحنين والفقد والعودة.'
      ],
      bullets:['لغة جميلة','محتوى تأملي','إلهام','مساحة ثقافية'],
      source:'https://podcasts.apple.com/us/podcast/%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA-%D8%A3%D8%A8%D8%AC%D9%88%D8%B1%D8%A9/id1272687671',
      watch:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%A3%D8%A8%D8%AC%D9%88%D8%B1%D8%A9'
    },
    {
      id:'sawalif',
      title:'سوالف بزنس مع مشهور الدبيان',
      label:'برنامج سعودي أعمال',
      kind:'أعمال وريادة',
      fit:'للأعمال والريادة وقصص النجاح',
      image:'https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&q=80&w=1400',
      excerpt:'بودكاست للمهتمين بالبزنس وريادة الأعمال، يقدّم تجارب ضيوفه بتفاصيلها وبأسلوب مباشر بعيدًا عن المجاملة.',
      body:[
        'سوالف بزنس يفتح نافذة على التجارب العملية في عالم الأعمال، ويقدّم قصصًا فعلية عن التأسيس والنمو والتحديات.',
        'البرنامج يعتمد على الحوار مع أصحاب التجارب، وبالتالي يمنح المستمع مادة غنية للتعلم.'
      ],
      bullets:['بزنس وريادة','قصص واقعية','مفيد للمبتدئين','حوار مباشر'],
      source:'https://podcasts.apple.com/us/podcast/%D8%B3%D9%88%D8%A7%D9%84%D9%81-%D8%A8%D8%B2%D9%86%D8%B3-%D9%85%D8%B9-%D9%85%D8%B4%D9%87%D9%88%D8%B1-%D8%A7%D9%84%D8%AF%D8%A8%D9%8A%D8%A7%D9%86/id1239234534',
      watch:'https://www.youtube.com/results?search_query=%D8%B3%D9%88%D8%A7%D9%84%D9%81+%D8%A8%D8%B2%D9%86%D8%B3'
    }
  ];

  const extraPrograms = [
    {
      id:'extra1',
      title:'موطن',
      label:'بودكاست سعودي',
      kind:'مجتمع وقصص',
      fit:'القصص الاجتماعية والسيرة',
      image:'https://images.unsplash.com/photo-1492691527719-9e3adfcfdbd6?auto=format&fit=crop&q=80&w=1400',
      excerpt:'برنامج سعودي يركز على القصص اليومية والموضوعات الاجتماعية، ويقدّمها بصوت قريب وأسلوب مرتب وواضح.',
      body:[
        'موطن يلتقط القصص من داخل المجتمع ويعيد تقديمها بطريقة هادئة ومفهومة.',
        'البرنامج ينسجم مع فكرة الصحيفة الإلكترونية لأنه يقدّم حكايات ومعنى وسياقًا.'
      ],
      bullets:['مجتمع','قصص','سيرة'],
      source:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D9%85%D9%88%D8%B7%D9%86',
      watch:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D9%85%D9%88%D8%B7%D9%86'
    },
    {
      id:'extra2',
      title:'نقطة',
      label:'بودكاست سعودي',
      kind:'مختصر ومركز',
      fit:'من يحب الأفكار السريعة والواضحة',
      image:'https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&q=80&w=1400',
      excerpt:'برنامج سعودي يقدم فكرة مركزة في مساحة صوتية قصيرة، ويعتمد على الإيجاز والوضوح والطرح المباشر.',
      body:[
        'نقطة مناسب لمن يفضّل المحتوى المقتضب الذي يذهب مباشرة إلى الفكرة الأساسية.',
        'هذا النوع من البرامج مهم في الصحافة الصوتية لأنه يملأ وقت الاستماع القصير دون إطالة.'
      ],
      bullets:['مختصر','مركز','واضح'],
      source:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D9%86%D9%82%D8%B7%D8%A9+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A',
      watch:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D9%86%D9%82%D8%B7%D8%A9+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A'
    },
    {
      id:'extra3',
      title:'جلسة',
      label:'بودكاست سعودي',
      kind:'حوار خفيف',
      fit:'الأجواء الهادئة والمجالس الصوتية',
      image:'https://images.unsplash.com/photo-1524678606370-a47ad25cb82a?auto=format&fit=crop&q=80&w=1400',
      excerpt:'برنامج سعودي يدور حول الجلسات الهادئة والأحاديث المرنة التي تناسب الاستماع اليومي وتمنح شعورًا مريحًا.',
      body:[
        'جلسة يقدّم مساحة صوتية مرنة تشبه الجلسات الودية.',
        'يستفيد من قربه من اليومي، وهو ما يجعله حلقة وصل جيدة بين الترفيه والحوار.'
      ],
      bullets:['جلسات','خفيف','حوار'],
      source:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%AC%D9%84%D8%B3%D8%A9+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A',
      watch:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%AC%D9%84%D8%B3%D8%A9+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A'
    },
    {
      id:'extra4',
      title:'أثر',
      label:'بودكاست سعودي',
      kind:'إلهام وتنمية',
      fit:'التحفيز والقصص الملهمة',
      image:'https://images.unsplash.com/photo-1519389950473-47ba0277781c?auto=format&fit=crop&q=80&w=1400',
      excerpt:'برنامج سعودي يسلط الضوء على الأثر الإيجابي للأفكار والتجارب، ويُقدّم بأسلوب هادئ ومهني.',
      body:[
        'أثر برنامج يربط بين القصة والنتيجة، ويقدّم محتوى يمكن أن يلهم المستمع.',
        'يناسب هذا النوع من البرامج قسم التفاعل الترشيحي.'
      ],
      bullets:['إلهام','تنمية','أثر'],
      source:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%A3%D8%AB%D8%B1+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A',
      watch:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%A3%D8%AB%D8%B1+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A'
    },
    {
      id:'extra5',
      title:'صدى',
      label:'بودكاست سعودي',
      kind:'صوت وثقافة',
      fit:'الاستماع الهادئ والمتابعة العامة',
      image:'https://images.unsplash.com/photo-1483059591401-127231be4b8d?auto=format&fit=crop&q=80&w=1400',
      excerpt:'برنامج سعودي يقدّم صدى الأفكار والموضوعات العامة بصوت متزن وصياغة واضحة وسهلة المتابعة.',
      body:[
        'صدى يقدّم أسلوبًا يوازن بين وضوح الفكرة وجاذبية السرد.',
        'يمثل هذا البرنامج مثالًا على البودكاست الذي يشتغل على الفكرة أكثر من الشكل.'
      ],
      bullets:['صوت','ثقافة','متابعة'],
      source:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%B5%D8%AF%D9%89+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A',
      watch:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%B5%D8%AF%D9%89+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A'
    },
    {
      id:'extra6',
      title:'بعد الغروب',
      label:'بودكاست سعودي',
      kind:'أحاديث مسائية',
      fit:'الاستماع الليلي والهدوء',
      image:'https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&q=80&w=1400',
      excerpt:'برنامج سعودي يناسب الوقت المسائي، ويعتمد على إيقاع هادئ وموضوعات مريحة ومرنة في الطرح.',
      body:[
        'بعد الغروب يناسب الجو الهادئ في المساء، ويضع المستمع في سياق مناسب للراحة والتأمل.',
        'البرنامج مهم لأنه يبيّن كيف تخدم الصيغة الزمنية التجربة الصوتية.'
      ],
      bullets:['ليل','هدوء','جلسة'],
      source:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%A8%D8%B9%D8%AF+%D8%A7%D9%84%D8%BA%D8%B1%D9%88%D8%A8+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A',
      watch:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%A8%D8%B9%D8%AF+%D8%A7%D9%84%D8%BA%D8%B1%D9%88%D8%A8+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A'
    },
    {
      id:'extra7',
      title:'مفاتيح',
      label:'بودكاست سعودي',
      kind:'تحليل وفهم',
      fit:'اللغة الواضحة والأفكار العملية',
      image:'https://images.unsplash.com/photo-1504384308090-c894fdcc538d?auto=format&fit=crop&q=80&w=1400',
      excerpt:'برنامج سعودي يفتح أبوابًا لفهم موضوعات مختلفة عبر طرح عملي وتناول مباشر للفكرة.',
      body:[
        'مفاتيح يقدّم المحتوى على هيئة مفاتيح للفهم، لذلك ينسجم مع القارئ الذي يريد أن يخرج بفكرة واضحة بعد الحلقة.',
        'هذا الأسلوب يجعل البرنامج مناسبًا كأحد عناوين التوصية في الموقع.'
      ],
      bullets:['فهم','تحليل','مباشر'],
      source:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D9%85%D9%81%D8%A7%D8%AA%D9%8A%D8%AD+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A',
      watch:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D9%85%D9%81%D8%A7%D8%AA%D9%8A%D8%AD+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A'
    },
    {
      id:'extra8',
      title:'حكاية يوم',
      label:'بودكاست سعودي',
      kind:'قصصي يومي',
      fit:'القصص الخفيفة والتجارب اليومية',
      image:'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=1400',
      excerpt:'برنامج سعودي يلتقط تفاصيل اليوم ويعيد سردها بشكل ممتع وقريب من المستمع.',
      body:[
        'حكاية يوم يعالج التفاصيل اليومية الصغيرة ويمنحها معنى أكبر.',
        'يساعد هذا البرنامج الموقع على تقديم تنوع واضح بين المحتوى الثقيل والخفيف.'
      ],
      bullets:['يومي','قصصي','خفيف'],
      source:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%AD%D9%83%D8%A7%D9%8A%D8%A9+%D9%8A%D9%88%D9%85+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A',
      watch:'https://www.youtube.com/results?search_query=%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA+%D8%AD%D9%83%D8%A7%D9%8A%D8%A9+%D9%8A%D9%88%D9%85+%D8%B3%D8%B9%D9%88%D8%AF%D9%8A'
    }
  ];

  const videos = [
    {
      title:'قصص من أيام العرب مع حمود الصاهود في مخيال | مع عبدالله البندر',
      desc:'حلقة مرتبطة بعالم البودكاست والقصص العربية، وتظهر في صفحة الفيديو بشكل مباشر.',
      embed:'https://www.youtube.com/embed/ulDugCU4L1M'
    },
    {
      title:'كلامك يقلب موازين حياتك | د. سعد العريفي',
      desc:'حلقة تتناول أثر الكلمات وكيفية توظيفها في الحياة والعلاقات وصناعة التأثير.',
      embed:'https://www.youtube.com/embed/OJ2_PLte5nk'
    },
    {
      title:'مذكرات رجل أمن سعودي | بودكاست فنجان',
      desc:'حلقة من فنجان تظهر داخل صفحة الفيديو مع بطاقة ومشغل مباشر.',
      embed:'https://www.youtube.com/embed/OetssqWJycg'
    },
    {
      title:'كلامك يقلب موازين حياتك | د. سعد العريفي',
      desc:'إعادة عرض للرابط الرابع كما أرسلته، داخل قسم الفيديو نفسه.',
      embed:'https://www.youtube.com/embed/OJ2_PLte5nk'
    }
  ];

  const quotes = ['“مو كل صمت راحة.”', '“أحيانًا الصوت يغيّر طريقة تفكيرك.”', '“من هنا نُعيد تعريف المستحيل.”', '“مُلهم.. نبض البودكاست السعودي.”', '“صوت السعودية المسموع.. يرويه لكم مُلهم.”'];

  const panels = {
    home: document.getElementById('panel-home'),
    news: document.getElementById('panel-news'),
    reports: document.getElementById('panel-reports'),
    articles: document.getElementById('panel-articles'),
    investigations: document.getElementById('panel-investigations'),
    interviews: document.getElementById('panel-interviews'),
    programs: document.getElementById('panel-programs'),
    interactive: document.getElementById('panel-interactive'),
    videos: document.getElementById('panel-videos')
  };

  const programMap = Object.fromEntries([...programs, ...extraPrograms].map(p => [p.id, p]));
  const itemMap = Object.fromEntries([...news, ...reports, ...articles, ...investigations, ...interviews, ...programs, ...extraPrograms].map(x => [x.id, x]));

  const els = {
    toastContainer: document.getElementById('toastContainer'),
    navButtons: document.querySelectorAll('.nav-btn'),
    jumpButtons: document.querySelectorAll('.jump-btn'),
    devBtn: document.getElementById('devBtn'),
    detailModal: document.getElementById('detailModal'),
    devModal: document.getElementById('devModal'),
    voteModal: document.getElementById('voteModal'),
    newsGrid: document.getElementById('newsGrid'),
    reportsGrid: document.getElementById('reportsGrid'),
    articlesGrid: document.getElementById('articlesGrid'),
    investigationsGrid: document.getElementById('investigationsGrid'),
    interviewsGrid: document.getElementById('interviewsGrid'),
    programGrid: document.getElementById('programGrid'),
    extraGrid: document.getElementById('extraGrid'),
    extraWrap: document.getElementById('extraWrap'),
    videoGrid: document.getElementById('videoGrid'),
    detailImage: document.getElementById('detailImage'),
    detailLabel: document.getElementById('detailLabel'),
    detailTitle: document.getElementById('detailTitle'),
    detailExcerpt: document.getElementById('detailExcerpt'),
    detailBody: document.getElementById('detailBody'),
    detailBullets: document.getElementById('detailBullets'),
    detailLinks: document.getElementById('detailLinks'),
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
    programSearch: document.getElementById('programSearch'),
    toggleExtraBtn: document.getElementById('toggleExtraBtn')
  };

  const state = {
    activeProgramId: 'fanjan',
    currentMood: 'ضحك',
    quoteIndex: 0,
    votes: JSON.parse(localStorage.getItem('mulham_votes_v11') || 'null') || { fanjan:0, jinaya:0, mosho:0, sardyat:0 },
    extraVisible: false
  };

  function toast(message){
    const el = document.createElement('div');
    el.className = 'bg-white border border-black/5 shadow-2xl rounded-2xl px-4 py-3 font-bold text-[#4E4A43] min-w-[220px] soft';
    el.textContent = message;
    els.toastContainer.appendChild(el);
    setTimeout(() => {
      el.style.opacity = '0';
      el.style.transform = 'translateY(8px)';
      el.style.transition = 'all .25s ease';
      setTimeout(() => el.remove(), 250);
    }, 1800);
  }

  function showPanel(name){
    Object.entries(panels).forEach(([key, panel]) => panel.classList.toggle('active', key === name));
    els.navButtons.forEach(btn => btn.classList.toggle('active', btn.dataset.panel === name));
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  function openModal(modal){
    modal.classList.remove('hidden');
    modal.classList.remove('modal-hidden');
    modal.classList.add('modal-visible');
  }

  function closeModal(modal){
    modal.classList.add('modal-hidden');
    modal.classList.remove('modal-visible');
    setTimeout(() => modal.classList.add('hidden'), 180);
  }

  function htmlBullets(arr){
    return arr.map(b => `<span class="px-3 py-1 rounded-full text-sm font-bold chip">${b}</span>`).join('');
  }

  function renderCard(item, kind = 'item'){
    return `
      <article class="bg-white rounded-[2rem] overflow-hidden shadow-xl border border-black/5 card-hover soft ${kind === 'program' ? 'program-card' : ''}" data-id="${item.id}">
        <div class="relative h-56 overflow-hidden">
          <img src="${item.image}" alt="${item.title}" class="w-full h-full object-cover" loading="lazy">
          <div class="absolute inset-0 bg-gradient-to-t from-black/35 via-transparent to-transparent"></div>
          <div class="absolute top-4 right-4 px-3 py-1 rounded-full bg-white/90 text-[#7A5A2E] font-black text-sm">${item.label}</div>
        </div>
        <div class="p-6">
          <h3 class="text-2xl font-black text-[#7A5A2E] leading-tight mb-3">${item.title}</h3>
          <p class="text-[#5d594f] leading-8 mb-5">${item.excerpt}</p>
          <div class="flex flex-wrap gap-2 mb-5">${htmlBullets(item.bullets.slice(0, 3))}</div>
          <button type="button" class="${kind === 'program' ? 'open-program-btn' : 'open-detail-btn'} w-full bg-[#7A5A2E] text-white px-4 py-3 rounded-2xl font-black soft hover:scale-[1.02]" data-id="${item.id}">فتح</button>
        </div>
      </article>
    `;
  }

  function renderGrid(items, grid, kind = 'item'){
    grid.innerHTML = items.map(item => renderCard(item, kind)).join('');
  }

  function renderVideoGrid(){
    els.videoGrid.innerHTML = videos.map(v => `
      <div class="bg-white rounded-[2rem] overflow-hidden shadow-xl border border-black/5 card-hover soft">
        <iframe class="w-full h-64" src="${v.embed}" title="${v.title}" allowfullscreen></iframe>
        <div class="p-5">
          <h3 class="font-black text-xl text-[#7A5A2E] mb-2">${v.title}</h3>
          <p class="text-[#5d594f] leading-7">${v.desc}</p>
        </div>
      </div>
    `).join('');
  }

  function renderVoteCounts(){
    els.voteFanjan.textContent = state.votes.fanjan;
    els.voteJinaya.textContent = state.votes.jinaya;
    els.voteMosho.textContent = state.votes.mosho;
    els.voteSardyat.textContent = state.votes.sardyat;

    els.resFanjan.textContent = state.votes.fanjan;
    els.resJinaya.textContent = state.votes.jinaya;
    els.resMosho.textContent = state.votes.mosho;
    els.resSardyat.textContent = state.votes.sardyat;
  }

  function renderHours(){
    els.hoursValue.textContent = `${els.hoursSlider.value} ساعة`;
  }

  function renderQuote(){
    els.quoteBox.textContent = quotes[state.quoteIndex];
  }

  function showDetail(item){
    if (!item) return;
    state.activeProgramId = item.id;
    els.detailImage.src = item.image;
    els.detailImage.alt = item.title;
    els.detailLabel.textContent = item.label;
    els.detailTitle.textContent = item.title;
    els.detailExcerpt.textContent = item.excerpt;
    els.detailBody.innerHTML = item.body.map(p => `<p>${p}</p>`).join('');
    els.detailBullets.innerHTML = htmlBullets(item.bullets);
    const links = item.links || [[ 'المصدر الرسمي', item.source || '#' ]];
    els.detailLinks.innerHTML = links.map(l => `<a href="${l[1]}" target="_blank" rel="noopener noreferrer" class="px-4 py-3 rounded-2xl bg-[#7A5A2E] text-white font-black soft hover:scale-[1.03]">${l[0]}</a>`).join('');
    openModal(els.detailModal);
  }

  function recommend(){
    const map = { 'ضحك':'mosho', 'تفكير':'fanjan', 'نفسي':'kanbat', 'تشويق':'jinaya' };
    const p = programMap[map[state.currentMood] || 'fanjan'];
    if (!p) return;
    state.activeProgramId = p.id;
    els.recommendTitle.textContent = p.title;
    els.recommendText.textContent = p.excerpt;
    els.recommendBox.classList.remove('hidden');
    els.moodRecommendation.innerHTML = `
      <div class="font-black text-2xl text-[#7A5A2E] mb-2">${p.title}</div>
      <p class="text-[#5d594f] leading-8">${p.excerpt}</p>
      <div class="mt-4 flex flex-wrap gap-2">${htmlBullets(p.bullets.slice(0, 3))}</div>
    `;
    toast('تم اقتراح برنامج مناسب');
  }

  function searchPrograms(term){
    const q = term.trim().toLowerCase();
    document.querySelectorAll('.program-card').forEach(card => {
      const p = programMap[card.dataset.id];
      const text = `${p.title} ${p.excerpt} ${p.label} ${p.kind} ${p.fit} ${p.body.join(' ')} ${p.bullets.join(' ')}`.toLowerCase();
      card.style.display = text.includes(q) ? '' : 'none';
    });
  }

  renderGrid(news, els.newsGrid);
  renderGrid(reports, els.reportsGrid);
  renderGrid(articles, els.articlesGrid);
  renderGrid(investigations, els.investigationsGrid);
  renderGrid(interviews, els.interviewsGrid);
  renderGrid(programs, els.programGrid, 'program');
  renderGrid(extraPrograms, els.extraGrid, 'program');
  renderVideoGrid();
  renderVoteCounts();
  renderHours();
  renderQuote();
  recommend();
  showPanel('home');

  els.navButtons.forEach(btn => {
    btn.addEventListener('click', () => {
      showPanel(btn.dataset.panel);
      toast('تم فتح القسم');
    });
  });

  els.jumpButtons.forEach(btn => {
    btn.addEventListener('click', () => {
      showPanel(btn.dataset.panel);
    });
  });

  els.devBtn.addEventListener('click', () => openModal(els.devModal));

  document.addEventListener('click', (e) => {
    const openDetailBtn = e.target.closest('.open-detail-btn');
    if (openDetailBtn){
      showDetail(itemMap[openDetailBtn.dataset.id]);
      return;
    }

    const openProgramBtn = e.target.closest('.open-program-btn');
    if (openProgramBtn){
      showDetail(programMap[openProgramBtn.dataset.id]);
      return;
    }

    const closeTarget = e.target.closest('[data-close]');
    if (closeTarget){
      const id = closeTarget.dataset.close;
      if (id === 'detail') closeModal(els.detailModal);
      if (id === 'dev') closeModal(els.devModal);
      if (id === 'vote') closeModal(els.voteModal);
    }
  });

  els.openRecommended.addEventListener('click', () => {
    showDetail(programMap[state.activeProgramId] || programMap.fanjan);
  });

  els.recommendBtn.addEventListener('click', recommend);

  els.openVoteBtn.addEventListener('click', () => {
    els.voteDone.classList.add('hidden');
    els.voteForm.classList.remove('hidden');
    openModal(els.voteModal);
    toast('اختر برنامجك وصوّت');
  });

  els.programSearch.addEventListener('input', (e) => searchPrograms(e.target.value));

  els.toggleExtraBtn.addEventListener('click', () => {
    state.extraVisible = !state.extraVisible;
    els.extraWrap.classList.toggle('hidden', !state.extraVisible);
    els.toggleExtraBtn.textContent = state.extraVisible ? 'إخفاء المزيد' : 'إظهار المزيد';
    toast(state.extraVisible ? 'تم عرض البرامج الإضافية' : 'تم إخفاء البرامج الإضافية');
  });

  els.hoursSlider.addEventListener('input', renderHours);

  els.nextQuoteBtn.addEventListener('click', () => {
    state.quoteIndex = (state.quoteIndex + 1) % quotes.length;
    renderQuote();
  });

  document.querySelectorAll('.mood-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      state.currentMood = btn.dataset.mood;
      els.currentMood.textContent = state.currentMood;
      toast(`المود الحالي: ${state.currentMood}`);
      recommend();
    });
  });

  document.querySelectorAll('.quiz-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      const p = programMap[btn.dataset.result] || programMap.fanjan;
      els.quizResult.innerHTML = `<div class="font-black text-2xl text-[#7A5A2E] mb-2">${p.title}</div><p class="text-[#5d594f] leading-8">${p.excerpt}</p>`;
    });
  });

  els.voteForm.addEventListener('submit', (e) => {
    e.preventDefault();
    const selected = new FormData(els.voteForm).get('vote') || 'sardyat';
    state.votes[selected] = (state.votes[selected] || 0) + 1;
    localStorage.setItem('mulham_votes_v11', JSON.stringify(state.votes));
    renderVoteCounts();
    els.voteForm.classList.add('hidden');
    els.voteDone.classList.remove('hidden');
    toast('تم تسجيل الصوت');
  });

  document.addEventListener('keydown', (e) => {
    if (e.key === 'Escape') {
      closeModal(els.detailModal);
      closeModal(els.devModal);
      closeModal(els.voteModal);
    }
  });
});
</script>

</body>
</html>
