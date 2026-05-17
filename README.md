<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>مُلهم | الصحيفة الإلكترونية للبودكاست السعودي</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700;900&family=Tajawal:wght@400;500;700;900&display=swap" rel="stylesheet">
  <style>
    :root{--bg:#f4f1ea;--brown:#7a5a2e;--olive:#7a856f;--text:#4e4a43;--card:#ffffff;--line:rgba(122,90,46,.12)}
    html{scroll-behavior:smooth}
    body{margin:0;background:var(--bg);color:var(--text);font-family:'Tajawal',sans-serif;overflow-x:hidden;touch-action:manipulation}
    a,button,input,label{touch-action:manipulation}
    .display-font{font-family:'Amiri',serif}
    .soft{transition:all .22s ease}
    .glass{background:rgba(255,255,255,.84);backdrop-filter:blur(18px);-webkit-backdrop-filter:blur(18px)}
    .page{display:none;min-height:100vh;animation:fade .22s ease-out;position:relative;z-index:2}
    .page.active{display:block}
    @keyframes fade{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}
    .nav-active{background:var(--brown)!important;color:#fff!important;box-shadow:0 8px 24px rgba(122,90,46,.18)}
    .card{background:var(--card);border:1px solid rgba(0,0,0,.05);box-shadow:0 14px 30px rgba(122,90,46,.08)}
    .card-hover:hover{transform:translateY(-6px);box-shadow:0 18px 40px rgba(122,90,46,.14)}
    .chip{border:1px solid rgba(122,90,46,.12);background:rgba(122,90,46,.08);color:var(--brown)}
    .pill{display:inline-flex;align-items:center;gap:.45rem;padding:.45rem .8rem;border-radius:999px;background:#fff;border:1px solid rgba(0,0,0,.06);font-weight:700}
    .hero-badge{position:absolute;top:16px;left:16px;z-index:2;background:rgba(122,90,46,.82);color:#fff;font-weight:900;padding:.45rem .9rem;border-radius:999px;box-shadow:0 8px 24px rgba(0,0,0,.14)}
    .image-frame{position:relative;overflow:hidden;border-radius:1.5rem;background:#e9e2d8}
    .image-frame img{width:100%;height:100%;display:block;object-fit:cover}
    .image-frame::after{content:"";position:absolute;inset:0;background:linear-gradient(180deg,transparent 50%,rgba(0,0,0,.42) 100%);pointer-events:none}
    .section-title{font-size:clamp(2rem,4vw,3.2rem);line-height:1.1;font-weight:900;color:var(--brown);letter-spacing:-.02em}
    .section-sub{color:var(--olive);font-size:1.05rem;line-height:1.9}
    .content p{line-height:1.9;margin-bottom:.35rem;font-size:1.06rem}
    .ticker-shell{overflow:hidden;width:100%;border-radius:1.5rem}
    .ticker-track{display:flex;width:max-content;will-change:transform;animation:ticker 20s linear infinite}
    .ticker-chip{display:inline-flex;align-items:center;white-space:nowrap;padding:0 1.75rem;font-weight:900;font-size:1rem;color:var(--brown)}
    @keyframes ticker{from{transform:translateX(0)}to{transform:translateX(-50%)}}
    .ref-link{color:#1d4ed8;text-decoration:underline;word-break:break-all}
    .quote-mark{font-size:2.6rem;line-height:1;color:var(--brown)}
    .no-scrollbar{scrollbar-width:none}
    .no-scrollbar::-webkit-scrollbar{display:none}
    .overlay-hidden{opacity:0;pointer-events:none;transform:translateY(10px) scale(.99)}
    .overlay-visible{opacity:1;pointer-events:auto;transform:translateY(0) scale(1)}
    .section-box{border:1px solid var(--line);border-radius:1.5rem;background:#fff;box-shadow:0 14px 30px rgba(122,90,46,.08)}
    @media (max-width:640px){.hero-badge{font-size:.75rem}.ticker-chip{padding:0 1.1rem;font-size:.95rem}}
  </style>
</head>
<body>
  <div class="fixed inset-0 -z-10 pointer-events-none opacity-[0.035]">
    <div class="absolute top-0 left-0 w-full h-full bg-[radial-gradient(circle_at_top_left,#7a856f,transparent_35%)]"></div>
    <div class="absolute bottom-0 right-0 w-full h-full bg-[radial-gradient(circle_at_bottom_right,#7a5a2e,transparent_35%)]"></div>
  </div>
  <div id="toastBox" class="fixed bottom-5 left-5 z-[260] space-y-3 pointer-events-none"></div>

  <!-- IMAGE MANIFEST: عدّل الصور من هنا بسهولة -->
  <script>
    const IMAGE_MANIFEST = {
  "programs": [
    {
      "title": "الحلقة الأولى: البودكاست مع ولي العهد",
      "src": "https://i.ytimg.com/vi/MnKoES8rcKA/hqdefault.jpg",
      "url": "https://youtu.be/MnKoES8rcKA",
      "pageUrl": "https://www.youtube.com/results?search_query=الحلقة+الخاصة"
    },
    {
      "title": "مذكرات رجل أمن سعودي | بودكاست فنجان",
      "src": "https://i.ytimg.com/vi/OetssqWJycg/hqdefault.jpg",
      "url": "https://youtu.be/OetssqWJycg",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+فنجان"
    },
    {
      "title": "الحكم لله ثم لعبدالعزيز | بودكاست فنجان",
      "src": "https://i.ytimg.com/vi/HwVwgIBFj_4/hqdefault.jpg",
      "url": "https://youtu.be/HwVwgIBFj_4",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+فنجان"
    },
    {
      "title": "الحل السعودي للعالم في الذكاء الاصطناعي | بودكاست سقراط",
      "src": "https://i.ytimg.com/vi/dzc0XEKzCRM/hqdefault.jpg",
      "url": "https://youtu.be/dzc0XEKzCRM",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+سقراط"
    },
    {
      "title": "كابتن طيار اختطف مرتين | بودكاست مربع",
      "src": "https://i.ytimg.com/vi/yNwQqqU2_tE/hqdefault.jpg",
      "url": "https://youtu.be/yNwQqqU2_tE",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+مربع"
    },
    {
      "title": "السيادة من الأمويين إلى السعوديين | بودكاست دواير",
      "src": "https://i.ytimg.com/vi/4uW2QMGl0SQ/hqdefault.jpg",
      "url": "https://youtu.be/4uW2QMGl0SQ",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+دواير"
    },
    {
      "title": "حياة السعوديين الصعبة قبل توحيد البلاد | بودكاست ذا قال",
      "src": "https://i.ytimg.com/vi/VV0Qualybqc/hqdefault.jpg",
      "url": "https://youtu.be/VV0Qualybqc",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+ذا+قال"
    },
    {
      "title": "ذكريات العسكرية وخفايا الصاعقة | بودكاست وضّاح",
      "src": "https://i.ytimg.com/vi/ak8haIU3Al4/hqdefault.jpg",
      "url": "https://youtu.be/ak8haIU3Al4",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+وضّاح"
    },
    {
      "title": "قصة: معاوية بن أبي سفيان | بودكاست دواير",
      "src": "https://i.ytimg.com/vi/7-YB9N4Tkuw/hqdefault.jpg",
      "url": "https://youtu.be/7-YB9N4Tkuw",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+دواير"
    },
    {
      "title": "قصص في عالم الجريمة مع معاذ عيد | بودكاست عدد",
      "src": "https://i.ytimg.com/vi/w8uWBRe8krs/hqdefault.jpg",
      "url": "https://youtu.be/w8uWBRe8krs",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+عدد"
    },
    {
      "title": "لماذا يُحارب السعودي في القطاع الخاص؟ ومن يحاسب على السعودة الوهمية ؟| مع أ.بدر العنزي | بودكاست نمو",
      "src": "https://i.ytimg.com/vi/cyvFRYX_FPo/hqdefault.jpg",
      "url": "https://youtu.be/cyvFRYX_FPo",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+نمو"
    },
    {
      "title": "بودكاست الأول | 9 | من يفتّش النساء في نقاط التفتيش؟",
      "src": "https://i.ytimg.com/vi/cbEnUFTEtHw/hqdefault.jpg",
      "url": "https://youtu.be/cbEnUFTEtHw",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+الأول"
    },
    {
      "title": "مجهولة أبوين | بودكاست فنجان",
      "src": "https://i.ytimg.com/vi/XH7Qv3siYNM/hqdefault.jpg",
      "url": "https://youtu.be/XH7Qv3siYNM",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+فنجان"
    },
    {
      "title": "ظاهرة شباب البومب وفيصل العيسى | بودكاست فنجان",
      "src": "https://i.ytimg.com/vi/GMyGyYBBM2M/hqdefault.jpg",
      "url": "https://youtu.be/GMyGyYBBM2M",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+فنجان"
    },
    {
      "title": "الثبات النفسي في غوانتانامو | بودكاست روايتهم 036 | فايز الكندري",
      "src": "https://i.ytimg.com/vi/rL4lrhoMRVA/hqdefault.jpg",
      "url": "https://youtu.be/rL4lrhoMRVA",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+روايتهم"
    },
    {
      "title": "بودكاست يصير خير | لعبة كمال الأجسام خساير وفيها محسوبيات - عبدالله الربيعة",
      "src": "https://i.ytimg.com/vi/HlH9NFARWds/hqdefault.jpg",
      "url": "https://youtu.be/HlH9NFARWds",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+يصير+خير"
    },
    {
      "title": "كيف تخسر دهون بالطريقة الصحيحة | بودكاست على البنش",
      "src": "https://i.ytimg.com/vi/g-Z8wuJUYBQ/hqdefault.jpg",
      "url": "https://youtu.be/g-Z8wuJUYBQ",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+على+البنش"
    },
    {
      "title": "كيف تلتزم بالنادي وتتمرن بسهولة | بودكاست فنجان",
      "src": "https://i.ytimg.com/vi/06ovyUh2iWU/hqdefault.jpg",
      "url": "https://youtu.be/06ovyUh2iWU",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+فنجان"
    },
    {
      "title": "آداب ومسائل الدعاء | بودكاست رفوف (67) مع حمد العتيق",
      "src": "https://i.ytimg.com/vi/F9IiYZoWBr0/hqdefault.jpg",
      "url": "https://youtu.be/F9IiYZoWBr0",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+رفوف"
    },
    {
      "title": "القضاء و القدر : بين الإيمان و العمل | د.عبدالرحمن الحرمي",
      "src": "https://i.ytimg.com/vi/am6jfmu7E_M/hqdefault.jpg",
      "url": "https://youtu.be/am6jfmu7E_M",
      "pageUrl": "https://www.youtube.com/results?search_query=محاضرة+مرئية"
    },
    {
      "title": "حسن الظن بالله… طريق الثبات | بودكاست ثبات (3) مع د. مطلق الجاسر #بودكاست #ثبات",
      "src": "https://i.ytimg.com/vi/fihKhSU9_rY/hqdefault.jpg",
      "url": "https://youtu.be/fihKhSU9_rY",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+ثبات"
    },
    {
      "title": "كيف تبني شركة ريادية بأقل المخاطر | بودكاست سوالف بزنس",
      "src": "https://i.ytimg.com/vi/aHU19xgbFM8/hqdefault.jpg",
      "url": "https://youtu.be/aHU19xgbFM8",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+سوالف+بزنس"
    },
    {
      "title": "دليل النجاح في ريادة الأعمال | بودكاست غلاف",
      "src": "https://i.ytimg.com/vi/6oox-CSglWw/hqdefault.jpg",
      "url": "https://youtu.be/6oox-CSglWw",
      "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+غلاف"
    },
    {
      "title": "كيف تكون تاجر وتنجح بمشروعك الصغير مع عبدالعزيز المطرودي بودكاست خبرة",
      "src": "https://i.ytimg.com/vi/yTiQd9Kgsck/hqdefault.jpg",
      "url": "https://youtu.be/yTiQd9Kgsck",
      "pageUrl": "https://www.youtube.com/results?search_query=%D9%83%D9%8A%D9%81%20%D8%AA%D9%83%D9%88%D9%86%20%D8%AA%D8%A7%D8%AC%D8%B1%20%D9%88%D8%AA%D9%86%D8%AC%D8%AD%20%D8%A8%D9%85%D8%B4%D8%B1%D9%88%D8%B9%D9%83%20%D8%A7%D9%84%D8%B5%D8%BA%D9%8A%D8%B1%20%D9%85%D8%B9%20%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B9%D8%B2%D9%8A%D8%B2%20%D8%A7%D9%84%D9%85%D8%B7%D8%B1%D9%88%D8%AF%D9%8A%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%AE%D8%A8%D8%B1%D8%A9"
    },
    {
      "title": "لماذا تفشل المشاريع الناشئة | بودكاست سوالف بزنس",
      "src": "https://i.ytimg.com/vi/PfTqG0vkVqo/hqdefault.jpg",
      "url": "https://youtu.be/PfTqG0vkVqo",
      "pageUrl": "https://www.youtube.com/results?search_query=%D9%84%D9%85%D8%A7%D8%B0%D8%A7%20%D8%AA%D9%81%D8%B4%D9%84%20%D8%A7%D9%84%D9%85%D8%B4%D8%A7%D8%B1%D9%8A%D8%B9%20%D8%A7%D9%84%D9%86%D8%A7%D8%B4%D8%A6%D8%A9%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%B3%D9%88%D8%A7%D9%84%D9%81%20%D8%A8%D8%B2%D9%86%D8%B3"
    },
    {
      "title": "كيف تحصل على وظيفة وتتطوّر مهنيًا | بودكاست فنجان",
      "src": "https://i.ytimg.com/vi/QPTwsoa47do/hqdefault.jpg",
      "url": "https://youtu.be/QPTwsoa47do",
      "pageUrl": "https://www.youtube.com/results?search_query=%D9%83%D9%8A%D9%81%20%D8%AA%D8%AD%D8%B5%D9%84%20%D8%B9%D9%84%D9%89%20%D9%88%D8%B8%D9%8A%D9%81%D8%A9%20%D9%88%D8%AA%D8%AA%D8%B7%D9%88%D9%91%D8%B1%20%D9%85%D9%87%D9%86%D9%8A%D9%8B%D8%A7%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D9%81%D9%86%D8%AC%D8%A7%D9%86"
    },
    {
      "title": "النصر يخسر نهائي آسيا 2 والهلال يؤجل حسم الدوري | بودكاست مرتدة",
      "src": "https://i.ytimg.com/vi/lVYybG7u8RQ/hqdefault.jpg",
      "url": "https://youtu.be/lVYybG7u8RQ",
      "pageUrl": "https://www.youtube.com/results?search_query=%D8%A7%D9%84%D9%86%D8%B5%D8%B1%20%D9%8A%D8%AE%D8%B3%D8%B1%20%D9%86%D9%87%D8%A7%D8%A6%D9%8A%20%D8%A2%D8%B3%D9%8A%D8%A7%202%20%D9%88%D8%A7%D9%84%D9%87%D9%84%D8%A7%D9%84%20%D9%8A%D8%A4%D8%AC%D9%84%20%D8%AD%D8%B3%D9%85%20%D8%A7%D9%84%D8%AF%D9%88%D8%B1%D9%8A%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D9%85%D8%B1%D8%AA%D8%AF%D8%A9"
    },
    {
      "title": "النصر يعود لصدارة دوري روشن | بودكاست شوط",
      "src": "https://i.ytimg.com/vi/ActJ1Hl_Wio/hqdefault.jpg",
      "url": "https://youtu.be/ActJ1Hl_Wio",
      "pageUrl": "https://www.youtube.com/results?search_query=%D8%A7%D9%84%D9%86%D8%B5%D8%B1%20%D9%8A%D8%B9%D9%88%D8%AF%20%D9%84%D8%B5%D8%AF%D8%A7%D8%B1%D8%A9%20%D8%AF%D9%88%D8%B1%D9%8A%20%D8%B1%D9%88%D8%B4%D9%86%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%B4%D9%88%D8%B7"
    },
    {
      "title": "استقطاب النجوم وعدالة المنافسة مع وزير الرياضة | بودكاست سقراط",
      "src": "https://i.ytimg.com/vi/6t6b15DCGT0/hqdefault.jpg",
      "url": "https://youtu.be/6t6b15DCGT0",
      "pageUrl": "https://www.youtube.com/results?search_query=%D8%A7%D8%B3%D8%AA%D9%82%D8%B7%D8%A7%D8%A8%20%D8%A7%D9%84%D9%86%D8%AC%D9%88%D9%85%20%D9%88%D8%B9%D8%AF%D8%A7%D9%84%D8%A9%20%D8%A7%D9%84%D9%85%D9%86%D8%A7%D9%81%D8%B3%D8%A9%20%D9%85%D8%B9%20%D9%88%D8%B2%D9%8A%D8%B1%20%D8%A7%D9%84%D8%B1%D9%8A%D8%A7%D8%B6%D8%A9%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%B3%D9%82%D8%B1%D8%A7%D8%B7"
    },
    {
      "title": "كيف يمكن فهمك للقرآن أن يغيّر حياتك بالكامل؟ | د. نايف بن نهار | بودكاست بدون ورق",
      "src": "https://i.ytimg.com/vi/Pfj4niPP0DY/hqdefault.jpg",
      "url": "https://youtu.be/Pfj4niPP0DY",
      "pageUrl": "https://www.youtube.com/results?search_query=%D9%83%D9%8A%D9%81%20%D9%8A%D9%85%D9%83%D9%86%20%D9%81%D9%87%D9%85%D9%83%20%D9%84%D9%84%D9%82%D8%B1%D8%A2%D9%86%20%D8%A3%D9%86%20%D9%8A%D8%BA%D9%8A%D9%91%D8%B1%20%D8%AD%D9%8A%D8%A7%D8%AA%D9%83%20%D8%A8%D8%A7%D9%84%D9%83%D8%A7%D9%85%D9%84%D8%9F%20%7C%20%D8%AF.%20%D9%86%D8%A7%D9%8A%D9%81%20%D8%A8%D9%86%20%D9%86%D9%87%D8%A7%D8%B1%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%A8%D8%AF%D9%88%D9%86%20%D9%88%D8%B1%D9%82"
    },
    {
      "title": "إعادة اكتشاف الصلاة | بودكاست فنجان",
      "src": "https://i.ytimg.com/vi/Zy_vOjKjcWA/hqdefault.jpg",
      "url": "https://youtu.be/Zy_vOjKjcWA",
      "pageUrl": "https://www.youtube.com/results?search_query=%D8%A5%D8%B9%D8%A7%D8%AF%D8%A9%20%D8%A7%D9%83%D8%AA%D8%B4%D8%A7%D9%81%20%D8%A7%D9%84%D8%B5%D9%84%D8%A7%D8%A9%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D9%81%D9%86%D8%AC%D8%A7%D9%86"
    },
    {
      "title": "حين يتحول الدعاء إلى يقين | بودكاست أروقة",
      "src": "https://i.ytimg.com/vi/UmoXguPAsAs/hqdefault.jpg",
      "url": "https://youtu.be/UmoXguPAsAs",
      "pageUrl": "https://www.youtube.com/results?search_query=%D8%AD%D9%8A%D9%86%20%D9%8A%D8%AA%D8%AD%D9%88%D9%84%20%D8%A7%D9%84%D8%AF%D8%B9%D8%A7%D8%A1%20%D8%A5%D9%84%D9%89%20%D9%8A%D9%82%D9%8A%D9%86%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%A3%D8%B1%D9%88%D9%82%D8%A9"
    },
    {
      "title": "لماذا الوظيفة هي أسرع طريق نحو الثراء؟ | من بودكاست غلاف",
      "src": "https://i.ytimg.com/vi/Brs2qH4Te0M/hqdefault.jpg",
      "url": "https://youtu.be/Brs2qH4Te0M",
      "pageUrl": "https://www.youtube.com/results?search_query=%D9%84%D9%85%D8%A7%D8%B0%D8%A7%20%D8%A7%D9%84%D9%88%D8%B8%D9%8A%D9%81%D8%A9%20%D9%87%D9%8A%20%D8%A3%D8%B3%D8%B1%D8%B9%20%D8%B7%D8%B1%D9%8A%D9%82%20%D9%86%D8%AD%D9%88%20%D8%A7%D9%84%D8%AB%D8%B1%D8%A7%D8%A1%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%BA%D9%84%D8%A7%D9%81"
    }
  ],
  "news": [
    {
      "title": "انطلاق أعمال المنتدى الحضري العالمي الـ13 في باكو",
      "lead": "ينطلق المنتدى الحضري العالمي الثالث عشر في باكو بمشاركة وفود دولية تناقش الإسكان والمدن المرنة وتطوير الخدمات الحضرية.",
      "body": [
        "يتقدم ملف الإسكان وجودة الحياة على جدول النقاشات، مع حضور واضح لقضايا النقل، وإدارة النمو السكاني، وتحسين الأحياء القائمة.",
        "تستعرض الوفود نماذج تساعد المدن على مواجهة الضغط العمراني من خلال التخطيط المبكر، والتمويل المستدام، ورفع كفاءة البنية التحتية.",
        "تمنح الجلسات مساحة لتبادل الخبرات بين الحكومات والبلديات والقطاع الخاص، بما يجعل الحلول العمرانية أقرب إلى التطبيق لا إلى العرض النظري فقط."
      ],
      "more": [
        "تظهر أهمية المنتدى في جمع الملفات التي تمس حياة السكان اليومية، من المسكن إلى الطريق إلى المساحة العامة، ضمن رؤية تجعل المدينة أكثر قابلية للعيش.",
        "ويبرز الحضور السعودي من خلال الاهتمام بتجارب التحول الحضري وجودة الحياة والمدن التي تربط التنمية بالخدمة اليومية للسكان."
      ],
      "tags": [
        "مدن",
        "إسكان",
        "تنمية"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?auto=format&fit=crop&w=1200&q=80"
    },
    {
      "title": "24 نقطة انخفاض للأسهم.. المؤشر عند 10.967",
      "lead": "أغلق مؤشر الأسهم السعودية على انخفاض بلغ 24 نقطة عند مستوى 10.967 نقطة، وسط تداولات وصلت قيمتها إلى 2.9 مليار ريال.",
      "body": [
        "شهدت الجلسة تباينًا بين القطاعات، إذ تحركت السيولة بين أسهم قيادية وأخرى متوسطة، بينما ظل اتجاه المؤشر العام محدودًا ضمن نطاق يومي ضيق.",
        "جاءت حركة السوق متأثرة بقراءة المستثمرين لنتائج الشركات، ومستويات السيولة، وتوقعات القطاعات الأكثر ارتباطًا بالنمو المحلي.",
        "توزعت التداولات بين عمليات جني أرباح وانتقاء فرص جديدة، ما جعل الإغلاق يعكس حذرًا أكثر من كونه تحولًا واسعًا في اتجاه السوق."
      ],
      "more": [
        "تبقى قيمة التداول وعدد الشركات الصاعدة والهابطة مؤشرات مهمة لفهم عمق الجلسة، لأن قراءة الرقم النهائي وحده لا تكشف كامل حركة السوق.",
        "ويمنح تتبع الأداء اليومي صورة أوضح عن شهية المخاطرة، وحجم النشاط داخل السوق، والقطاعات التي تقود التغير في المؤشر."
      ],
      "tags": [
        "اقتصاد",
        "أسهم",
        "تداول"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1611974789855-9c2a0a7236a3?auto=format&fit=crop&w=1200&q=80"
    },
    {
      "title": "لماذا غاب رونالدو عن تسلُّم ميداليته الآسيوية؟",
      "lead": "غياب كريستيانو رونالدو عن مراسم تسلم الميدالية الفضية بعد خسارة النصر نهائي دوري أبطال آسيا 2 أثار موجة واسعة من التفاعل الرياضي.",
      "body": [
        "جاء الغياب في لحظة حساسة بعد نهاية نهائي كبير، لذلك تجاوزت اللقطة حدود المباراة وتحولت إلى مادة نقاش بين الجماهير ووسائل الإعلام.",
        "يرتبط حضور لاعب بحجم رونالدو بالمشهد الكامل للبطولة، فكل تصرف بعد صافرة النهاية يقرأ بوصفه جزءًا من صورة النادي واللاعب.",
        "استعاد المتابعون تفاصيل المباراة والخسارة والضغط الجماهيري، بينما بقي السؤال عن الغياب حاضرًا بسبب رمزية المنصة والميدالية."
      ],
      "more": [
        "تكشف اللقطة أن المباريات النهائية لا تنتهي بالنتيجة فقط، بل بما يرافقها من مشاهد ومواقف وردود فعل تترك أثرًا في ذاكرة الجمهور.",
        "وسيحتاج النصر إلى تحويل التركيز سريعًا نحو الاستحقاقات التالية حتى لا يبقى أثر النهائي حاضرًا في كل نقاش رياضي لاحق."
      ],
      "tags": [
        "رياضة",
        "النصر",
        "آسيا"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1522778119026-d647f0596c20?auto=format&fit=crop&w=1200&q=80"
    },
    {
      "title": "مدارس أم مطاعم؟ التعليم: منحناها فرصاً كافية",
      "lead": "وزارة التعليم تؤكد منح مدارس أهلية فرصًا كافية قبل اتخاذ قرارات الإغلاق، وسط جدل يلامس سلامة الطلاب واستقرار الأسر وحقوق المستثمرين.",
      "body": [
        "تدور القضية حول الالتزام بالاشتراطات التعليمية والتنظيمية، ومدى قدرة المدارس على تصحيح الملاحظات قبل الوصول إلى قرار نهائي.",
        "تطالب الأسر بوضوح أكبر في إجراءات نقل الطلاب، بينما يربط المستثمرون بين الرقابة واستقرار العملية التعليمية خلال العام الدراسي.",
        "تضع الوزارة جودة البيئة المدرسية في مقدمة الاعتبارات، لأن استمرار المنشأة التعليمية يرتبط بقدرتها على توفير شروط مناسبة للطلاب."
      ],
      "more": [
        "تكشف القضية حاجة المدارس الأهلية إلى متابعة مستمرة لا تبدأ عند الأزمة، بل من خلال مراجعة دورية للمباني والسلامة والكادر والخدمات.",
        "ويظل انتقال الطالب إلى مدرسة بديلة جزءًا حساسًا من الملف، لأنه يمس الأسرة والجدول الدراسي والثقة في القرار التنظيمي."
      ],
      "tags": [
        "تعليم",
        "مدارس",
        "تنظيم"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1580582932707-520aed937b7b?auto=format&fit=crop&w=1200&q=80"
    },
    {
      "title": "سوسن البهيتي في بودكاست من.. إلى",
      "lead": "سوسن البهيتي تحضر في لقاء حواري يتناول تجربتها في الأوبرا ومسارها الفني وعلاقة الصوت بالهوية الثقافية السعودية.",
      "body": [
        "يفتح اللقاء مساحة للحديث عن التدريب، وبناء الحضور، والتعامل مع لون فني عالمي داخل بيئة ثقافية محلية تتسع تدريجيًا للتنوع.",
        "تقدم التجربة نموذجًا لفنانة سعودية اختارت صوتًا مختلفًا، ثم حولته إلى مسار مهني يحتاج صبرًا ومعرفة وانضباطًا.",
        "يعطي الحوار الطويل فرصة لفهم الطريق الذي يسبق الظهور على المسرح، من التمرين إلى اللغة إلى اختيار الأعمال وتقديمها للجمهور."
      ],
      "more": [
        "تبدو الحلقة مهمة لأنها لا تكتفي بتقديم اسم فني، بل تشرح كيف تتشكل التجربة حين تتقاطع الموهبة مع التعليم والفرص الثقافية الجديدة.",
        "ويمنح البودكاست هذا النوع من الحوارات وقتًا كافيًا لسرد التفاصيل التي لا تظهر في المقاطع القصيرة أو الأخبار السريعة."
      ],
      "tags": [
        "ثقافة",
        "فن",
        "بودكاست"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1478737270239-2f02b77fc618?auto=format&fit=crop&w=1200&q=80"
    },
    {
      "title": "شرق الطائف ينتظر توسعة طريق وادي جليل",
      "lead": "سكان شرق الطائف ينتظرون توسعة طريق وادي جليل مع تزايد الحاجة إلى مسار أكثر أمانًا وانسيابية يخدم الحركة اليومية.",
      "body": [
        "يرتبط الطريق بتنقل الطلاب والموظفين ووصول الخدمات، لذلك يتحول الازدحام أو ضيق المسار إلى مشكلة يومية لا تقف عند مستخدم واحد.",
        "توسعة الطريق تعني تقليل نقاط الاختناق، وتحسين السلامة، ورفع كفاءة الربط بين الأحياء والمرافق التي يعتمد عليها السكان.",
        "تتزايد أهمية المشروع عندما يصبح الطريق جزءًا من حركة مستمرة لا تستطيع انتظار حلول مؤقتة أو معالجة محدودة."
      ],
      "more": [
        "تطوير الطرق المحلية ينعكس مباشرة على جودة الحياة، لأن وقت الوصول والسلامة المرورية وسهولة الحركة عناصر يشعر بها السكان كل يوم.",
        "وتحتاج المشاريع المشابهة إلى تنسيق واضح بين الجهات الخدمية حتى تأتي المعالجة شاملة للطريق والإنارة والتقاطعات والمداخل."
      ],
      "tags": [
        "الطائف",
        "طرق",
        "خدمات"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1477959858617-67f85cf4f1df?auto=format&fit=crop&w=1200&q=80"
    },
    {
      "title": "خطوط المشاة المطموسة تتسبب في مخالفات بخميس مشيط",
      "lead": "خطوط مشاة مطموسة في خميس مشيط تربك السائقين والمشاة، وتفتح ملف وضوح العلامات المرورية داخل الطرق الحيوية.",
      "body": [
        "اختفاء العلامة الأرضية يجعل القرار المروري أقل وضوحًا، خصوصًا في المواقع التي تشهد عبورًا متكررًا وحركة مركبات مستمرة.",
        "تتضرر السلامة عندما تصبح المخالفة نتيجة التباس بصري لا نتيجة تجاهل متعمد، ما يزيد الحاجة إلى صيانة دورية للخطوط واللوحات.",
        "المواقع القريبة من المدارس والأسواق والمرافق العامة تحتاج علامات ظاهرة لأنها تجمع بين كثافة المشاة وسرعة حركة السيارات."
      ],
      "more": [
        "تبدأ السلامة المرورية من تفاصيل صغيرة لكنها حاسمة، مثل خط واضح، ولوحة في مكان مناسب، وإنارة تساعد على الرؤية في الليل.",
        "ومعالجة هذه الملاحظات تقلل الالتباس وتساعد السائق والمشاة على التصرف بثقة أكبر داخل الطريق."
      ],
      "tags": [
        "مرور",
        "سلامة",
        "خميس مشيط"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1519501025264-65ba15a82390?auto=format&fit=crop&w=1200&q=80"
    },
    {
      "title": "مستنقعات الصرف الصحي تثير مخاوف الأهالي في الحناكية",
      "lead": "مستنقعات صرف صحي في الحناكية تثير قلق الأهالي بسبب الروائح والمخاطر الصحية وتأثيرها المباشر على الأحياء القريبة.",
      "body": [
        "ترتبط المشكلة بالصحة العامة وجودة البيئة السكنية، إذ يمكن لتجمعات المياه الملوثة أن تتحول إلى مصدر إزعاج ومخاوف يومية للسكان.",
        "يطالب الأهالي بمعالجة سريعة تمنع تكرار التسرب أو الركود، وتضمن رقابة مستمرة على الشبكات والمواقع المتضررة.",
        "يتجاوز أثر المشكلة حدود الرائحة إلى الإحساس بالأمان داخل الحي، خصوصًا عندما تقع التجمعات قرب المنازل أو الطرق المستخدمة باستمرار."
      ],
      "more": [
        "تحتاج مثل هذه الحالات إلى تدخل يجمع بين المعالجة العاجلة والحل الدائم، حتى لا يعود الموقع إلى الوضع نفسه بعد فترة قصيرة.",
        "ويمنح وضوح الإجراءات السكان ثقة أكبر في متابعة الجهات المختصة وقدرتها على حماية البيئة اليومية للحي."
      ],
      "tags": [
        "بيئة",
        "صحة",
        "الحناكية"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1518837695005-2083093ee35b?auto=format&fit=crop&w=1200&q=80"
    },
    {
      "title": "طريق الطائف - بني سعد يحتاج مركزاً إسعافياً عاجلاً",
      "lead": "طريق الطائف ـ بني سعد يحتاج مركزًا إسعافيًا قريبًا يخدم الحالات الطارئة ويقلل زمن الاستجابة على طريق يشهد حركة مستمرة.",
      "body": [
        "يرتبط وجود مركز إسعافي بزمن الوصول إلى المصاب، وهو عامل حاسم في الحوادث والحالات المرضية المفاجئة على الطرق الطويلة.",
        "يستخدم الطريق سكان وزوار ومركبات خدمات، ما يجعل الحاجة إلى تغطية إسعافية ثابتة أكثر ارتباطًا بالسلامة العامة من كونها مطلبًا محليًا فقط.",
        "تعزيز نقاط الاستجابة يخفف الضغط على المراكز البعيدة، ويساعد الفرق الطبية على الوصول إلى الحالات قبل تفاقمها."
      ],
      "more": [
        "كل دقيقة في الطريق قد تصنع فرقًا عند وقوع حادث، لذلك تصبح مواقع الإسعاف جزءًا من تخطيط الطريق لا خدمة منفصلة عنه.",
        "وتكامل الإسعاف مع السلامة المرورية والإنارة واللوحات التحذيرية يمنح المسار حماية أفضل لمستخدميه."
      ],
      "tags": [
        "صحة",
        "طرق",
        "إسعاف"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1579684385127-1ef15d508118?auto=format&fit=crop&w=1200&q=80"
    },
    {
      "title": "أهالي أم القرى والوسيعة يطالبون بحديقة بديلة للملعب",
      "lead": "أهالي أم القرى والوسيعة يطالبون بحديقة بديلة بعد تخصيص مساحة كانت متنفسًا للحي، في مطلب يرتبط بالأسرة والطفل وجودة الحياة.",
      "body": [
        "تعتمد الأحياء السكنية على الحدائق بوصفها مساحة يومية للمشي واللعب والتواصل الاجتماعي، لا مجرد عنصر تجميلي داخل المخطط.",
        "يرى السكان أن وجود بديل مناسب يحفظ حق الأسر في متنفس قريب، خصوصًا في الأحياء التي تقل فيها المساحات العامة المفتوحة.",
        "تطرح المطالبة سؤالًا عن توازن التخطيط بين المرافق الرياضية والمساحات الخضراء التي تخدم شرائح أوسع من السكان."
      ],
      "more": [
        "الحديقة القريبة تمنح الحي حياة يومية أكثر نشاطًا، وتخفف الحاجة إلى قطع مسافات طويلة للوصول إلى متنفس آمن.",
        "ويصبح الحل أكثر قبولًا عندما يراعي احتياج الأطفال وكبار السن والعائلات في تصميم المكان وموقعه وخدماته."
      ],
      "tags": [
        "أحياء",
        "حدائق",
        "جودة الحياة"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1500534314209-a25ddb2bd429?auto=format&fit=crop&w=1200&q=80"
    },
    {
      "title": "مقترح بتحويل مكاتب التعليم المُلغاة إلى مدارس مسائية",
      "lead": "مقترح تحويل مكاتب تعليم ملغاة إلى مدارس مسائية يفتح باب الاستفادة من مبانٍ قائمة لتقليل الهدر وتوسيع الخيارات التعليمية.",
      "body": [
        "يقوم المقترح على استخدام أصول موجودة بدل تركها خارج الخدمة، مع إعادة تهيئتها بما يناسب احتياجات التعليم المسائي.",
        "يمكن لهذه الخطوة أن تخدم الطلاب الذين يحتاجون أوقاتًا مختلفة، وتخفف الضغط عن المدارس في بعض الأحياء أو المراحل.",
        "نجاح الفكرة يرتبط بجاهزية المباني، وتوفر الكادر، ووضوح آلية التشغيل، وضمان السلامة والخدمات الأساسية."
      ],
      "more": [
        "الاستفادة من المرافق التعليمية غير المستخدمة تعني تحويل المساحة من عبء إداري إلى فرصة خدمة، بشرط دراسة الطلب الفعلي قبل التنفيذ.",
        "ويمنح التعليم المسائي مرونة إضافية عندما يدار وفق معايير واضحة تحفظ جودة التعليم لا مجرد فتح باب جديد للحضور."
      ],
      "tags": [
        "تعليم",
        "مدارس مسائية",
        "استثمار مرافق"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1509062522246-3755977927d7?auto=format&fit=crop&w=1200&q=80"
    },
    {
      "title": "المنتدى السعودي للإعلام 2026 يستحضر الكنوز السعودية",
      "lead": "المنتدى السعودي للإعلام 2026 يستحضر الكنوز السعودية من خلال مسار يربط الإعلام بالهوية والسرد الثقافي والتحول في صناعة المحتوى.",
      "body": [
        "يعكس حضور الكنوز السعودية رغبة في تقديم المكان والإنسان والتاريخ ضمن لغة إعلامية حديثة تصل إلى جمهور واسع.",
        "يتقاطع المنتدى مع أسئلة الصناعة الإعلامية الجديدة، من المحتوى الرقمي إلى البودكاست إلى الصورة القصيرة والمنصات المتعددة.",
        "تمنح الفعاليات مساحة لعرض تجارب سعودية تشتغل على تحويل الذاكرة والمواقع والقصص إلى محتوى قابل للمشاهدة والاستماع والتداول."
      ],
      "more": [
        "تزداد قيمة هذا المسار عندما لا يكتفي بتقديم التراث بوصفه مادة قديمة، بل يربطه بأدوات إنتاج معاصرة تحافظ على المعنى وتوسع الوصول.",
        "ويؤكد المنتدى أن الإعلام السعودي يتجه إلى صناعة محتوى يرى الهوية مصدرًا للابتكار لا مجرد خلفية شكلية."
      ],
      "tags": [
        "إعلام",
        "هوية",
        "ثقافة"
      ],
      "sources": [],
      "src": "https://images.unsplash.com/photo-1505373877841-8d25f7d46678?auto=format&fit=crop&w=1200&q=80"
    }
  ],
  "articles": [
    {
      "title": "مقال: السرد الهادئ",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505418752290979900/9622e02c-3c95-4bf0-951c-ca89376ff5b0.png?ex=6a0a8df7&is=6a093c77&hm=8102a79b93db82942ebab7fdc0cf51706134af6ca7994258107e8bf6c0f836b5&=&format=webp&quality=lossless",
      "lead": "يناقش المقال السرد الهادئ بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> بطء الإيقاع عندما يتحول إلى قوة في الحوار، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> يبني الثقة بين المقدم والمستمع لأنه يعطي الفكرة وقتها قبل الانتقال إلى سؤال جديد، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> الحلقات التي تعتمد هذا الأسلوب تبدو أقرب إلى جلسة فهم لا إلى سباق عناوين، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> ينتهي المقال إلى أن الهدوء ليس ضعفًا في الإيقاع بل طريقة لضبط المعنى.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة السرد الهادئ من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الكتابة الصحفية",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505418940174700584/611c676c-b19b-41b7-8cd2-db61c64ef8ac.png?ex=6a0a8e24&is=6a093ca4&hm=857bac96b01cd2a9010adb909bccf0a060e350ab099683213c5e44c6da19d40a&=&format=webp&quality=lossless",
      "lead": "يناقش المقال الكتابة الصحفية بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> تحويل الفكرة الصوتية إلى نص واضح، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تجعل القارئ يعرف الأهم أولًا ثم ينتقل إلى التفاصيل الأقل إلحاحًا، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> تحتاج البودكاستات إلى هذه الكتابة عند إعداد الوصف والعناوين والمقتطفات، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> يبقى النص الجيد هو الذي يختصر دون أن يفرغ الحلقة من معناها.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الكتابة الصحفية من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الصورة والمعنى",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505419661708361872/cc38094c-360a-46a7-832c-85ae971b2250.png?ex=6a0a8ed0&is=6a093d50&hm=f92739d48d0c27989888e4c5ffcde2813139b669efb33ebb662ee1efc40a5dc9&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال الصورة والمعنى بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> علاقة الصورة بالعنوان والجو العام للحلقة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تساعد الصورة المناسبة على توقع النبرة قبل القراءة أو المشاهدة، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> اختيار صورة عشوائية يضعف الثقة حتى لو كان المحتوى قويًا، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> تنجح الصورة عندما تضيف وضوحًا لا عندما تسرق الانتباه.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الصورة والمعنى من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الهوية الصوتية",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505419634185343117/b4ebc59d-ff93-41fe-878a-d01129aa4899.png?ex=6a0a8eca&is=6a093d4a&hm=b04c9a0c4e4230e1dc0bc210dbe97de4a19ff8335b87804144d34685ce545d80&=&format=webp&quality=lossless&width=1032&height=1032",
      "lead": "يناقش المقال الهوية الصوتية بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> البصمة التي تجعل البرنامج معروفًا من نبرته، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تتكون من المقدمة والموسيقى وطريقة السؤال وحضور المقدم، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> الهوية لا تصنعها المؤثرات وحدها بل الاستمرارية في الأسلوب، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> كل برنامج يحتاج صوتًا خاصًا لا نسخة من برامج أخرى.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الهوية الصوتية من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: البودكاست النسائي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505419687343947837/e5d43c1d-076c-413f-9ce0-ac440d2537cc.png?ex=6a0a8ed6&is=6a093d56&hm=bb7a34f7622c846d3f2f2d10052800a0d752bff0291d2ff6e199e4240a3e90d7&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال البودكاست النسائي بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> حضور الأصوات النسائية في المشهد الصوتي، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> يفتح موضوعات وتجارب وأسئلة لا تظهر دائمًا في القوالب العامة، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> تزداد قيمته عندما يقدم الضيفة بصفتها صاحبة تجربة لا مجرد عنوان ناعم، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> يتسع المشهد السعودي كلما تعددت الأصوات وزوايا النظر.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة البودكاست النسائي من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الاختصار الذكي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505419719891751022/d354065b-cd15-42d6-be87-0fdf726629ca.png?ex=6a0a8ede&is=6a093d5e&hm=751f38558da7da1c3341d8ed59a1f38e765128bee602bdb5331534063112abf2&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال الاختصار الذكي بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> قول الكثير دون إطالة مرهقة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> يعتمد على اختيار الجملة الحاسمة وحذف ما لا يغير الفكرة، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> لا يعني الاختصار إلغاء التفاصيل المهمة بل ترتيبها، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> القارئ والمستمع يتذكران النص المكثف عندما يكون دقيقًا ومباشرًا.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الاختصار الذكي من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الفصل بين الخبر والرأي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505419747590672474/8677bf01-7b0e-4b33-b719-35fa06d45d17.png?ex=6a0a8ee5&is=6a093d65&hm=b6283895e2e44c95b9b9a8dbc9a2a3fe745916681a9587af1ef39dd588f68b1c&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال الفصل بين الخبر والرأي بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> حماية القارئ من خلط المعلومة بالتوجيه، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> يضع الواقعة في مكانها ويترك التحليل لمساحة معلنة وواضحة، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> هذا الفصل ضروري في المواد التي تمس أشخاصًا أو جهات أو قرارات عامة، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> تزداد ثقة الجمهور عندما يعرف أين تنتهي المعلومة وأين يبدأ الرأي.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الفصل بين الخبر والرأي من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: العنوان الافتتاحي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505419820403789934/16254d63-9663-4b7d-ad6d-6bb0fba099d5.png?ex=6a0a8ef6&is=6a093d76&hm=2c96e889776617553b5182b81d4e495f76b7e372f74d90d651a3e5ab1d76b599&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال العنوان الافتتاحي بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> أول وعد يقدمه النص للقارئ، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> يجب أن يحمل الفكرة الأساسية دون مبالغة أو تضليل، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> العنوان في البودكاست قد يصنع قرار المشاهدة قبل صورة الضيف، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> العنوان الجيد يفتح الباب ولا يحرق كل التفاصيل.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة العنوان الافتتاحي من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الفقرة الأولى",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505419877362565181/8a1f71b2-eff5-40ad-8ae1-3c55d8a0bf01.png?ex=6a0a8f04&is=6a093d84&hm=770d0bf86295d3e5e73fe414ef2a7a1c7632fef81ace2dedcc7f28962a09c519&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال الفقرة الأولى بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> المدخل الذي يحدد قيمة الاستمرار في القراءة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تحتاج إلى أهم زاوية بسرعة وبأقل عدد من الكلمات، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> عندما تطول البداية يضيع القارئ قبل الوصول إلى الفكرة، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> الفقرة الأولى الناجحة تمنح النص اتجاهًا واضحًا.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الفقرة الأولى من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: لغة الضيف",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505420532705660962/52436256-6a27-41ce-b4b4-fced5243842c.png?ex=6a0a8fa0&is=6a093e20&hm=2d23743814ff4ed2270c7d5d11cd20c974f3efc408bf0f0898967a39b79e4e83&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال لغة الضيف بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> حفظ صوت الضيف دون تهذيب زائد، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> اللغة تكشف خلفية الضيف وطريقة تفكيره وحدود تجربته، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> التدخل التحريري مطلوب فقط لتوضيح المعنى لا لمحو الشخصية، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> كلما بقيت اللغة قريبة من صاحبها صار الحوار أصدق.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة لغة الضيف من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الإصغاء الجيد",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505420663366615040/b12707a1-af00-4c72-8b4d-1a617d7b5ffd.png?ex=6a0a8fbf&is=6a093e3f&hm=2ceb6b92e1143f068562a8018903186ea59dbc21e97308d59bf60a6e5e60cbd3&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال الإصغاء الجيد بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> الاستماع بوصفه أداة تحرير لا مجاملة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> المقدم الذي يصغي يلتقط السؤال التالي من جواب الضيف نفسه، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> الإصغاء يمنع المقاطعة الفارغة ويجعل الحوار متدرجًا، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> الحلقة المتماسكة تبدأ من أذن تعرف متى تنتظر ومتى تسأل.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الإصغاء الجيد من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الإخراج",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505423093470855279/176e2f12-b604-42cb-9ab7-ac0793428704.png?ex=6a0a9202&is=6a094082&hm=0c3cdb399f1eb929917352a4aa34e1ec8a937ac36353150803353bcb9fb1cc4e&=&format=webp&quality=lossless",
      "lead": "يناقش المقال الإخراج بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> تنظيم الصوت والصورة داخل تجربة واحدة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> الإخراج يضبط الانتقال بين اللقطات والسكوت والموسيقى وحركة الكاميرا، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> كل قرار بصري أو صوتي يؤثر في فهم الحلقة لا في شكلها فقط، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> الإخراج الناجح يجعل التفاصيل تعمل من دون أن يشعر المشاهد بثقلها.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الإخراج من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: التوازن",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505423327274209402/c45c93a4-460c-43c6-9bd6-ecd144074a3a.png?ex=6a0a923a&is=6a0940ba&hm=a859e517096d53165ef85a5e345445afd85c94d3f42b64295a015004583ecf11&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال التوازن بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> منح الأطراف والأفكار مساحة عادلة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> يظهر التوازن في السؤال وفي ترتيب الحجج وفي اختيار الاقتباس، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> يفشل النص عندما يدفع القارئ إلى موقف جاهز قبل عرض المعطيات، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> التوازن لا يعني الحياد البارد بل الإنصاف في البناء.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة التوازن من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الترتيب",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505422830244728952/e56a6e63-1a61-4503-811b-6ff378160a12.png?ex=6a0a91c4&is=6a094044&hm=0cd38238bab237fcae8572328310b653f90ea8477f5021bf82f9e5876e5e5dc3&=&format=webp&quality=lossless",
      "lead": "يناقش المقال الترتيب بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> بناء الفكرة خطوة بعد خطوة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> يجعل الموضوع الطويل قابلًا للمتابعة دون قفزات مربكة، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> الترتيب يبدأ من العنوان ويمتد إلى الفقرات والصورة وزر المشاهدة، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> النص المرتب يترك أثرًا أوضح من نص مزدحم بالمعلومات.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الترتيب من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: التلقي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505422607783170159/1e97b25e-eacd-4612-bdad-8e9f0e125a9a.png?ex=6a0a918f&is=6a09400f&hm=0531a9a65e0e2637a1ca9ae9a9902d5e7228cc0e01c449e6ec91798a0f755fff&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال التلقي بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> طريقة وصول الحلقة إلى الجمهور، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> يتأثر التلقي بالمنصة والوقت والعنوان وطبيعة المقطع المتداول، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> الفكرة الواحدة قد تفهم بشكل مختلف إذا خرجت من سياقها الكامل، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> فهم التلقي يساعد صانع المحتوى على حماية المعنى.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة التلقي من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الذاكرة",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505423842909225081/08ca9224-b2a1-4f29-84ad-ff8bd8631543.png?ex=6a0a92b5&is=6a094135&hm=7d847ef03833ca0bb36c31632d6ba2322eccb4f3bc47d6821554f26a84c0be28&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال الذاكرة بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> ما يبقى من الحلقة بعد انتهائها، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> لا تحفظ الذاكرة كل التفاصيل بل تلتقط المشهد الأقوى والجملة الأوضح، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> لذلك يحتاج المحتوى إلى لحظات مركزة لا إلى تكرار طويل، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> الحلقة الناجحة تترك معنى يمكن استعادته لا مجرد ضجيج عابر.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الذاكرة من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الجلسة الحوارية",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505424113659809913/e59ab08a-e8c0-4db1-968f-9a1983e42030.png?ex=6a0a92f6&is=6a094176&hm=64d58cdc23374e7a37a6378b016dc8465cebb63897a31514e7d21ed0ea2bd756&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال الجلسة الحوارية بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> شكل اللقاء الذي يمنح الضيف مساحة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تقوم الجلسة على الثقة والإيقاع ووضوح المحاور، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> كل كرسي وإضاءة وصمت قصير يشارك في صناعة الشعور العام، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> الجلسة الجيدة تجعل المشاهد حاضرًا داخل الحوار لا متفرجًا بعيدًا.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الجلسة الحوارية من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: النص الكامل",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505422824821493870/70638b4d-6ac0-41ad-a3ab-2f628c421458.png?ex=6a0a91c2&is=6a094042&hm=98d9d011e89cac3cceb7c2b433e329b92eccf05c199c9dcdfcc096909fa9a01a&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال النص الكامل بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> قيمة قراءة الحلقة بعد سماعها، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> يساعد النص الكامل الباحث والقارئ على العودة إلى التفاصيل بدقة، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> تحويل الصوت إلى نص يحتاج مراجعة تحافظ على المعنى وتصحح الالتباس، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> النص الكامل يطيل عمر الحلقة ويجعلها قابلة للاقتباس.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة النص الكامل من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الحلقة المرئية",
      "src": "https://cdn.discordapp.com/attachments/1327007975604355153/1505424292375040081/98de1931-ce67-4246-810a-564b17c1564f.png?ex=6a0a9320&is=6a0941a0&hm=cc2bbc4f372d6e5976bfc10ebe0317d38addd2eed467466b8f6ae9016d6a87ef",
      "lead": "يناقش المقال الحلقة المرئية بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> انتقال البودكاست من الصوت إلى الصورة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تضيف الصورة لغة الجسد والمكان والملامح إلى التجربة، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> لكن الحضور البصري قد يربك الحلقة إذا غاب الانضباط الإخراجي، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> الحلقة المرئية تنجح عندما تخدم الصورة الحوار ولا تستبدله.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الحلقة المرئية من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الصياغة",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505424557140348948/0996858f-f94a-4fba-befd-87342b7e60c3.png?ex=6a0a935f&is=6a0941df&hm=3c279237d3fcbb7391e8e5b6ad1b9e38222b0915e8cf0ec2ad304df46d6afcc7&=&format=webp&quality=lossless",
      "lead": "يناقش المقال الصياغة بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> اختيار العبارة التي تحمل المعنى بوضوح، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تظهر الصياغة في العنوان والوصف والسؤال والاقتباس، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> الكلمة الزائدة قد تضعف الإيقاع كما أن الكلمة الناقصة قد تترك فراغًا، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> الصياغة القوية تجعل المادة مفهومة من القراءة الأولى.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الصياغة من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: العمق",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505424825060163654/04c57c6c-5c88-4705-9530-6b5150cd9be3.png?ex=6a0a939f&is=6a09421f&hm=f0d7e07b6fcd81172007a2d6742bdf89d3caf96f2871fd9738c357fa2f23054a&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال العمق بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> الانتقال من سطح الموضوع إلى أسبابه، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> لا يتحقق العمق بطول الحلقة فقط بل بترتيب الأسئلة ومتابعة الإجابات، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> الضيف العميق يحتاج مقدمًا يعرف متى يتركه يتوسع ومتى يعيده للمسار، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> العمق الجيد يضيف معرفة لا تعقيدًا مصطنعًا.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة العمق من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: البساطة",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505424909042450452/d53ee609-ec5b-4254-b4d7-ddd7f6848e0b.png?ex=6a0a93b3&is=6a094233&hm=bab396d69ac27d6cecd7a1e31383da969a638d1e4c0df353eae31100452f8d27&=&format=webp&quality=lossless",
      "lead": "يناقش المقال البساطة بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> تقديم الفكرة الصعبة بلغة مفهومة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تجعل البساطة المادة أقرب إلى القارئ دون التنازل عن دقتها، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> المحتوى المتخصص يفشل عندما يتحدث لنفسه فقط، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> البساطة الحقيقية تحتاج معرفة كافية لا اختصارًا كسولًا.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة البساطة من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الإيقاع",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505425051158184057/4cef0017-b762-460c-9f18-ccc8245230ab.png?ex=6a0a93d5&is=6a094255&hm=c8eb1c300aec07a9c3069f8573b1beba4246c998044a75fdd8937dacee315e0c&=&format=webp&quality=lossless",
      "lead": "يناقش المقال الإيقاع بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> حركة النص والحوار بين السرعة والهدوء، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> يحافظ الإيقاع على انتباه المتلقي ويمنع الملل في المواد الطويلة، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> يتأثر الإيقاع بالأسئلة والانتقالات والمقاطع الصامتة وطول الإجابة، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> الإيقاع المتزن يجعل الحلقة طويلة لكنها غير مرهقة.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الإيقاع من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الفخامة الهادئة",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505425411931246602/f743e9a0-ff9f-4ff4-9aa3-6da65dbecd82.png?ex=6a0a942b&is=6a0942ab&hm=693f51f1924218f2331b831d2b40df31f6db906d7d4e9a893ce0458097fd2cf8&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال الفخامة الهادئة بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> الجمال الذي لا يصرخ في التصميم والصوت، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تظهر الفخامة الهادئة في اللون والمساحة والاختيار القليل الدقيق، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> المبالغة البصرية قد تجعل الموقع يبدو مزدحمًا بدل أن يكون راقيًا، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> الفخامة هنا تعني الوضوح والثقة لا كثرة الزخرفة.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الفخامة الهادئة من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الرياض في البودكاست",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505425173401174136/55ce4682-c2c5-405f-b207-e393f0334730.png?ex=6a0a93f2&is=6a094272&hm=abfe4f22647fbb1380c443016ecf196823cea4a2166ac1205a11515f75846fc7&=&format=webp&quality=lossless&width=1032&height=576",
      "lead": "يناقش المقال الرياض في البودكاست بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> حضور المدينة بوصفها مسرحًا للحكاية، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تظهر الرياض في الحوارات من خلال التحول والعمل والذاكرة والمكان، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> ليست المدينة خلفية فقط بل مصدر قصص عن الناس والإيقاع والفرص، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> كلما حضرت الرياض بصدق صار السرد أكثر قربًا من الحياة اليومية.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الرياض في البودكاست من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: العلا في السرد السعودي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505425655351742584/846b9531-494a-4386-bb72-051dde1fc4b1.png?ex=6a0a9465&is=6a0942e5&hm=35d73980c7c2679bdcbf40e5137ed9c3749959c87718bc67cf04629c697a48b7&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال العلا في السرد السعودي بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> المكان التاريخي عندما يتحول إلى قصة معاصرة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تمنح العلا السرد السعودي طبقات من التراث والطبيعة والهوية البصرية، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> التعامل معها يحتاج لغة تحترم الذاكرة ولا تكتفي بالصورة الجميلة، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> تنجح الحكاية عندما تجمع المكان بالإنسان لا بالمشهد وحده.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة العلا في السرد السعودي من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الصوت النسائي السعودي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505425990430756914/9684e1b6-fb13-4e47-9fa8-449c7daa643d.png?ex=6a0a94b5&is=6a094335&hm=de72ecec952b17f9e94bfa08789af382dfc5e75b1f6eba5cd18b1f7174cfa1f7&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال الصوت النسائي السعودي بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> التجربة النسائية كما تظهر في الحوارات الطويلة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> يحمل الصوت النسائي أسئلة عن العمل والبيت والطموح والتمثيل الإعلامي، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> قيمة هذا الصوت في خصوصيته لا في فصله عن المشهد العام، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> كل مساحة عادلة للصوت النسائي توسع معنى البودكاست السعودي.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الصوت النسائي السعودي من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: لماذا تطول بعض الحلقات؟",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505426191744634980/db6542d9-d8ab-4e82-8406-97335a1ff344.png?ex=6a0a94e5&is=6a094365&hm=c2d7500d2d216c630606124651cb25525a93aeab6bd847407892a1c27f828f33&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال لماذا تطول بعض الحلقات؟ بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> سبب امتداد الحلقات في الحوار السعودي، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تطول الحلقة عندما يحتاج الموضوع إلى خلفية وسياق وتجربة شخصية، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> الإطالة تصبح مشكلة إذا غابت المحاور أو تكررت الفكرة نفسها، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> الطول مقبول عندما يمنح المستمع معرفة إضافية في كل انتقال.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة لماذا تطول بعض الحلقات؟ من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: الصورة حين تخدم المعنى",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505426472205287544/8ff32d30-8b58-4af7-a76d-f8af064003f0.png?ex=6a0a9528&is=6a0943a8&hm=69f06d343598ed18b463007e7ad62f8ca379f7b9a5eb1a96f3d7989df87e5e06&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال الصورة حين تخدم المعنى بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> دور الصورة في توجيه القراءة دون فرضها، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> الصورة المناسبة تختصر النبرة وتفتح باب التوقع الصحيح، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> لا تحتاج كل مادة إلى صورة صاخبة كي تبدو مهمة، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> تخدم الصورة المعنى عندما تجعل العنوان أوضح لا أكثر غموضًا.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة الصورة حين تخدم المعنى من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: من الحلقة إلى الأثر",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505427023894548641/ff3dfc8c-5faf-4dd8-8687-d5884f4a5377.png?ex=6a0a95ab&is=6a09442b&hm=ee01526adc2bdcb3e8f54302aad82c6f0f2cf79ef97f3ef1f116188518e8e88d&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال من الحلقة إلى الأثر بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> ما يحدث بعد نشر الحلقة، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> الأثر يظهر في النقاشات والاقتباسات وتغير طريقة فهم الموضوع، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> ليست كل مشاهدة أثرًا حقيقيًا إذا لم ينتقل المعنى إلى الجمهور، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> الحلقة المؤثرة تمنح المستمع سؤالًا جديدًا أو قرارًا أو زاوية نظر.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة من الحلقة إلى الأثر من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    },
    {
      "title": "مقال: لغة المقدم السعودي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505426324720980018/4ec23616-0dfc-47da-8cda-9e1985490971.png?ex=6a0a9505&is=6a094385&hm=2bee64dd1d63448d809b218fd2e444fd2c1b309a5bee447d6f0dd379204edf2d&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يناقش المقال لغة المقدم السعودي بوصفه قضية تحريرية تؤثر في قراءة البودكاست السعودي وفهم حضوره عند الجمهور.",
      "body": [
        "<strong>فكرة مباشرة:</strong> نبرة المقدم بين المحلية والاحتراف، ولذلك لا يكفي ذكر العنوان وحده من غير شرح يضعه في موضعه الصحيح.",
        "<strong>ما وراء العنوان:</strong> تحافظ اللغة السعودية على القرب عندما لا تتحول إلى استعراض، ويظهر هذا الأثر في طريقة صياغة السؤال، وترتيب الفقرة، واختيار الصورة المصاحبة.",
        "<strong>الخلفية:</strong> المقدم الناجح يوازن بين العفوية واحترام الضيف ودقة السؤال، لأن المادة الصوتية تتحول إلى تجربة أوضح عندما يلتقي النص مع الصوت في مسار واحد."
      ],
      "more": [
        "<strong>رأي المقال:</strong> هذه اللغة جزء من هوية البرنامج بقدر ما هي أداة للتواصل.",
        "<strong>مساحة القارئ:</strong> يستطيع القارئ أن يقيس جودة لغة المقدم السعودي من خلال وضوح الفكرة الأولى، وارتباط التفاصيل بها، وقدرة النص على دفعه لتكوين موقفه الخاص."
      ],
      "tags": [
        "مقال",
        "رأي",
        "بودكاست"
      ],
      "sources": []
    }
  ],
  "reports": [
    {
      "title": "تقرير: سلوك الاستماع السعودي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505437058959802429/a43d3a8c-166a-4172-a4b0-6da3e13cbaee.png?ex=6a0a9f04&is=6a094d84&hm=b42210f418efaf8b1f79826f8539e85ed8b39d54fc846b6ba24c2340cd5fd4cc&=&format=webp&quality=lossless",
      "lead": "يرصد التقرير سلوك الاستماع السعودي من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> يتغير الاستماع بين السيارة والمنزل والعمل، وتختلف معه مدة الحلقة وطريقة اختيارها، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> توضح الملاحظة أن الجمهور يبحث عن محتوى يرافق يومه لا يقطعه، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> النتيجة أن صانع البودكاست يحتاج فهم وقت المستمع قبل صياغة الحلقة.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: الحلقة الطويلة",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505437076152127583/cc236d93-4ef9-4de7-97db-0c567b247782.png?ex=6a0a9f08&is=6a094d88&hm=46df3a00c41d692a4cf52a6aa13958e83dad7a9714df045c833baadaf6cfe1eb&=&format=webp&quality=lossless",
      "lead": "يرصد التقرير الحلقة الطويلة من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> تمتد الحلقات الطويلة عندما يجتمع التاريخ الشخصي مع التحليل والسؤال المفتوح، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> المؤشر الأهم ليس عدد الدقائق بل قدرة كل محور على إضافة معنى جديد، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> القيمة تظهر عندما يشعر المستمع أن الوقت الطويل كان مبررًا.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: البودكاست النسائي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505437099904602203/81ec6f09-ead4-45bf-85ba-17cf89710745.png?ex=6a0a9f0e&is=6a094d8e&hm=153ec6dd24f7559d6f7ddefe6e6ca5a9c48c7ae8ca9ab703fa624a391b1d32b2&=&format=webp&quality=lossless",
      "lead": "يرصد التقرير البودكاست النسائي من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> يتوسع حضور النساء في برامج الحوار والسرد والتجارب المهنية، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> تكشف الحلقات عن موضوعات لا تظهر بوضوح في المواد القصيرة، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> النتيجة أن التنوع الصوتي أصبح عنصرًا أساسيًا في نمو المشهد.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: الهوية البصرية",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505437137565384805/56c2e39f-ac05-4dfd-adab-147af2c8ec11.png?ex=6a0a9f17&is=6a094d97&hm=30f44a8d7c30c04fb2ea2ef19d15139ca02e18a71f4ea0db067e42116e6c1afe&=&format=webp&quality=lossless",
      "lead": "يرصد التقرير الهوية البصرية من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> تعتمد البرامج على ألوان وشعارات وصور ضيوف تميزها داخل المنصات، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> يتحول الغلاف إلى أداة تعرّف سريعة عندما يتكرر بشكل منظم، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> كلما وضحت الهوية البصرية أصبح البرنامج أسهل في التذكر والبحث.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: الاستماع في السيارة",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505437260928254185/f5834b8f-e07f-41c6-ac2f-fab42f4aa569.png?ex=6a0a9f34&is=6a094db4&hm=248f05999aaa56efc4ec984dfe0ad90dc2871a63d1fc72b9da1ea1263ff362fe&=&format=webp&quality=lossless",
      "lead": "يرصد التقرير الاستماع في السيارة من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> السيارة مساحة استماع طبيعية في المدن السعودية بسبب التنقل اليومي، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> يناسبها المحتوى ذو الفقرات الواضحة والصوت المستقر والانتقالات القليلة، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> النتيجة أن الحلقة الجيدة للسيارة تراعي التركيز المتقطع للمستمع.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: الاستماع في المنزل",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505437282860273694/669113ea-fbe9-4b21-9861-5488fc46f81c.png?ex=6a0a9f39&is=6a094db9&hm=acdc27449535e0f32bcf82546572cca3e32e67e7c332e3dfb274e8b5aed624be&=&format=webp&quality=lossless",
      "lead": "يرصد التقرير الاستماع في المنزل من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> المنزل يمنح المستمع وقتًا أهدأ للحلقات الطويلة والموضوعات العميقة، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> يزداد حضور البودكاست أثناء الأعمال اليومية أو الجلسات الفردية، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> هذا النوع من الاستماع يرفع قيمة الحلقات التي تبني سياقها ببطء.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: الاستماع في العمل",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505437309477060760/88cc8cd0-6b2b-4506-a087-3d1ca43acd59.png?ex=6a0a9f40&is=6a094dc0&hm=cda4e26437346e02d59f21996deb585992eaaa704a79de43b95e0a5f154216de&=&format=webp&quality=lossless",
      "lead": "يرصد التقرير الاستماع في العمل من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> الاستماع أثناء العمل يحتاج محتوى لا يطلب متابعة بصرية دائمة، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> تنجح الحلقات المهنية والقصصية عندما تقدم محاور واضحة وسهلة العودة، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> النتيجة أن وضوح التقسيم يساعد المستمع الذي ينشغل ثم يعود.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: خريطة المنصات",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505437918523560036/88cc8cd0-6b2b-4506-a087-3d1ca43acd59.png?ex=6a0a9fd1&is=6a094e51&hm=0e65988c4452b093f5365312b1c60034d2a597d188dc191ea3baa0996312b79c&=&format=webp&quality=lossless&width=928&height=507",
      "lead": "يرصد التقرير خريطة المنصات من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> يتوزع البودكاست بين يوتيوب وسبوتيفاي وآبل بودكاست ومنصات التواصل، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> كل منصة تفرض أسلوب عرض مختلفًا في الصورة والوصف والمقطع القصير، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> البرنامج القوي لا ينسخ نفسه في كل منصة بل يكيّف حضوره معها.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: التوزيع الرقمي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505437918225760266/84cbbe05-8ebb-40b2-b0fb-766f6fc0014b.png?ex=6a0a9fd1&is=6a094e51&hm=b25cf41c96b60d460e3c49619f46fa6297066461103aa8a6436d3d68b32684dc&=&format=webp&quality=lossless&width=928&height=507",
      "lead": "يرصد التقرير التوزيع الرقمي من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> التوزيع يحول الحلقة من ملف منشور إلى شبكة وصول كاملة، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> تؤثر العناوين والكلمات المفتاحية ومواعيد النشر في انتشار المادة، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> النتيجة أن نجاح الحلقة يبدأ بعد الإنتاج ولا يتوقف عند التسجيل.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: الإخراج الفني",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505438519370186823/d1e435a2-32e2-4fa8-88c1-2feb2c7c6f6b.png?ex=6a0aa060&is=6a094ee0&hm=0b0eeec9078bdbe98beb61f56abdf08d3b2b660c3cdd9524192046b5bb2211e5&=&format=webp&quality=lossless",
      "lead": "يرصد التقرير الإخراج الفني من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> الإخراج ينظم الصوت والصورة والإضاءة وحركة الكاميرا داخل الحلقة، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> تتضح جودة الإخراج عندما ينسى المشاهد التقنية ويركز في الحوار، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> النتيجة أن الحرفية الهادئة ترفع قيمة البرنامج دون أن تطغى عليه.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: إدارة الحوار",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505438527096098856/690f5651-2a36-41c4-8025-b22225a5d50b.png?ex=6a0aa062&is=6a094ee2&hm=a0ed774115ea7091251123f7b41e57f58a77b4841687c01e9405391485e71547&=&format=webp&quality=lossless",
      "lead": "يرصد التقرير إدارة الحوار من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> إدارة الحوار تضبط العلاقة بين السؤال والجواب والانتقال إلى محور جديد، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> تظهر مهارة المقدم عند متابعة إجابة الضيف لا الاكتفاء بقائمة أسئلة جاهزة، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> الحوار المنظم ينتج مادة قابلة للفهم والاقتباس والمشاركة.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: المؤثرات الصوتية",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505439315797475428/4373e2f4-edc5-491a-9216-622c0227fb11.png?ex=6a0aa11e&is=6a094f9e&hm=0793a806c06c795c162c4a0d59694028901f35136278a174f97d5f60c602d01a&=&format=webp&quality=lossless",
      "lead": "يرصد التقرير المؤثرات الصوتية من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> المؤثرات تضيف طبقة شعورية لكنها قد تضعف الحلقة إذا حضرت بلا سبب، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> الاستخدام الدقيق يوضح الانتقال أو يهيئ المستمع للحكاية، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> النتيجة أن المؤثر الجيد يعمل في الخلفية ولا يصبح موضوعًا مستقلًا.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تقرير: نبرة المقدم",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505439916081811466/a533404e-ee09-45d5-9311-32ee85dc7655.png?ex=6a0aa1ad&is=6a09502d&hm=8bf541b8baf170cbbdd85e2da2962a4216a7f7a87645ba32546fd27acba8e95c&=&format=webp&quality=lossless",
      "lead": "يرصد التقرير نبرة المقدم من زاوية عملية تربط بين ما يظهر للجمهور وما يحدث داخل صناعة البودكاست السعودي.",
      "body": [
        "<strong>زاوية المشهد:</strong> النبرة تحدد علاقة المستمع بالمقدم قبل مضمون السؤال، وهذا يجعل الموضوع مرتبطًا بسلوك الجمهور وبطريقة إنتاج الحلقة في الوقت نفسه.",
        "<strong>المؤشرات:</strong> النبرة الهادئة تمنح الثقة بينما النبرة الحادة قد تدفع الضيف إلى الدفاع، مع ملاحظة أثر العنوان والصورة والمنصة في تحديد مسار الوصول إلى المستمع.",
        "<strong>مسار الموضوع:</strong> يبدأ الأثر من قرار الإنتاج، ثم ينتقل إلى النشر، ثم يظهر في التفاعل والمشاهدة والعودة إلى الحلقة بعد نشرها."
      ],
      "more": [
        "<strong>قراءة النتائج:</strong> المقدم الناجح يجعل صوته طريقًا للمعنى لا حاجزًا بين الضيف والجمهور.",
        "<strong>ما يبقى بعد التقرير:</strong> يترك الموضوع سؤالًا مفتوحًا حول الطريقة التي يمكن بها تحسين التجربة من غير أن تفقد الحلقة شخصيتها أو جمهورها الأساسي."
      ],
      "tags": [
        "تقرير",
        "رصد",
        "تحليل"
      ],
      "sources": []
    }
  ],
  "investigations": [
    {
      "title": "تحقيق: الحلقة الطويلة",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505433561765777438/c56c2603-7f6e-4946-81e2-ae08b026ca26.png?ex=6a0a9bc2&is=6a094a42&hm=539505838232be9a7e1164cc15d1d24e918f26fcb626117152b66eeff6126c3c&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يفتح التحقيق ملف الحلقة الطويلة من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> لماذا تقبل بعض الحلقات الساعات الطويلة بينما تفقد أخرى جمهورها مبكرًا، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> يتضح أن طول الحلقة يحتاج بنية محاور لا مجرد تدفق حر للكلام، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع الحلقة الطويلة مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> أقوى الحلقات الطويلة هي التي تفتح سؤالًا ثم تعود إليه بإجابة أوضح.",
        "<strong>قراءة المحرر:</strong> معالجة الحلقة الطويلة تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق: فخامة الشكل",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505433765327933521/9d6cfba8-9fff-41e8-9976-fd57ccb8d9e5.png?ex=6a0a9bf3&is=6a094a73&hm=75464220c48f56aff3368e06b7fe09204fdf91e15c9f3cdcf3b4cd3cdd7fb1d2&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يفتح التحقيق ملف فخامة الشكل من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> هل تخدم الفخامة البصرية المحتوى أم تتحول إلى ستار يخفي ضعف الفكرة، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> تظهر الفخامة في الاتساق والهدوء قبل أن تظهر في الألوان والخلفيات، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع فخامة الشكل مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> الشكل المقنع هو الذي يجعل القارئ يثق بالمادة دون أن ينشغل عن مضمونها.",
        "<strong>قراءة المحرر:</strong> معالجة فخامة الشكل تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق: العودة إلى الحلقات الكاملة",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505433795971645480/48040ce9-8722-4002-9f3c-7de782c50d93.png?ex=6a0a9bfa&is=6a094a7a&hm=ce1441475cccc177cd074d5234c635d4333e60a01774d205c21ee5da741a8772&=&format=webp&quality=lossless",
      "lead": "يفتح التحقيق ملف العودة إلى الحلقات الكاملة من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> لماذا يعود بعض الجمهور إلى الحلقة كاملة بعد مشاهدة مقطع قصير، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> المقطع يلفت الانتباه لكنه لا يشرح الخلفية ولا يحفظ تسلسل الفكرة، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع العودة إلى الحلقات الكاملة مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> قيمة الحلقة الكاملة تظهر عندما يحتاج المستمع إلى السياق لا إلى الجملة المتداولة فقط.",
        "<strong>قراءة المحرر:</strong> معالجة العودة إلى الحلقات الكاملة تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق: البودكاست النسائي",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505434076960784425/5101b3f3-f39e-4078-afe6-7efa5e0cc508.png?ex=6a0a9c3d&is=6a094abd&hm=c732608aec3d3fb237c2319902cc5298908982ae2f8b9ffe0eb500e762289565&=&format=webp&quality=lossless&width=1032&height=563",
      "lead": "يفتح التحقيق ملف البودكاست النسائي من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> ما الذي يعيق حضور الأصوات النسائية وما الذي يمنحها مساحة أوسع، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> تتداخل الجرأة التحريرية مع اختيار الضيفات وطبيعة الموضوعات المطروحة، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع البودكاست النسائي مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> الحضور النسائي يتقدم عندما يعامل بوصفه جزءًا من المشهد لا فقرة موسمية.",
        "<strong>قراءة المحرر:</strong> معالجة البودكاست النسائي تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق : الثقة",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505434109009330217/02d448df-c8f7-4a82-a216-de17d37a3bad.png?ex=6a0a9c45&is=6a094ac5&hm=e081c644725aaac654a1a4477c0b5017def97dd8f500f919cd6012b3262f9a1e&=&format=webp&quality=lossless",
      "lead": "يفتح التحقيق ملف الثقة من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> كيف يقرر المستمع أن برنامجًا ما يستحق وقته وثقته، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> تنشأ الثقة من وضوح المصادر ودقة العنوان واحترام الضيف والجمهور، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع الثقة مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> أي مبالغة في الوعد أو اقتطاع مضلل تضعف هذه العلاقة سريعًا.",
        "<strong>قراءة المحرر:</strong> معالجة الثقة تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق: السياق",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505434125857853481/f0c926d0-9d6e-403c-ac45-506272848582.png?ex=6a0a9c49&is=6a094ac9&hm=75fd0e1ddb62299826b3aa7e97d64e74aa0c364ef9a066bfe3d3766b17f8c255&=&format=webp&quality=lossless",
      "lead": "يفتح التحقيق ملف السياق من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> لماذا تفشل بعض المقاطع عندما تنتزع من سياق الحلقة، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> السياق يمنح الجملة معناها ويشرح سبب السؤال وطبيعة اللحظة، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع السياق مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> غياب السياق يجعل الجمهور يحاكم جزءًا صغيرًا كأنه القصة كاملة.",
        "<strong>قراءة المحرر:</strong> معالجة السياق تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق: التمهيد",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505434141745746020/3d26c70e-8079-4ebe-b3bc-7e41306cd8b3.png?ex=6a0a9c4d&is=6a094acd&hm=3f79aec174bb50a1d8ee99ec63473cba8059e2c06f1f62250014708e2ea5a156&=&format=webp&quality=lossless",
      "lead": "يفتح التحقيق ملف التمهيد من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> ما الدور الذي تلعبه الدقائق الأولى في نجاح الحلقة، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> التمهيد يعرّف الجمهور على سبب اللقاء والمسار المتوقع دون إطالة، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع التمهيد مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> كل تمهيد جيد يقلل الارتباك ويدخل المستمع إلى الموضوع بثقة.",
        "<strong>قراءة المحرر:</strong> معالجة التمهيد تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق: النبرة",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505434155016650842/b8508c6e-2662-430a-bac5-8958dc3b5329.png?ex=6a0a9c50&is=6a094ad0&hm=8a779da65405137e12b394624bce4170bdc0ffc7a4c3f232bb997219881aea6e&=&format=webp&quality=lossless",
      "lead": "يفتح التحقيق ملف النبرة من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> كيف تغير نبرة المقدم معنى السؤال حتى لو بقيت الكلمات نفسها، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> النبرة قد تجعل السؤال فضوليًا أو هجوميًا أو محايدًا، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع النبرة مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> المقدم المحترف يضبط نبرته كي لا يفرض جوابًا قبل سماعه.",
        "<strong>قراءة المحرر:</strong> معالجة النبرة تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق: المونتاج",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505434178005499964/fa20b5e8-5bdb-4ce7-9636-d3209e9d37fc.png?ex=6a0a9c55&is=6a094ad5&hm=9cacc004f6022b4455f41c616b58f4ad7ea504a55fa5be707d899e1a71c7d323&=&format=webp&quality=lossless",
      "lead": "يفتح التحقيق ملف المونتاج من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> هل يحسن المونتاج الحلقة أم يغير حقيقتها، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> المونتاج الجيد يحذف التكرار والفراغ ويحفظ سياق الإجابة، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع المونتاج مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> الخطر يبدأ عندما يتحول القص إلى صناعة معنى لم يقله الضيف.",
        "<strong>قراءة المحرر:</strong> معالجة المونتاج تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق: التوزيع",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505434194157764668/7480316a-aa36-4954-8170-0f836dcc5999.png?ex=6a0a9c59&is=6a094ad9&hm=8e551d161f5506b2529375dc6d2f9d1a060e736c9c09931f7ee041629eee136c&=&format=webp&quality=lossless",
      "lead": "يفتح التحقيق ملف التوزيع من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> لماذا لا تصل بعض الحلقات الجيدة إلى جمهورها المتوقع، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> التوزيع يحتاج عنوانًا واضحًا وصورة مناسبة ومقاطع قصيرة تقود إلى الحلقة كاملة، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع التوزيع مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> المحتوى القوي يخسر أثره إذا نشر بلا خطة وصول مفهومة.",
        "<strong>قراءة المحرر:</strong> معالجة التوزيع تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق: الجمهور",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505434208372523148/c4249916-1813-4645-800d-d6faaf4e0e79.png?ex=6a0a9c5c&is=6a094adc&hm=17e22fddcb03db65693d12a02a414b35a31c418e1245842d3fb2422dce188070&=&format=webp&quality=lossless",
      "lead": "يفتح التحقيق ملف الجمهور من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> من هو جمهور البودكاست السعودي وكيف يختار ما يسمعه، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> يتحرك الجمهور بين المعرفة والترفيه والتجربة الشخصية والاهتمام المحلي، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع الجمهور مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> فهم الجمهور لا يعني ملاحقته بكل ما يريد بل تقديم ما يستحق وقته.",
        "<strong>قراءة المحرر:</strong> معالجة الجمهور تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق: الحضور",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505434220783472872/8d9582db-9ba1-4b78-bedd-a3cb495e7fa8.png?ex=6a0a9c5f&is=6a094adf&hm=e96ad999bd20d5db01796847f764a1b7c10d30d48fcd8d4c33e88c02f02199c2&=&format=webp&quality=lossless",
      "lead": "يفتح التحقيق ملف الحضور من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> ما الذي يجعل الضيف حاضرًا في الحلقة لا مجرد اسم على العنوان، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> الحضور يصنعه الصدق والقدرة على السرد ووضوح التجربة، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع الحضور مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> الضيف القوي يترك أثرًا عندما يجد سؤالًا يسمح له بفتح ذاكرته لا تكرار سيرته.",
        "<strong>قراءة المحرر:</strong> معالجة الحضور تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    },
    {
      "title": "تحقيق: المقدم",
      "src": "https://media.discordapp.net/attachments/1327007975604355153/1505434248423669863/ab00d53e-0910-4439-a64b-f37e47e52481.png?ex=6a0a9c66&is=6a094ae6&hm=bc027ec32cc8b4a83ca264b0a465c8a535c70978386e51ca384a3cb488ca8f7d&=&format=webp&quality=lossless",
      "lead": "يفتح التحقيق ملف المقدم من خلال سؤال رئيسي يبحث عن السبب والأثر والنتيجة داخل تجربة البودكاست السعودي.",
      "body": [
        "<strong>السؤال الرئيسي:</strong> ما الذي يميز المقدم القادر على قيادة حوار طويل، وهو سؤال لا تكفيه إجابة سريعة لأنه يرتبط بطريقة صناعة الحلقة واستقبالها.",
        "<strong>الشواهد:</strong> المقدم يجمع بين التحضير والمرونة ومعرفة متى يتدخل ومتى يصمت، كما يظهر في العنوان، والتمهيد، وترتيب الحوار، وطريقة تحويل المقطع إلى مادة قابلة للتداول.",
        "<strong>زوايا مرتبطة:</strong> يتقاطع المقدم مع اختيار الضيف، ودرجة التحضير، وحجم التدخل في المونتاج، ومكان نشر الحلقة بعد اكتمالها."
      ],
      "more": [
        "<strong>ما وصل إليه التحقيق:</strong> النجاح الحقيقي يظهر عندما يخرج الضيف أفضل مما كان سيقوله وحده.",
        "<strong>قراءة المحرر:</strong> معالجة المقدم تحتاج اختصارًا في العبارة وبعدًا عن الحشو، لأن قوة التحقيق تظهر عندما يجيب عن السؤال الذي فتحه من غير أن يبتعد عن محوره."
      ],
      "tags": [
        "تحقيق",
        "أسئلة",
        "تحليل"
      ],
      "sources": []
    }
  ]
};
  </script>

  <header class="sticky top-0 z-[100] glass border-b border-black/5">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 py-4 flex items-center justify-between gap-4">
      <button id="logoBtn" type="button" class="flex items-center gap-3 min-w-0 text-right" aria-label="العودة إلى الصفحة الرئيسية">
        <img id="siteLogo" src="" alt="مُلهم" class="w-14 h-14 rounded-2xl object-cover shadow-lg shrink-0 bg-white p-1">
        <div class="min-w-0">
          <h1 class="display-font text-2xl sm:text-3xl font-black text-[var(--brown)] leading-none truncate">مُلهم</h1>
          <p class="text-sm text-[var(--olive)] mt-1 truncate">الصحيفة الإلكترونية للبودكاست السعودي</p>
        </div>
      </button>
      <button id="devBtn" class="px-4 py-3 rounded-2xl bg-white border border-black/10 shadow-sm hover:shadow-md soft font-bold text-[var(--brown)] flex items-center justify-center" type="button" aria-label="المطورون">
        <span class="w-8 h-8 rounded-full bg-[var(--brown)]/10 text-[var(--brown)] flex items-center justify-center">⋯</span>
      </button>
    </div>
    <div class="max-w-7xl mx-auto px-4 sm:px-6 pb-4">
      <nav class="flex items-center gap-2 overflow-x-auto no-scrollbar whitespace-nowrap pb-1">
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[var(--brown)]/10 text-[var(--brown)] font-bold min-w-max" data-page="home" type="button">الرئيسية</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[var(--brown)]/10 text-[var(--brown)] font-bold min-w-max" data-page="programs" type="button">البرامج</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[var(--brown)]/10 text-[var(--brown)] font-bold min-w-max" data-page="articles" type="button">مقال</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[var(--brown)]/10 text-[var(--brown)] font-bold min-w-max" data-page="investigations" type="button">تحقيق</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[var(--brown)]/10 text-[var(--brown)] font-bold min-w-max" data-page="reports" type="button">تقارير</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[var(--brown)]/10 text-[var(--brown)] font-bold min-w-max" data-page="news" type="button">أخبار</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[var(--brown)]/10 text-[var(--brown)] font-bold min-w-max" data-page="interactive" type="button">تفاعلي</button>
        <button class="nav-btn soft px-4 py-2 rounded-xl bg-white border border-[var(--brown)]/10 text-[var(--brown)] font-bold min-w-max" data-page="references" type="button">المراجع</button>
      </nav>
    </div>
  </header>

  <main class="relative z-10">
    <section id="page-home" class="page active">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-8 md:py-10">
        <div class="rounded-[2rem] overflow-hidden border border-white/60 shadow-[0_24px_70px_rgba(122,90,46,.10)] bg-gradient-to-b from-[#e7ded2] to-[#f4f1ea]">
          <div class="relative px-5 sm:px-10 py-14 md:py-24 text-center">
            <div class="absolute inset-0 opacity-20 pointer-events-none">
              <div class="absolute w-[620px] h-[620px] bg-[#7a856f] rounded-full blur-3xl top-[-220px] right-[-200px] animate-pulse"></div>
              <div class="absolute w-[520px] h-[520px] bg-[#7a5a2e] rounded-full blur-3xl bottom-[-200px] left-[-120px] animate-pulse"></div>
            </div>
            <div class="relative z-10 max-w-5xl mx-auto">
              <div class="hero-badge display-font">مُلهم.. نبض البودكاست السعودي</div>
              <h2 class="display-font text-5xl sm:text-7xl md:text-8xl font-black text-[var(--brown)] leading-tight mb-6">صفحة سعودية تجمع الخبر والسرد والصوت</h2>
              <p class="text-xl md:text-2xl leading-loose text-[var(--olive)] max-w-4xl mx-auto">صحيفة إلكترونية مصممة حول المشهد السعودي فقط، وفيها برامج ومقالات وتحقيقات وتقارير وأخبار وتفاعل، بلغة تحريرية رسمية ومتماسكة.</p>
              <div class="mt-10 flex flex-wrap justify-center gap-4">
                <button type="button" class="bg-[var(--brown)] text-white px-7 py-4 rounded-2xl text-lg font-bold shadow-xl hover:scale-[1.03] soft" data-page-jump="programs">اذهب إلى البرامج</button>
              </div>
            </div>
          </div>
        </div>
        <div class="mt-8 flex justify-center">
          <div class="card rounded-[2rem] overflow-hidden relative text-right w-full max-w-5xl">
            <div class="hero-badge display-font">مُلهم</div>
            <div class="image-frame rounded-none h-52 sm:h-64 md:h-80">
              <img id="homeFlag" src="" alt="بنر فكرة موقع مُلهم">
            </div>
            <div class="p-6">
              <h3 class="display-font text-2xl font-black text-[var(--brown)]">فكرة مُلهم</h3>
              <p class="mt-3 leading-8">مُلهم موقع سعودي يجمع حلقات البودكاست المختارة مع المقالات والتقارير والأخبار في واجهة واحدة، ليقدّم الفكرة والصورة والصوت بأسلوب منظم يساعد الزائر على الوصول للمحتوى المناسب بسرعة.</p>
            </div>
          </div>
        </div>
        <div class="mt-8 ticker-shell bg-white shadow-sm border border-black/5">
          <div class="ticker-track py-3">
            <div class="ticker-chip">مُلهم.. نبض البودكاست السعودي</div>
            <div class="ticker-chip">المشهد السعودي يُكتب بالصوت والصورة</div>
            <div class="ticker-chip">من الرياض إلى العلا.. قصة سعودية واحدة</div>
            <div class="ticker-chip">كل باب هنا يحكي حكاية من داخل المملكة</div>
            <div class="ticker-chip">مُلهم.. حيث يبدأ الإلهام السعودي</div>
            <div class="ticker-chip">مُلهم.. نبض البودكاست السعودي</div>
            <div class="ticker-chip">المشهد السعودي يُكتب بالصوت والصورة</div>
            <div class="ticker-chip">من الرياض إلى العلا.. قصة سعودية واحدة</div>
            <div class="ticker-chip">كل باب هنا يحكي حكاية من داخل المملكة</div>
            <div class="ticker-chip">مُلهم.. حيث يبدأ الإلهام السعودي</div>
          </div>
        </div>
        <div class="grid lg:grid-cols-3 gap-6 mt-8">
          <div class="card rounded-3xl p-6 card-hover soft">
            <div class="w-14 h-14 rounded-2xl bg-[var(--brown)]/10 text-[var(--brown)] flex items-center justify-center text-2xl mb-4">📰</div>
            <h3 class="display-font text-2xl font-black text-[var(--brown)] mb-3">صحيفة مكتملة العناصر</h3>
            <p class="text-lg leading-8">أخبار وتقارير ومقالات وتحقيقات وبرامج ومراجع داخل تصميم واحد واضح ومترابط.</p>
          </div>
          <div class="card rounded-3xl p-6 card-hover soft">
            <div class="w-14 h-14 rounded-2xl bg-[var(--olive)]/10 text-[var(--olive)] flex items-center justify-center text-2xl mb-4">🎧</div>
            <h3 class="display-font text-2xl font-black text-[var(--brown)] mb-3">برامج سعودية مفصلة</h3>
            <p class="text-lg leading-8">أول عنصر هنا للحلقة الخاصة الطويلة، ثم برامج أخرى تعكس التحول الثقافي والإعلامي في السعودية.</p>
          </div>
          <div class="card rounded-3xl p-6 card-hover soft">
            <div class="w-14 h-14 rounded-2xl bg-[var(--brown)]/10 text-[var(--brown)] flex items-center justify-center text-2xl mb-4">⚡</div>
            <h3 class="display-font text-2xl font-black text-[var(--brown)] mb-3">تفاعل مباشر وسريع</h3>
            <p class="text-lg leading-8">بودكاست اليوم والمود والتصويت والاقتباس تعمل من دون تحميل إضافي وبسلاسة واضحة.</p>
          </div>
        </div>
      </div>
    </section>
    <section id="page-programs" class="page">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div class="min-w-0">
            <h2 class="section-title display-font">البرامج</h2>
            <p class="section-sub mt-3">حلقات سعودية مختارة، وكل عنصر له صورة مستقلة ومناسبة، والتفاصيل فيه خاصة بهذا العنصر.</p>
          </div>
          <input id="programSearch" type="text" placeholder="ابحث داخل البرامج" class="w-full md:w-80 px-4 py-3 rounded-2xl bg-white border border-[var(--brown)]/10 shadow-sm focus:outline-none focus:ring-2 focus:ring-[var(--brown)]/30">
        </div>
        <div id="programFilterBar" class="flex flex-wrap gap-2 mb-6"></div>
        <div id="programGrid" class="grid lg:grid-cols-2 xl:grid-cols-3 gap-6"></div>
      </div>
    </section>

    <section id="page-articles" class="page">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="section-title display-font">مقال</h2>
            <p class="section-sub mt-3">مقالات طويلة عن السرد والصورة والهوية الصوتية في البودكاست السعودي، مع صور لا تتكرر.</p>
          </div>
        </div>
        <div id="articleGrid" class="grid md:grid-cols-2 xl:grid-cols-3 gap-6"></div>
      </div>
    </section>

    <section id="page-investigations" class="page">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="section-title display-font">تحقيق</h2>
            <p class="section-sub mt-3">تحقيقات مطولة تفكك المشهد السعودي وتقرأ الحلقة الطويلة والهوية البصرية والصوتية بعمق.</p>
          </div>
        </div>
        <div id="investigationGrid" class="grid md:grid-cols-2 xl:grid-cols-3 gap-6"></div>
      </div>
    </section>

    <section id="page-reports" class="page">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="section-title display-font">تقارير</h2>
            <p class="section-sub mt-3">تقارير عن الاستماع والسلوك والمنصات والجمهور، وكل عنصر بصورة مناسبة مختلفة عن غيرها.</p>
          </div>
        </div>
        <div id="reportGrid" class="grid md:grid-cols-2 xl:grid-cols-3 gap-6"></div>
      </div>
    </section>

    <section id="page-news" class="page">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="section-title display-font">أخبار</h2>
            <p class="section-sub mt-3">أخبار سعودية واسعة عن البودكاست والوزارة والمدينة والمنصة، وكل خبر له صورة مستقلة.</p>
          </div>
          <div class="pill">تغطية يومية</div>
        </div>
        <div id="newsGrid" class="grid md:grid-cols-2 xl:grid-cols-3 gap-6"></div>
      </div>
    </section>

    <section id="page-interactive" class="page">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="section-title display-font">تفاعلي</h2>
            <p class="section-sub mt-3">أدوات تفاعلية خفيفة: توصية، مود، تصويت مرة واحدة فقط من هذا المتصفح، واقتباس، واختبار قصير.</p>
          </div>
        </div>
        <div class="grid lg:grid-cols-3 gap-6">
          <div class="card rounded-[2rem] p-7">
            <span class="text-6xl block mb-4">🎧</span>
            <h3 class="display-font text-2xl font-black text-[var(--brown)] mb-3">بودكاست اليوم</h3>
            <p class="text-lg leading-8 mb-5">كل مرة يظهر ترشيح مختلف، مرتبط بطبيعة الاستماع والتحول السعودي في المحتوى الصوتي.</p>
            <button type="button" class="bg-[var(--brown)] text-white px-5 py-4 rounded-2xl font-black w-full shadow-xl hover:scale-[1.03] soft" id="recommendBtn">اقترح لي برنامجًا</button>
            <div id="recommendBox" class="hidden mt-5 rounded-3xl p-5 bg-[var(--bg)] border border-[var(--brown)]/10">
              <h4 id="recommendTitle" class="display-font text-2xl font-black text-[var(--brown)] mb-2"></h4>
              <p id="recommendText" class="text-[var(--text)] leading-8"></p>
            </div>
          </div>
          <div class="card rounded-[2rem] p-7">
            <span class="text-6xl block mb-4">💡</span>
            <h3 class="display-font text-2xl font-black text-[var(--brown)] mb-3">اختر مودك</h3>
            <p class="text-lg leading-8 mb-5">ضحك، تفكير، نفس، أو تشويق. كل زر يغيّر الترشيحات النصية داخل الصفحة.</p>
            <div class="grid grid-cols-2 gap-2">
              <button type="button" class="mood-btn bg-[var(--brown)]/10 hover:bg-[var(--brown)] hover:text-white text-[var(--brown)] px-3 py-3 rounded-xl font-bold soft" data-mood="ضحك">أبي أضحك</button>
              <button type="button" class="mood-btn bg-[var(--brown)]/10 hover:bg-[var(--brown)] hover:text-white text-[var(--brown)] px-3 py-3 rounded-xl font-bold soft" data-mood="تفكير">أبي أفكر</button>
              <button type="button" class="mood-btn bg-[var(--brown)]/10 hover:bg-[var(--brown)] hover:text-white text-[var(--brown)] px-3 py-3 rounded-xl font-bold soft" data-mood="نفسي">أبي شيء نفسي</button>
              <button type="button" class="mood-btn bg-[var(--brown)]/10 hover:bg-[var(--brown)] hover:text-white text-[var(--brown)] px-3 py-3 rounded-xl font-bold soft" data-mood="تشويق">أبي تشويق</button>
            </div>
            <div class="mt-5 bg-[var(--bg)] rounded-2xl p-4 border border-[var(--brown)]/10">
              <div class="text-sm text-[var(--olive)] mb-1">المود الحالي</div>
              <div id="currentMood" class="display-font text-2xl font-black text-[var(--brown)]">ضحك</div>
            </div>
          </div>
          <div class="card rounded-[2rem] p-7">
            <span class="text-6xl block mb-4">🗳</span>
            <h3 class="display-font text-2xl font-black text-[var(--brown)] mb-3">صوّت لأفضل بودكاست سعودي</h3>
            <p class="text-lg leading-8 mb-5">التصويت هنا داخل الجلسة فقط، ومرة واحدة فقط من هذا المتصفح.</p>
            <button id="voteBtn" type="button" class="bg-white border-2 border-[var(--brown)] text-[var(--brown)] px-5 py-4 rounded-2xl font-black w-full hover:bg-[var(--brown)] hover:text-white soft">ابدأ التصويت</button>
            <div class="mt-5 space-y-3 text-right bg-[var(--bg)] rounded-3xl p-5 border border-[var(--brown)]/10">
              <div class="flex justify-between"><span>فنجان</span><span id="voteFanjan">0</span></div>
              <div class="flex justify-between"><span>جناية</span><span id="voteJinaya">0</span></div>
              <div class="flex justify-between"><span>The Mo Show</span><span id="voteMosho">0</span></div>
              <div class="flex justify-between"><span>سرديات</span><span id="voteSardyat">0</span></div>
            </div>
          </div>
        </div>
        <div class="grid lg:grid-cols-3 gap-6 mt-6">
          <div class="card rounded-[2rem] p-7">
            <h3 class="display-font text-2xl font-black text-[var(--brown)] mb-3">كم ساعة تسمع بودكاست بالأسبوع؟</h3>
            <input id="hoursSlider" type="range" min="0" max="40" value="8" class="w-full">
            <div class="flex justify-between text-sm text-[var(--olive)] mt-2"><span>0</span><span>40</span></div>
            <div class="mt-4 rounded-2xl bg-[var(--bg)] border border-[var(--brown)]/10 p-4">
              <div class="text-sm text-[var(--olive)]">عدد الساعات</div>
              <div id="hoursValue" class="display-font text-3xl font-black text-[var(--brown)]">8 ساعة</div>
            </div>
          </div>
          <div class="card rounded-[2rem] p-7">
            <h3 class="display-font text-2xl font-black text-[var(--brown)] mb-3">اقتباس اليوم</h3>
            <div class="rounded-3xl bg-[var(--bg)] border border-[var(--brown)]/10 p-5 leading-9 text-lg text-[var(--text)]">
              <span class="quote-mark">“</span>
              <span id="quoteBox">مو كل صمت راحة.</span>
            </div>
            <button type="button" class="mt-4 bg-[var(--olive)] text-white px-5 py-3 rounded-2xl font-black w-full" id="quoteBtn">اقتباس جديد</button>
          </div>
          <div class="card rounded-[2rem] p-7">
            <h3 class="display-font text-2xl font-black text-[var(--brown)] mb-3">اختبر شخصيتك: أي برنامج يشبهك؟</h3>
            <div class="grid grid-cols-2 gap-2">
              <button type="button" class="quiz-btn bg-[var(--brown)]/10 text-[var(--brown)] px-3 py-3 rounded-xl font-bold soft" data-quiz="fanjan">تفكير عميق</button>
              <button type="button" class="quiz-btn bg-[var(--brown)]/10 text-[var(--brown)] px-3 py-3 rounded-xl font-bold soft" data-quiz="jinaya">تشويق</button>
              <button type="button" class="quiz-btn bg-[var(--brown)]/10 text-[var(--brown)] px-3 py-3 rounded-xl font-bold soft" data-quiz="kanbat">شيء نفسي</button>
              <button type="button" class="quiz-btn bg-[var(--brown)]/10 text-[var(--brown)] px-3 py-3 rounded-xl font-bold soft" data-quiz="abjora">تطوير ذات</button>
            </div>
            <div id="quizResult" class="mt-4 rounded-2xl bg-[var(--bg)] border border-[var(--brown)]/10 p-4">اختر إجابة لتظهر النتيجة.</div>
          </div>
        </div>
        <div class="grid lg:grid-cols-2 gap-6 mt-6">
          <div class="card rounded-[2rem] p-7">
            <h3 class="display-font text-2xl font-black text-[var(--brown)] mb-3">ترشيحات حسب مودك</h3>
            <div id="moodRecommendation" class="rounded-3xl bg-[var(--bg)] border border-[var(--brown)]/10 p-5">اضغط أحد الأزرار بالأعلى لاختيار مزاجك.</div>
          </div>
          <div class="card rounded-[2rem] p-7">
            <h3 class="display-font text-2xl font-black text-[var(--brown)] mb-3">خريطة المنصات</h3>
            <div class="grid sm:grid-cols-3 gap-4">
              <div class="rounded-3xl p-4 bg-[var(--bg)] border border-black/5"><div class="font-black text-lg text-[var(--brown)] flex items-center gap-2"><span>🍎</span>Apple Podcasts</div><div class="text-sm text-[var(--text)] mt-2">الصفحات الرسمية للحلقات والبرامج.</div></div>
              <div class="rounded-3xl p-4 bg-[var(--bg)] border border-black/5"><div class="font-black text-lg text-[var(--brown)] flex items-center gap-2"><span>🟢</span>Spotify</div><div class="text-sm text-[var(--text)] mt-2">خيار شائع للاستماع أثناء الحركة.</div></div>
              <div class="rounded-3xl p-4 bg-[var(--bg)] border border-black/5"><div class="font-black text-lg text-[var(--brown)] flex items-center gap-2"><span>▶</span>YouTube</div><div class="text-sm text-[var(--text)] mt-2">للمشاهد المرئية والمقاطع القصيرة.</div></div>
            </div>
          </div>
        </div>
        <div class="mt-6 bg-[var(--brown)] text-white rounded-[2rem] p-8 shadow-2xl">
          <p class="display-font text-2xl md:text-3xl font-black leading-relaxed">“مُلهم.. حيث يبدأ الإلهام السعودي، ويكتب تاريخ الصوت من قلب المملكة.”</p>
        </div>
      </div>
    </section>

    <section id="page-references" class="page">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 py-10 md:py-14">
        <div class="flex items-center justify-between gap-4 flex-wrap mb-8">
          <div>
            <h2 class="section-title display-font">المراجع</h2>
            <p class="section-sub mt-3">مرتبة بأسلوب قريب من الصورة: بند، ثم النص، ثم رابط الاسترجاع أسفلها.</p>
          </div>
        </div>
        <div id="referencesGrid" class="grid gap-4"></div>
      </div>
    </section>
  </main>

  <div id="detailModal" class="fixed inset-0 z-[140] flex items-center justify-center p-4 hidden overlay-hidden soft">
    <div class="absolute inset-0 bg-black/60 backdrop-blur-sm" data-close-modal></div>
    <div class="relative z-10 w-full max-w-6xl bg-white rounded-[2rem] shadow-2xl overflow-hidden border border-black/5">
      <div class="p-5 md:p-6 flex items-start justify-between gap-4 border-b border-black/5">
        <div class="min-w-0">
          <div id="detailKicker" class="text-sm text-[var(--olive)] font-bold mb-2">التفاصيل</div>
          <h3 id="detailTitle" class="display-font text-3xl md:text-4xl font-black text-[var(--brown)] leading-tight"></h3>
        </div>
        <button type="button" class="w-11 h-11 rounded-full bg-black/5 hover:bg-black/10 soft text-2xl leading-none" data-close-modal>×</button>
      </div>
      <div class="grid lg:grid-cols-5">
        <div class="lg:col-span-2 p-5 md:p-6">
          <div class="image-frame rounded-[1.5rem] overflow-hidden">
            <img id="detailImage" src="" alt="">
          </div>
          <div class="mt-4 flex flex-wrap gap-2" id="detailTags"></div>
        </div>
        <div class="lg:col-span-3 p-5 md:p-6">
          <div class="flex flex-wrap items-center gap-3 mb-4">
            <span id="detailLabel" class="px-3 py-1 rounded-full bg-[var(--brown)]/10 text-[var(--brown)] font-black text-sm"></span>
            <span id="detailMeta" class="text-sm text-[var(--olive)] font-bold"></span>
            <span id="detailType" class="text-sm text-[var(--olive)] font-bold"></span>
          </div>
          <p id="detailLead" class="text-xl md:text-2xl leading-loose text-[var(--text)]"></p>
          <div id="detailBody" class="content mt-6"></div>
          <button id="moreBtn" type="button" class="mt-4 bg-[var(--olive)] text-white px-6 py-4 rounded-2xl font-black shadow-lg hover:scale-[1.02] soft">اقرأ المزيد</button>
          <div id="moreBox" class="hidden mt-6 section-box p-5">
            <div class="text-sm text-[var(--olive)] font-bold mb-3">النص الكامل</div>
            <div id="moreBody" class="content"></div>
          </div>
          <div id="detailWatchArea" class="mt-6 hidden"></div>
          <div id="detailSources" class="mt-6"></div>
        </div>
      </div>
    </div>
  </div>

  <div id="devModal" class="fixed inset-0 z-[130] flex items-center justify-center p-4 hidden overlay-hidden soft">
    <div class="absolute inset-0 bg-black/60 backdrop-blur-sm" data-close-dev></div>
    <div class="relative z-10 w-full max-w-2xl bg-white rounded-[2rem] shadow-2xl overflow-hidden border border-black/5">
      <div class="p-6 md:p-8">
        <div class="flex items-start justify-between gap-4 mb-5">
          <div>
            <div class="text-sm text-[var(--olive)] font-bold mb-2">فريق الموقع</div>
            <h3 class="display-font text-3xl md:text-4xl font-black text-[var(--brown)]">فريق مُلهم</h3>
          </div>
          <button type="button" class="w-11 h-11 rounded-full bg-black/5 hover:bg-black/10 soft text-2xl leading-none" data-close-dev>×</button>
        </div>
        <div class="grid gap-4">
          <div class="rounded-2xl p-4 border border-black/5 bg-[var(--bg)] flex items-center justify-between"><span class="display-font font-black text-lg text-[var(--brown)]">عهد المحمدي</span><span class="font-bold text-[var(--text)]">4556365</span></div>
          <div class="rounded-2xl p-4 border border-black/5 bg-[var(--bg)] flex items-center justify-between"><span class="display-font font-black text-lg text-[var(--brown)]">علياء العوفي</span><span class="font-bold text-[var(--text)]">4553854</span></div>
          <div class="rounded-2xl p-4 border border-black/5 bg-[var(--bg)] flex items-center justify-between"><span class="display-font font-black text-lg text-[var(--brown)]">كوثر المطرفي</span><span class="font-bold text-[var(--text)]">4550073</span></div>
          <div class="rounded-2xl p-4 border border-black/5 bg-[var(--bg)] flex items-center justify-between"><span class="display-font font-black text-lg text-[var(--brown)]">ساره الحربي</span><span class="font-bold text-[var(--text)]">4555801</span></div>
          <div class="rounded-2xl p-4 border border-black/5 bg-[var(--bg)] flex items-center justify-between"><span class="display-font font-black text-lg text-[var(--brown)]">هديل الحربي</span><span class="font-bold text-[var(--text)]">4554545</span></div>
        </div>
        <div class="mt-6 rounded-2xl bg-[var(--brown)] text-white p-5">
          <div class="display-font font-black text-lg">شعبة F7</div>
          <div class="text-white/90 mt-1">دكتور المقرر: خالد القحطاني</div>
        </div>
      </div>
    </div>
  </div>

  <script>
    const $ = s => document.querySelector(s);
    const $$ = s => [...document.querySelectorAll(s)];

    const state = {
      page:'home',
      previous:'home',
      current:null,
      quoteIndex:0,
      voted: localStorage.getItem('mulham_voted_once_v4') === '1',
      votes: JSON.parse(localStorage.getItem('mulham_votes_v32') || 'null') || { fanjan:0, jinaya:0, mosho:0, sardyat:0 },
      programQuery:'',
      programFilter:'all'
    };

    const USER_LOGO_URL = "https://media.discordapp.net/attachments/937276649261633546/1505573694125244456/image.png?ex=6a0b1e44&is=6a09ccc4&hm=04f2443f20a4cd817d397a7b7a3acba01371588e388e08170cb185a10971a566&=&format=webp&quality=lossless";

    const quotes = ['مو كل صمت راحة.','الصوت حين يصدق، يصير ذاكرة.','المعنى لا يحتاج ضجيجًا كي يصل.','الحكاية السعودية أكبر من عنوان واحد.','التفاصيل الصغيرة تصنع المشهد الكبير.'];

    const moods = {
      ضحك:'إذا مال مزاجك إلى الخفة، فالأفضل أن تتجه إلى حلقة تجمع بين اللطف وسرعة الإيقاع من دون فقدان المعنى.',
      تفكير:'المزاج المتأمل يناسبه المحتوى الذي يشرح ويتدرج ويترك مساحة للفهم.',
      نفسي:'المحتوى الهادئ هو الأنسب حين تريد صوتًا قريبًا ونبرة أكثر دفئًا.',
      تشويق:'إذا أردت توترًا لطيفًا وتدرجًا في الانتباه، فاختر الحلقات التي تبني السؤال خطوة خطوة.'
    };

    const recommendations = [
      { title:'حلقة العلا', text:'مناسبة حين تريد محتوى يمشي ببطء ويفتح المكان كقصة كاملة.' },
      { title:'حلقة الرياض', text:'مناسبة إذا أردت أن ترى المدينة كصوت حي لا كخلفية صامتة.' },
      { title:'الحلقة الخاصة الأولى', text:'مناسبة عندما تبحث عن ملف طويل ومفصل يقرأ التحول السعودي من زاوية القيادة والرؤية.' },
      { title:'المقال التحليلي', text:'إذا كنت تريد لغة مستقرة تشرح لماذا يفضل الجمهور السرد الهادئ.' }
    ];

    function toast(msg){
      const el = document.createElement('div');
      el.className = 'card px-4 py-3 rounded-2xl shadow-lg pointer-events-auto';
      el.textContent = msg;
      $('#toastBox').appendChild(el);
      setTimeout(() => { el.style.opacity = '0'; el.style.transform = 'translateY(6px)'; setTimeout(() => el.remove(), 220); }, 2200);
    }

    function validSrc(s){ return typeof s === 'string' && s && s !== 'REPLACE_ME'; }
    function escHtml(s){ return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;'); }
    function hashCode(str){ let h = 0; for (let i = 0; i < str.length; i++) { h = ((h << 5) - h) + str.charCodeAt(i); h |= 0; } return Math.abs(h); }

    /* =====================================================
       إعداد الصور السريع
       عدّل الروابط هنا فقط، وستنعكس على كل الأقسام تلقائياً.
       - كل عنوان يمكن أن يأخذ 3 صور مختلفة.
       - الصور الواقعية محفوظة بالترتيب: برامج / أخبار / تقارير / مقالات / تحقيق.
       - إذا أردت صورة معينة، غيّر الرابط هنا فقط.
    ====================================================== */
    // تعديل الصور السريعة: غيّر الروابط هنا مباشرة لكل قسم أو عنوان تريد تخصيصه.
    const IMAGE_EDITOR = {
      exact: {
        'الحلقة الأولى: البودكاست مع ولي العهد': [
          'https://upload.wikimedia.org/wikipedia/commons/1/19/Prince_Muhammad_of_Saudia.png',
          'https://upload.wikimedia.org/wikipedia/commons/0/0c/Prince_Mohammad_bin_Salman%2C_Oct._2023.jpg',
          'https://upload.wikimedia.org/wikipedia/commons/b/be/The_Prime_Minister%2C_Shri_Narendra_Modi_with_the_Deputy_Crown_Prince_of_Saudi_Arabia%2C_Mohammed_bin_Salman%2C_at_G20_Summit_2016%2C_in_Hangzhou%2C_China_on_September_04%2C_2016.jpg'
        ],
        'بودكاست الرياض: المدينة التي تصنع لسانها': [
          'https://source.unsplash.com/featured/1400x900/?riyadh,skyline,saudi-arabia&sig=11',
          'https://source.unsplash.com/featured/1400x900/?riyadh,city,saudi-arabia&sig=12',
          'https://source.unsplash.com/featured/1400x900/?riyadh,modern-city,saudi-arabia&sig=13'
        ],
        'العلا: حين يروي المكان نفسه': [
          'https://source.unsplash.com/featured/1400x900/?alula,saudi-arabia,desert-rock&sig=21',
          'https://source.unsplash.com/featured/1400x900/?alula,saudi-arabia,heritage&sig=22',
          'https://source.unsplash.com/featured/1400x900/?alula,saudi-arabia,landscape&sig=23'
        ],
        'البودكاست النسائي السعودي: حضور واتزان': [
          'https://source.unsplash.com/featured/1400x900/?hijab,woman,podcast,studio&sig=31',
          'https://source.unsplash.com/featured/1400x900/?hijab,female,interview,studio&sig=32',
          'https://source.unsplash.com/featured/1400x900/?muslim-woman,headscarf,recording&sig=33'
        ]
      },
      rules: [
        {
          test: /ولي العهد|محمد بن سلمان/,
          images: [
            'https://upload.wikimedia.org/wikipedia/commons/1/19/Prince_Muhammad_of_Saudia.png',
            'https://upload.wikimedia.org/wikipedia/commons/0/0c/Prince_Mohammad_bin_Salman%2C_Oct._2023.jpg',
            'https://upload.wikimedia.org/wikipedia/commons/b/be/The_Prime_Minister%2C_Shri_Narendra_Modi_with_the_Deputy_Crown_Prince_of_Saudi_Arabia%2C_Mohammed_bin_Salman%2C_at_G20_Summit_2016%2C_in_Hangzhou%2C_China_on_September_04%2C_2016.jpg'
          ]
        },
        {
          test: /الرياض/,
          images: [
            'https://source.unsplash.com/featured/1400x900/?riyadh,skyline,saudi-arabia&sig=41',
            'https://source.unsplash.com/featured/1400x900/?riyadh,city,saudi-arabia&sig=42',
            'https://source.unsplash.com/featured/1400x900/?riyadh,modern-city,saudi-arabia&sig=43'
          ]
        },
        {
          test: /العلا/,
          images: [
            'https://source.unsplash.com/featured/1400x900/?alula,saudi-arabia,desert-rock&sig=51',
            'https://source.unsplash.com/featured/1400x900/?alula,saudi-arabia,heritage&sig=52',
            'https://source.unsplash.com/featured/1400x900/?alula,saudi-arabia,landscape&sig=53'
          ]
        },
        {
          test: /البودكاست النسائي|النساء|نسائي|حضور واتزان/,
          images: [
            'https://source.unsplash.com/featured/1400x900/?hijab,woman,podcast,studio&sig=61',
            'https://source.unsplash.com/featured/1400x900/?hijab,female,interview,studio&sig=62',
            'https://source.unsplash.com/featured/1400x900/?muslim-woman,headscarf,recording&sig=63'
          ]
        },
        {
          test: /استوديو|ميكروفون|حوار|مقدم|صوت|برنامج|حلقة|بودكاست/,
          images: [
            'https://source.unsplash.com/featured/1400x900/?podcast,studio,microphone,interview&sig=71',
            'https://source.unsplash.com/featured/1400x900/?podcast,recording,studio,interview&sig=72',
            'https://source.unsplash.com/featured/1400x900/?microphone,studio,conversation&sig=73'
          ]
        }
      ],
      sectionPools: {
        programs: ['podcast studio microphone interview','podcast recording microphone','saudi podcast studio'],
        articles: ['editorial writing desk','journalism notebook analysis','feature writing desk'],
        investigations: ['investigative journalism newsroom','reporter notebook interview','media investigation desk'],
        reports: ['riyadh skyline city commute','alula desert heritage landscape','daily life saudi city'],
        news: ['newsroom city skyline saudi arabia','breaking news newsroom editorial','podcast microphone interview'],
        videos: ['video podcast studio camera','podcast filming interview','recording studio lights'],
        default: ['podcast studio','editorial','saudi city']
      }
    };


    const IMAGE_SEEN = new Set();

    function fallbackImage(key, section){
      const fallbackPools = {
        programs: [
          'podcast studio microphone interview',
          'saudi podcast studio',
          'microphone recording room',
          'podcast host studio'
        ],
        articles: [
          'editorial desk notebook',
          'journalism writing desk',
          'feature article workspace',
          'analysis notebook journalism'
        ],
        investigations: [
          'investigative newsroom desk',
          'reporter interview notebook',
          'media desk investigation',
          'journalism camera interview'
        ],
        reports: [
          'riyadh skyline saudi arabia',
          'alula desert heritage',
          'saudi city commute',
          'modern saudi city'
        ],
        news: [
          'newsroom editorial desk',
          'breaking news newsroom',
          'podcast microphone interview',
          'saudi city skyline news'
        ],
        videos: [
          'video podcast studio camera',
          'podcast filming interview',
          'recording studio lights',
          'youtube podcast set'
        ],
        default: [
          'podcast studio',
          'editorial',
          'saudi city',
          'newsroom'
        ]
      };
      const pool = fallbackPools[section] || fallbackPools.default;
      const q = pool[Math.abs(hashCode(key)) % pool.length];
      const sig = Math.abs(hashCode(`${section}-${key}-fallback`));
      return `https://source.unsplash.com/featured/1400x900/?${encodeURIComponent(q)}&sig=${sig}`;
    }

    function resolveUniqueImage(candidate, key, section){
      let url = String(candidate || '').trim();
      if (!url) {
        url = fallbackImage(key, section);
      }
      if (!IMAGE_SEEN.has(url)) {
        IMAGE_SEEN.add(url);
        return url;
      }
      for (let i = 1; i <= 6; i++) {
        let alt = fallbackImage(`${key}-${i}`, section);
        if (!IMAGE_SEEN.has(alt)) {
          IMAGE_SEEN.add(alt);
          return alt;
        }
      }
      const last = url.includes('?') ? `${url}&v=${Math.abs(hashCode(key))}` : `${url}?v=${Math.abs(hashCode(key))}`;
      IMAGE_SEEN.add(last);
      return last;
    }

    function realImage(section, title, idx, variant = 0){
      const t = String(title || '');
      const key = `${section}-${title}-${idx}-${variant}`;
      const exact = IMAGE_EDITOR.exact[t];
      if (exact && exact.length) {
        const candidate = exact[Math.abs(hashCode(key)) % exact.length];
        return resolveUniqueImage(candidate, key, section);
      }
      for (const rule of IMAGE_EDITOR.rules) {
        if (rule.test.test(t)) {
          const candidate = rule.images[Math.abs(hashCode(key)) % rule.images.length];
          return resolveUniqueImage(candidate, key, section);
        }
      }
      const pool = IMAGE_EDITOR.sectionPools[section] || IMAGE_EDITOR.sectionPools.default;
      const q = pool[Math.abs(hashCode(key)) % pool.length];
      const sig = Math.abs(hashCode(key));
      const candidate = `https://source.unsplash.com/featured/1400x900/?${encodeURIComponent(q)}&sig=${sig}`;
      return resolveUniqueImage(candidate, key, section);
    }

function svgCover(title, section, idx){
      const palettes = {
        programs: ['#7a5a2e','#7a856f'], articles: ['#5f6d5c','#efe4d5'], investigations: ['#8b6a38','#f4ead8'], reports: ['#7a856f','#eadfcf'], news: ['#4e4a43','#d8cbb8'], videos: ['#7a5a2e','#f1e6d9'], home: ['#7a5a2e','#7a856f']
      };
      const [bg, accent] = palettes[section] || palettes.home;
      const motifs = ['leadership','city','pod','frame','editorial','mic','wave','meeting'];
      const motif = motifs[(hashCode(title) + idx) % motifs.length];
      const safe = escHtml(title.length > 36 ? title.slice(0, 36) : title);
      const shapes = {
        city: `<rect x="0" y="250" width="900" height="150" fill="${accent}" opacity=".20"/><rect x="120" y="192" width="72" height="110" rx="10" fill="#fff" opacity=".20"/><rect x="220" y="146" width="50" height="156" rx="10" fill="#fff" opacity=".16"/><rect x="292" y="118" width="82" height="184" rx="12" fill="#fff" opacity=".24"/><rect x="392" y="164" width="62" height="138" rx="10" fill="#fff" opacity=".15"/><rect x="478" y="98" width="100" height="204" rx="14" fill="#fff" opacity=".22"/><rect x="602" y="144" width="76" height="158" rx="12" fill="#fff" opacity=".14"/><rect x="694" y="126" width="120" height="176" rx="14" fill="#fff" opacity=".18"/>`,
        mic: `<rect x="220" y="100" width="96" height="162" rx="48" fill="#fff" opacity=".16"/><rect x="248" y="260" width="40" height="70" rx="18" fill="#fff" opacity=".42"/><rect x="205" y="272" width="130" height="18" rx="9" fill="#fff" opacity=".22"/><path d="M186 170 C186 238 350 238 350 170" fill="none" stroke="#fff" stroke-width="10" opacity=".22"/><circle cx="670" cy="126" r="60" fill="${accent}" opacity=".18"/>`,
        pod: `<circle cx="256" cy="176" r="74" fill="#fff" opacity=".13"/><circle cx="256" cy="176" r="46" fill="${bg}" opacity=".33"/><rect x="248" y="230" width="16" height="78" rx="8" fill="#fff" opacity=".72"/><rect x="176" y="154" width="160" height="24" rx="12" fill="#fff" opacity=".16"/><circle cx="650" cy="120" r="58" fill="${accent}" opacity=".18"/>`,
        wave: `<path d="M0 250 C130 190 195 318 320 262 C424 214 520 144 636 206 C748 264 822 244 900 206 L900 400 L0 400 Z" fill="${accent}" opacity=".22"/><path d="M0 310 C110 274 210 348 340 304 C484 254 580 348 710 306 C792 278 840 274 900 262 L900 400 L0 400 Z" fill="#fff" opacity=".10"/>`,
        frame: `<rect x="112" y="86" width="228" height="232" rx="24" fill="#fff" opacity=".10"/><rect x="156" y="124" width="140" height="156" rx="18" fill="${bg}" opacity=".24"/><rect x="396" y="118" width="162" height="166" rx="26" fill="#fff" opacity=".15"/><circle cx="688" cy="120" r="54" fill="${accent}" opacity=".18"/>`,
        editorial: `<rect x="130" y="138" width="186" height="124" rx="22" fill="#fff" opacity=".13"/><rect x="348" y="104" width="114" height="190" rx="20" fill="${accent}" opacity=".17"/><rect x="496" y="136" width="166" height="128" rx="22" fill="#fff" opacity=".10"/><path d="M184 222 L262 152" stroke="#fff" stroke-width="16" opacity=".20" stroke-linecap="round"/><circle cx="708" cy="126" r="48" fill="#fff" opacity=".14"/>`,
        leadership: `<circle cx="250" cy="145" r="66" fill="${accent}" opacity=".18"/><rect x="126" y="178" width="250" height="148" rx="72" fill="#fff" opacity=".14"/><rect x="177" y="210" width="145" height="110" rx="55" fill="${bg}" opacity=".28"/><rect x="219" y="128" width="64" height="24" rx="12" fill="#fff" opacity=".72"/><circle cx="252" cy="171" r="14" fill="#fff" opacity=".92"/><rect x="192" y="142" width="120" height="18" rx="9" fill="#fff" opacity=".18"/>`,
        meeting: `<rect x="118" y="120" width="246" height="172" rx="24" fill="#fff" opacity=".12"/><rect x="390" y="108" width="130" height="196" rx="24" fill="${accent}" opacity=".16"/><circle cx="680" cy="122" r="52" fill="#fff" opacity=".14"/><path d="M176 236 H300" stroke="#fff" stroke-width="14" opacity=".18" stroke-linecap="round"/>`
      };
      const svg = `
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 900 400" role="img" aria-label="${safe}">
        <defs><linearGradient id="g" x1="0" x2="1" y1="0" y2="1"><stop offset="0%" stop-color="${bg}"/><stop offset="100%" stop-color="#5b4525"/></linearGradient></defs>
        <rect width="900" height="400" fill="url(#g)"/>
        <circle cx="770" cy="82" r="120" fill="#fff" opacity=".07"/>
        <circle cx="120" cy="320" r="160" fill="#fff" opacity=".06"/>
        ${shapes[motif]}
        <text x="58" y="62" fill="#fff" font-size="34" font-family="Amiri,serif" font-weight="700">${safe}</text>
        <text x="58" y="118" fill="#fff" font-size="54" font-family="Amiri,serif" font-weight="900">${safe}</text>
        <text x="58" y="360" fill="#fff" font-size="22" font-family="Tajawal,Arial" opacity=".85">مُلهم | الصحيفة الإلكترونية للبودكاست السعودي</text>
      </svg>`;
      return 'data:image/svg+xml;charset=UTF-8,' + encodeURIComponent(svg);
    }

    
    // غيّر روابط البرامج ونبذها وتصنيفها من هذا الجدول فقط عند الحاجة
    const PROGRAM_VIDEO_MAP = {
      "الحلقة الأولى: البودكاست مع ولي العهد": {
            "watchUrl": "https://youtu.be/MnKoES8rcKA",
            "pageUrl": "https://www.youtube.com/results?search_query=الحلقة+الخاصة",
            "category": "مميز",
            "programName": "الحلقة الخاصة",
            "lead": "الحلقة الخاصة: الحلقة تعرض حوارًا مطولًا مع ولي العهد وتفتح ملفات التحول والرؤية والمجتمع السعودي في صيغة حوارية مباشرة.",
            "programBrief": "الحلقة الخاصة تعرض حوارًا مطولًا مع ولي العهد، وتضعه ضمن سياق التحول الوطني ورؤية المملكة.",
            "episodeBrief": "الحلقة تعرض حوارًا مطولًا مع ولي العهد وتفتح ملفات التحول والرؤية والمجتمع السعودي في صيغة حوارية مباشرة.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "مميز",
                  "الحلقة الخاصة",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/MnKoES8rcKA"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=الحلقة+الخاصة"
                  ]
            ]
      },
      "مذكرات رجل أمن سعودي | بودكاست فنجان": {
            "watchUrl": "https://youtu.be/OetssqWJycg",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+فنجان",
            "category": "أخرى",
            "programName": "بودكاست فنجان",
            "lead": "بودكاست فنجان: الحلقة تستمع إلى مذكرات رجل أمن سعودي، وتعرض الذاكرة المهنية من داخل التجربة الأمنية وما تحمله من مواقف ومسؤوليات.",
            "programBrief": "فنجان برنامج حواري طويل من ثمانية، يفتح مساحة واسعة للضيف حتى يشرح تجربته وفكرته من دون اختصار مخل.",
            "episodeBrief": "الحلقة تستمع إلى مذكرات رجل أمن سعودي، وتعرض الذاكرة المهنية من داخل التجربة الأمنية وما تحمله من مواقف ومسؤوليات.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "أخرى",
                  "بودكاست فنجان",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/OetssqWJycg"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+فنجان"
                  ]
            ]
      },
      "الحكم لله ثم لعبدالعزيز | بودكاست فنجان": {
            "watchUrl": "https://youtu.be/HwVwgIBFj_4",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+فنجان",
            "category": "أخرى",
            "programName": "بودكاست فنجان",
            "lead": "بودكاست فنجان: الحلقة تتناول عبارة مرتبطة بتاريخ الملك عبدالعزيز، وتفتح بابًا لفهم الحكم والتوحيد وبناء الدولة في سياقه التاريخي.",
            "programBrief": "فنجان برنامج حواري طويل من ثمانية، يفتح مساحة واسعة للضيف حتى يشرح تجربته وفكرته من دون اختصار مخل.",
            "episodeBrief": "الحلقة تتناول عبارة مرتبطة بتاريخ الملك عبدالعزيز، وتفتح بابًا لفهم الحكم والتوحيد وبناء الدولة في سياقه التاريخي.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "أخرى",
                  "بودكاست فنجان",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/HwVwgIBFj_4"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+فنجان"
                  ]
            ]
      },
      "الحل السعودي للعالم في الذكاء الاصطناعي | بودكاست سقراط": {
            "watchUrl": "https://youtu.be/dzc0XEKzCRM",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+سقراط",
            "category": "أخرى",
            "programName": "بودكاست سقراط",
            "lead": "بودكاست سقراط: الحلقة تناقش موقع السعودية في الذكاء الاصطناعي، وتربط الطموح التقني بالحلول التي يمكن أن تقدمها المملكة للعالم.",
            "programBrief": "سقراط برنامج من ثمانية يركز على الملفات العامة والتحولات السعودية عبر حوارات مباشرة مع مسؤولين ومختصين.",
            "episodeBrief": "الحلقة تناقش موقع السعودية في الذكاء الاصطناعي، وتربط الطموح التقني بالحلول التي يمكن أن تقدمها المملكة للعالم.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "أخرى",
                  "بودكاست سقراط",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/dzc0XEKzCRM"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+سقراط"
                  ]
            ]
      },
      "كابتن طيار اختطف مرتين | بودكاست مربع": {
            "watchUrl": "https://youtu.be/yNwQqqU2_tE",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+مربع",
            "category": "أخرى",
            "programName": "بودكاست مربع",
            "lead": "بودكاست مربع: الحلقة تستضيف كابتن طيار مر بتجربتي اختطاف، وتروي كيف تُقرأ المواقف الصعبة من زاوية مهنية وإنسانية.",
            "programBrief": "مربع برنامج حواري يمنح القصص الشخصية مساحة طويلة، ويعتمد على الاستماع للتجربة كما يرويها صاحبها.",
            "episodeBrief": "الحلقة تستضيف كابتن طيار مر بتجربتي اختطاف، وتروي كيف تُقرأ المواقف الصعبة من زاوية مهنية وإنسانية.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "أخرى",
                  "بودكاست مربع",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/yNwQqqU2_tE"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+مربع"
                  ]
            ]
      },
      "السيادة من الأمويين إلى السعوديين | بودكاست دواير": {
            "watchUrl": "https://youtu.be/4uW2QMGl0SQ",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+دواير",
            "category": "مميز",
            "programName": "بودكاست دواير",
            "lead": "بودكاست دواير: الحلقة تقرأ مفهوم السيادة من الدولة الأموية إلى الدولة السعودية، وتربط التاريخ السياسي بتطور فكرة الحكم.",
            "programBrief": "دواير برنامج سردي وتحليلي يتناول التاريخ والسياسة والفكر عبر بناء متدرج للفكرة وربطها بسياقها.",
            "episodeBrief": "الحلقة تقرأ مفهوم السيادة من الدولة الأموية إلى الدولة السعودية، وتربط التاريخ السياسي بتطور فكرة الحكم.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "مميز",
                  "بودكاست دواير",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/4uW2QMGl0SQ"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+دواير"
                  ]
            ]
      },
      "حياة السعوديين الصعبة قبل توحيد البلاد | بودكاست ذا قال": {
            "watchUrl": "https://youtu.be/VV0Qualybqc",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+ذا+قال",
            "category": "أخرى",
            "programName": "بودكاست ذا قال",
            "lead": "بودكاست ذا قال: الحلقة تعود إلى ملامح الحياة الصعبة قبل توحيد البلاد، وتوضح التحول الاجتماعي والمعيشي الذي سبق الدولة الحديثة.",
            "programBrief": "ذا قال برنامج يستعيد موضوعات من التاريخ والذاكرة الاجتماعية بأسلوب سردي قريب من المستمع.",
            "episodeBrief": "الحلقة تعود إلى ملامح الحياة الصعبة قبل توحيد البلاد، وتوضح التحول الاجتماعي والمعيشي الذي سبق الدولة الحديثة.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "أخرى",
                  "بودكاست ذا قال",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/VV0Qualybqc"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+ذا+قال"
                  ]
            ]
      },
      "ذكريات العسكرية وخفايا الصاعقة | بودكاست وضّاح": {
            "watchUrl": "https://youtu.be/ak8haIU3Al4",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+وضّاح",
            "category": "أخرى",
            "programName": "بودكاست وضّاح",
            "lead": "بودكاست وضّاح: الحلقة تجمع ذكريات العسكرية وخفايا الصاعقة، وتقدم التجربة من داخل الانضباط والتدريب والمواقف الميدانية.",
            "programBrief": "وضّاح برنامج حواري يستضيف أصحاب تجارب ميدانية ويترك لهم مساحة لشرح التفاصيل والخلفيات.",
            "episodeBrief": "الحلقة تجمع ذكريات العسكرية وخفايا الصاعقة، وتقدم التجربة من داخل الانضباط والتدريب والمواقف الميدانية.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "أخرى",
                  "بودكاست وضّاح",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/ak8haIU3Al4"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+وضّاح"
                  ]
            ]
      },
      "قصة: معاوية بن أبي سفيان | بودكاست دواير": {
            "watchUrl": "https://youtu.be/7-YB9N4Tkuw",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+دواير",
            "category": "مميز",
            "programName": "بودكاست دواير",
            "lead": "بودكاست دواير: الحلقة تسرد قصة معاوية بن أبي سفيان من زاوية تاريخية، وتعرض التحولات السياسية والشخصية في تلك المرحلة.",
            "programBrief": "دواير برنامج سردي وتحليلي يتناول التاريخ والسياسة والفكر عبر بناء متدرج للفكرة وربطها بسياقها.",
            "episodeBrief": "الحلقة تسرد قصة معاوية بن أبي سفيان من زاوية تاريخية، وتعرض التحولات السياسية والشخصية في تلك المرحلة.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "مميز",
                  "بودكاست دواير",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/7-YB9N4Tkuw"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+دواير"
                  ]
            ]
      },
      "قصص في عالم الجريمة مع معاذ عيد | بودكاست عدد": {
            "watchUrl": "https://youtu.be/w8uWBRe8krs",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+عدد",
            "category": "مميز",
            "programName": "بودكاست عدد",
            "lead": "بودكاست عدد: الحلقة تفتح قصصًا من عالم الجريمة مع معاذ عيد، وتركز على التفاصيل التي تجعل الحكاية مفهومة لا مجرد إثارة.",
            "programBrief": "عدد برنامج يهتم بالموضوع المحدد في كل حلقة، ويقدمه عبر سرد أو حوار يعطي التفاصيل حضورًا واضحًا.",
            "episodeBrief": "الحلقة تفتح قصصًا من عالم الجريمة مع معاذ عيد، وتركز على التفاصيل التي تجعل الحكاية مفهومة لا مجرد إثارة.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "مميز",
                  "بودكاست عدد",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/w8uWBRe8krs"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+عدد"
                  ]
            ]
      },
      "لماذا يُحارب السعودي في القطاع الخاص؟ ومن يحاسب على السعودة الوهمية ؟| مع أ.بدر العنزي | بودكاست نمو": {
            "watchUrl": "https://youtu.be/cyvFRYX_FPo",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+نمو",
            "category": "مميز",
            "programName": "بودكاست نمو",
            "lead": "بودكاست نمو: الحلقة تناقش تحديات السعودي في القطاع الخاص، وتطرح أسئلة عن السعودة الوهمية والمحاسبة وواقع سوق العمل.",
            "programBrief": "نمو برنامج يناقش قضايا العمل والسوق والقطاع الخاص والنمو المهني من خلال ضيوف وتجارب عملية.",
            "episodeBrief": "الحلقة تناقش تحديات السعودي في القطاع الخاص، وتطرح أسئلة عن السعودة الوهمية والمحاسبة وواقع سوق العمل.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "مميز",
                  "بودكاست نمو",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/cyvFRYX_FPo"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+نمو"
                  ]
            ]
      },
      "بودكاست الأول | 9 | من يفتّش النساء في نقاط التفتيش؟": {
            "watchUrl": "https://youtu.be/cbEnUFTEtHw",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+الأول",
            "category": "أخرى",
            "programName": "بودكاست الأول",
            "lead": "بودكاست الأول: الحلقة تطرح سؤال التفتيش في نقاط التفتيش من زاوية اجتماعية وإجرائية، وتفتح نقاشًا حول الممارسة والخصوصية.",
            "programBrief": "بودكاست الأول يقدم موضوعات اجتماعية وميدانية بصيغة حوارية تفتح أسئلة عن الواقع والتجربة.",
            "episodeBrief": "الحلقة تطرح سؤال التفتيش في نقاط التفتيش من زاوية اجتماعية وإجرائية، وتفتح نقاشًا حول الممارسة والخصوصية.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "أخرى",
                  "بودكاست الأول",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/cbEnUFTEtHw"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+الأول"
                  ]
            ]
      },
      "مجهولة أبوين | بودكاست فنجان": {
            "watchUrl": "https://youtu.be/XH7Qv3siYNM",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+فنجان",
            "category": "أخرى",
            "programName": "بودكاست فنجان",
            "lead": "بودكاست فنجان: الحلقة تتناول تجربة إنسانية حساسة بعنوان مجهولة أبوين، وتمنح مساحة لفهم البعد الاجتماعي والنفسي للحكاية.",
            "programBrief": "فنجان برنامج حواري طويل من ثمانية، يفتح مساحة واسعة للضيف حتى يشرح تجربته وفكرته من دون اختصار مخل.",
            "episodeBrief": "الحلقة تتناول تجربة إنسانية حساسة بعنوان مجهولة أبوين، وتمنح مساحة لفهم البعد الاجتماعي والنفسي للحكاية.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "أخرى",
                  "بودكاست فنجان",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/XH7Qv3siYNM"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+فنجان"
                  ]
            ]
      },
      "ظاهرة شباب البومب وفيصل العيسى | بودكاست فنجان": {
            "watchUrl": "https://youtu.be/GMyGyYBBM2M",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+فنجان",
            "category": "مميز",
            "programName": "بودكاست فنجان",
            "lead": "بودكاست فنجان: الحلقة تناقش ظاهرة شباب البومب مع فيصل العيسى، وتقرأ أثر العمل على الجمهور والدراما السعودية الشعبية.",
            "programBrief": "فنجان برنامج حواري طويل من ثمانية، يفتح مساحة واسعة للضيف حتى يشرح تجربته وفكرته من دون اختصار مخل.",
            "episodeBrief": "الحلقة تناقش ظاهرة شباب البومب مع فيصل العيسى، وتقرأ أثر العمل على الجمهور والدراما السعودية الشعبية.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "مميز",
                  "بودكاست فنجان",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/GMyGyYBBM2M"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+فنجان"
                  ]
            ]
      },
      "الثبات النفسي في غوانتانامو | بودكاست روايتهم 036 | فايز الكندري": {
            "watchUrl": "https://youtu.be/rL4lrhoMRVA",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+روايتهم",
            "category": "أخرى",
            "programName": "بودكاست روايتهم",
            "lead": "بودكاست روايتهم: الحلقة تعرض تجربة الثبات النفسي في غوانتانامو مع فايز الكندري، وتروي معنى الصبر داخل ظرف شديد القسوة.",
            "programBrief": "روايتهم برنامج يستند إلى سرد التجارب كما عاشها أصحابها، مع حضور واضح للشهادة الشخصية والتوثيق.",
            "episodeBrief": "الحلقة تعرض تجربة الثبات النفسي في غوانتانامو مع فايز الكندري، وتروي معنى الصبر داخل ظرف شديد القسوة.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "أخرى",
                  "بودكاست روايتهم",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/rL4lrhoMRVA"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+روايتهم"
                  ]
            ]
      },
      "بودكاست يصير خير | لعبة كمال الأجسام خساير وفيها محسوبيات - عبدالله الربيعة": {
            "watchUrl": "https://youtu.be/HlH9NFARWds",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+يصير+خير",
            "category": "الرياضة",
            "programName": "بودكاست يصير خير",
            "lead": "بودكاست يصير خير: الحلقة تناقش عالم كمال الأجسام مع عبدالله الربيعة، وتعرض جوانب الخسائر والمحسوبيات وما يحيط باللعبة.",
            "programBrief": "يصير خير برنامج حواري اجتماعي يقترب من قصص الناس وتجاربهم ويطرحها بلغة مباشرة وقريبة.",
            "episodeBrief": "الحلقة تناقش عالم كمال الأجسام مع عبدالله الربيعة، وتعرض جوانب الخسائر والمحسوبيات وما يحيط باللعبة.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الرياضة",
                  "بودكاست يصير خير",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/HlH9NFARWds"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+يصير+خير"
                  ]
            ]
      },
      "كيف تخسر دهون بالطريقة الصحيحة | بودكاست على البنش": {
            "watchUrl": "https://youtu.be/g-Z8wuJUYBQ",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+على+البنش",
            "category": "الرياضة",
            "programName": "بودكاست على البنش",
            "lead": "بودكاست على البنش: الحلقة تشرح خسارة الدهون بطريقة صحيحة، وتربط التدريب والتغذية بالاستمرارية بدل الحلول السريعة.",
            "programBrief": "على البنش برنامج يهتم باللياقة والتدريب والصحة الجسدية من زاوية عملية يفهمها المتابع.",
            "episodeBrief": "الحلقة تشرح خسارة الدهون بطريقة صحيحة، وتربط التدريب والتغذية بالاستمرارية بدل الحلول السريعة.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الرياضة",
                  "بودكاست على البنش",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/g-Z8wuJUYBQ"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+على+البنش"
                  ]
            ]
      },
      "كيف تلتزم بالنادي وتتمرن بسهولة | بودكاست فنجان": {
            "watchUrl": "https://youtu.be/06ovyUh2iWU",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+فنجان",
            "category": "الرياضة",
            "programName": "بودكاست فنجان",
            "lead": "بودكاست فنجان: الحلقة تتناول الالتزام بالنادي والتمرين بسهولة، وتبحث عن الطريقة التي تجعل الرياضة عادة قابلة للاستمرار.",
            "programBrief": "فنجان برنامج حواري طويل من ثمانية، يفتح مساحة واسعة للضيف حتى يشرح تجربته وفكرته من دون اختصار مخل.",
            "episodeBrief": "الحلقة تتناول الالتزام بالنادي والتمرين بسهولة، وتبحث عن الطريقة التي تجعل الرياضة عادة قابلة للاستمرار.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الرياضة",
                  "بودكاست فنجان",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/06ovyUh2iWU"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+فنجان"
                  ]
            ]
      },
      "آداب ومسائل الدعاء | بودكاست رفوف (67) مع حمد العتيق": {
            "watchUrl": "https://youtu.be/F9IiYZoWBr0",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+رفوف",
            "category": "الإسلامية",
            "programName": "بودكاست رفوف",
            "lead": "بودكاست رفوف: الحلقة تعرض آداب الدعاء ومسائله مع حمد العتيق، وتقدم المعنى الشرعي بأسلوب مرتب وقريب.",
            "programBrief": "رفوف برنامج معرفي يهتم بالموضوعات الشرعية والثقافية ويقدمها في حلقات مرقمة وواضحة.",
            "episodeBrief": "الحلقة تعرض آداب الدعاء ومسائله مع حمد العتيق، وتقدم المعنى الشرعي بأسلوب مرتب وقريب.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الإسلامية",
                  "بودكاست رفوف",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/F9IiYZoWBr0"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+رفوف"
                  ]
            ]
      },
      "القضاء و القدر : بين الإيمان و العمل | د.عبدالرحمن الحرمي": {
            "watchUrl": "https://youtu.be/am6jfmu7E_M",
            "pageUrl": "https://www.youtube.com/results?search_query=محاضرة+مرئية",
            "category": "الإسلامية",
            "programName": "محاضرة مرئية",
            "lead": "محاضرة مرئية: المادة تتناول القضاء والقدر بين الإيمان والعمل، وتشرح كيف يجتمع التسليم مع السعي في حياة المسلم.",
            "programBrief": "هذه مادة مرئية معرفية تتناول موضوعًا إيمانيًا بأسلوب شرح مباشر ومركّز.",
            "episodeBrief": "المادة تتناول القضاء والقدر بين الإيمان والعمل، وتشرح كيف يجتمع التسليم مع السعي في حياة المسلم.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الإسلامية",
                  "محاضرة مرئية",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/am6jfmu7E_M"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=محاضرة+مرئية"
                  ]
            ]
      },
      "حسن الظن بالله… طريق الثبات | بودكاست ثبات (3) مع د. مطلق الجاسر #بودكاست #ثبات": {
            "watchUrl": "https://youtu.be/fihKhSU9_rY",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+ثبات",
            "category": "الإسلامية",
            "programName": "بودكاست ثبات",
            "lead": "بودكاست ثبات: الحلقة تتناول حسن الظن بالله بوصفه طريقًا للثبات، وتربط المعنى الإيماني بسكينة القلب والعمل.",
            "programBrief": "ثبات برنامج ديني وتربوي يعتني بالمعاني الإيمانية التي تساعد على بناء الطمأنينة والاستقامة.",
            "episodeBrief": "الحلقة تتناول حسن الظن بالله بوصفه طريقًا للثبات، وتربط المعنى الإيماني بسكينة القلب والعمل.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الإسلامية",
                  "بودكاست ثبات",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/fihKhSU9_rY"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+ثبات"
                  ]
            ]
      },
      "كيف تبني شركة ريادية بأقل المخاطر | بودكاست سوالف بزنس": {
            "watchUrl": "https://youtu.be/aHU19xgbFM8",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+سوالف+بزنس",
            "category": "الأعمال",
            "programName": "بودكاست سوالف بزنس",
            "lead": "بودكاست سوالف بزنس: الحلقة تناقش بناء شركة ريادية بأقل المخاطر، وتعرض طريقة التفكير قبل التوسع واتخاذ القرارات الكبيرة.",
            "programBrief": "سوالف بزنس برنامج يركز على ريادة الأعمال والشركات والتجارب التجارية بلغة عملية قريبة من السوق.",
            "episodeBrief": "الحلقة تناقش بناء شركة ريادية بأقل المخاطر، وتعرض طريقة التفكير قبل التوسع واتخاذ القرارات الكبيرة.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الأعمال",
                  "بودكاست سوالف بزنس",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/aHU19xgbFM8"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+سوالف+بزنس"
                  ]
            ]
      },
      "دليل النجاح في ريادة الأعمال | بودكاست غلاف": {
            "watchUrl": "https://youtu.be/6oox-CSglWw",
            "pageUrl": "https://www.youtube.com/results?search_query=بودكاست+غلاف",
            "category": "الأعمال",
            "programName": "بودكاست غلاف",
            "lead": "بودكاست غلاف: الحلقة تقدم دليلًا في ريادة الأعمال، وتربط نجاح المشروع بفهم السوق والتجربة والقرارات اليومية.",
            "programBrief": "غلاف برنامج يقدم موضوعات معرفية وتجارية عبر نقاشات تشرح الفكرة والتجربة والنتيجة.",
            "episodeBrief": "الحلقة تقدم دليلًا في ريادة الأعمال، وتربط نجاح المشروع بفهم السوق والتجربة والقرارات اليومية.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الأعمال",
                  "بودكاست غلاف",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/6oox-CSglWw"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=بودكاست+غلاف"
                  ]
            ]
      },
      "كيف تكون تاجر وتنجح بمشروعك الصغير مع عبدالعزيز المطرودي بودكاست خبرة": {
            "watchUrl": "https://youtu.be/yTiQd9Kgsck",
            "pageUrl": "https://www.youtube.com/results?search_query=%D9%83%D9%8A%D9%81%20%D8%AA%D9%83%D9%88%D9%86%20%D8%AA%D8%A7%D8%AC%D8%B1%20%D9%88%D8%AA%D9%86%D8%AC%D8%AD%20%D8%A8%D9%85%D8%B4%D8%B1%D9%88%D8%B9%D9%83%20%D8%A7%D9%84%D8%B5%D8%BA%D9%8A%D8%B1%20%D9%85%D8%B9%20%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B9%D8%B2%D9%8A%D8%B2%20%D8%A7%D9%84%D9%85%D8%B7%D8%B1%D9%88%D8%AF%D9%8A%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%AE%D8%A8%D8%B1%D8%A9",
            "category": "الأعمال",
            "programName": "بودكاست خبرة",
            "lead": "بودكاست خبرة: الحلقة تستضيف عبدالعزيز المطرودي للحديث عن التجارة والمشروع الصغير، وتوضح كيف تبدأ الفكرة وتكبر بخطوات محسوبة.",
            "programBrief": "خبرة برنامج يهتم بتحويل التجارب العملية إلى خطوات مفهومة، ويقرب خبرات الضيوف من المتابع.",
            "episodeBrief": "الحلقة تستضيف عبدالعزيز المطرودي للحديث عن التجارة والمشروع الصغير، وتوضح كيف تبدأ الفكرة وتكبر بخطوات محسوبة.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الأعمال",
                  "بودكاست خبرة",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/yTiQd9Kgsck"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=%D9%83%D9%8A%D9%81%20%D8%AA%D9%83%D9%88%D9%86%20%D8%AA%D8%A7%D8%AC%D8%B1%20%D9%88%D8%AA%D9%86%D8%AC%D8%AD%20%D8%A8%D9%85%D8%B4%D8%B1%D9%88%D8%B9%D9%83%20%D8%A7%D9%84%D8%B5%D8%BA%D9%8A%D8%B1%20%D9%85%D8%B9%20%D8%B9%D8%A8%D8%AF%D8%A7%D9%84%D8%B9%D8%B2%D9%8A%D8%B2%20%D8%A7%D9%84%D9%85%D8%B7%D8%B1%D9%88%D8%AF%D9%8A%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%AE%D8%A8%D8%B1%D8%A9"
                  ]
            ]
      },
      "لماذا تفشل المشاريع الناشئة | بودكاست سوالف بزنس": {
            "watchUrl": "https://youtu.be/PfTqG0vkVqo",
            "pageUrl": "https://www.youtube.com/results?search_query=%D9%84%D9%85%D8%A7%D8%B0%D8%A7%20%D8%AA%D9%81%D8%B4%D9%84%20%D8%A7%D9%84%D9%85%D8%B4%D8%A7%D8%B1%D9%8A%D8%B9%20%D8%A7%D9%84%D9%86%D8%A7%D8%B4%D8%A6%D8%A9%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%B3%D9%88%D8%A7%D9%84%D9%81%20%D8%A8%D8%B2%D9%86%D8%B3",
            "category": "الأعمال",
            "programName": "بودكاست سوالف بزنس",
            "lead": "بودكاست سوالف بزنس: الحلقة تناقش أسباب فشل المشاريع الناشئة، وتقرأ الأخطاء التي تظهر في التخطيط والسوق والفريق والتمويل.",
            "programBrief": "سوالف بزنس برنامج يركز على ريادة الأعمال والشركات والتجارب التجارية بلغة عملية قريبة من السوق.",
            "episodeBrief": "الحلقة تناقش أسباب فشل المشاريع الناشئة، وتقرأ الأخطاء التي تظهر في التخطيط والسوق والفريق والتمويل.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الأعمال",
                  "بودكاست سوالف بزنس",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/PfTqG0vkVqo"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=%D9%84%D9%85%D8%A7%D8%B0%D8%A7%20%D8%AA%D9%81%D8%B4%D9%84%20%D8%A7%D9%84%D9%85%D8%B4%D8%A7%D8%B1%D9%8A%D8%B9%20%D8%A7%D9%84%D9%86%D8%A7%D8%B4%D8%A6%D8%A9%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%B3%D9%88%D8%A7%D9%84%D9%81%20%D8%A8%D8%B2%D9%86%D8%B3"
                  ]
            ]
      },
      "كيف تحصل على وظيفة وتتطوّر مهنيًا | بودكاست فنجان": {
            "watchUrl": "https://youtu.be/QPTwsoa47do",
            "pageUrl": "https://www.youtube.com/results?search_query=%D9%83%D9%8A%D9%81%20%D8%AA%D8%AD%D8%B5%D9%84%20%D8%B9%D9%84%D9%89%20%D9%88%D8%B8%D9%8A%D9%81%D8%A9%20%D9%88%D8%AA%D8%AA%D8%B7%D9%88%D9%91%D8%B1%20%D9%85%D9%87%D9%86%D9%8A%D9%8B%D8%A7%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D9%81%D9%86%D8%AC%D8%A7%D9%86",
            "category": "الأعمال",
            "programName": "بودكاست فنجان",
            "lead": "بودكاست فنجان: الحلقة تركز على الحصول على وظيفة والتطور المهني، وتعرض التفكير المطلوب لبناء مسار عملي أكثر وضوحًا.",
            "programBrief": "فنجان برنامج حواري طويل من ثمانية، يفتح مساحة واسعة للضيف حتى يشرح تجربته وفكرته من دون اختصار مخل.",
            "episodeBrief": "الحلقة تركز على الحصول على وظيفة والتطور المهني، وتعرض التفكير المطلوب لبناء مسار عملي أكثر وضوحًا.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الأعمال",
                  "بودكاست فنجان",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/QPTwsoa47do"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=%D9%83%D9%8A%D9%81%20%D8%AA%D8%AD%D8%B5%D9%84%20%D8%B9%D9%84%D9%89%20%D9%88%D8%B8%D9%8A%D9%81%D8%A9%20%D9%88%D8%AA%D8%AA%D8%B7%D9%88%D9%91%D8%B1%20%D9%85%D9%87%D9%86%D9%8A%D9%8B%D8%A7%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D9%81%D9%86%D8%AC%D8%A7%D9%86"
                  ]
            ]
      },
      "النصر يخسر نهائي آسيا 2 والهلال يؤجل حسم الدوري | بودكاست مرتدة": {
            "watchUrl": "https://youtu.be/lVYybG7u8RQ",
            "pageUrl": "https://www.youtube.com/results?search_query=%D8%A7%D9%84%D9%86%D8%B5%D8%B1%20%D9%8A%D8%AE%D8%B3%D8%B1%20%D9%86%D9%87%D8%A7%D8%A6%D9%8A%20%D8%A2%D8%B3%D9%8A%D8%A7%202%20%D9%88%D8%A7%D9%84%D9%87%D9%84%D8%A7%D9%84%20%D9%8A%D8%A4%D8%AC%D9%84%20%D8%AD%D8%B3%D9%85%20%D8%A7%D9%84%D8%AF%D9%88%D8%B1%D9%8A%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D9%85%D8%B1%D8%AA%D8%AF%D8%A9",
            "category": "الرياضة",
            "programName": "بودكاست مرتدة",
            "lead": "بودكاست مرتدة: الحلقة الرياضية تقرأ خسارة النصر نهائي آسيا 2 وتأجيل الهلال لحسم الدوري، وتربط النتيجة بسياق المنافسة السعودية.",
            "programBrief": "مرتدة برنامج رياضي يتابع مباريات كرة القدم السعودية وتحولاتها بلغة تحليلية مرتبطة بالمشهد الحالي.",
            "episodeBrief": "الحلقة الرياضية تقرأ خسارة النصر نهائي آسيا 2 وتأجيل الهلال لحسم الدوري، وتربط النتيجة بسياق المنافسة السعودية.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الرياضة",
                  "بودكاست مرتدة",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/lVYybG7u8RQ"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=%D8%A7%D9%84%D9%86%D8%B5%D8%B1%20%D9%8A%D8%AE%D8%B3%D8%B1%20%D9%86%D9%87%D8%A7%D8%A6%D9%8A%20%D8%A2%D8%B3%D9%8A%D8%A7%202%20%D9%88%D8%A7%D9%84%D9%87%D9%84%D8%A7%D9%84%20%D9%8A%D8%A4%D8%AC%D9%84%20%D8%AD%D8%B3%D9%85%20%D8%A7%D9%84%D8%AF%D9%88%D8%B1%D9%8A%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D9%85%D8%B1%D8%AA%D8%AF%D8%A9"
                  ]
            ]
      },
      "النصر يعود لصدارة دوري روشن | بودكاست شوط": {
            "watchUrl": "https://youtu.be/ActJ1Hl_Wio",
            "pageUrl": "https://www.youtube.com/results?search_query=%D8%A7%D9%84%D9%86%D8%B5%D8%B1%20%D9%8A%D8%B9%D9%88%D8%AF%20%D9%84%D8%B5%D8%AF%D8%A7%D8%B1%D8%A9%20%D8%AF%D9%88%D8%B1%D9%8A%20%D8%B1%D9%88%D8%B4%D9%86%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%B4%D9%88%D8%B7",
            "category": "الرياضة",
            "programName": "بودكاست شوط",
            "lead": "بودكاست شوط: الحلقة تتابع عودة النصر لصدارة دوري روشن، وتناقش أثر النتائج على سباق الدوري وترتيب المنافسين.",
            "programBrief": "شوط برنامج رياضي يقرأ أحداث دوري روشن والأندية السعودية عبر نقاشات قصيرة ومباشرة.",
            "episodeBrief": "الحلقة تتابع عودة النصر لصدارة دوري روشن، وتناقش أثر النتائج على سباق الدوري وترتيب المنافسين.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الرياضة",
                  "بودكاست شوط",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/ActJ1Hl_Wio"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=%D8%A7%D9%84%D9%86%D8%B5%D8%B1%20%D9%8A%D8%B9%D9%88%D8%AF%20%D9%84%D8%B5%D8%AF%D8%A7%D8%B1%D8%A9%20%D8%AF%D9%88%D8%B1%D9%8A%20%D8%B1%D9%88%D8%B4%D9%86%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%B4%D9%88%D8%B7"
                  ]
            ]
      },
      "استقطاب النجوم وعدالة المنافسة مع وزير الرياضة | بودكاست سقراط": {
            "watchUrl": "https://youtu.be/6t6b15DCGT0",
            "pageUrl": "https://www.youtube.com/results?search_query=%D8%A7%D8%B3%D8%AA%D9%82%D8%B7%D8%A7%D8%A8%20%D8%A7%D9%84%D9%86%D8%AC%D9%88%D9%85%20%D9%88%D8%B9%D8%AF%D8%A7%D9%84%D8%A9%20%D8%A7%D9%84%D9%85%D9%86%D8%A7%D9%81%D8%B3%D8%A9%20%D9%85%D8%B9%20%D9%88%D8%B2%D9%8A%D8%B1%20%D8%A7%D9%84%D8%B1%D9%8A%D8%A7%D8%B6%D8%A9%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%B3%D9%82%D8%B1%D8%A7%D8%B7",
            "category": "الرياضة",
            "programName": "بودكاست سقراط",
            "lead": "بودكاست سقراط: الحلقة تستضيف وزير الرياضة للحديث عن استقطاب النجوم وعدالة المنافسة، وتعرض النقاش من زاوية تطوير الرياضة السعودية.",
            "programBrief": "سقراط برنامج من ثمانية يركز على الملفات العامة والتحولات السعودية عبر حوارات مباشرة مع مسؤولين ومختصين.",
            "episodeBrief": "الحلقة تستضيف وزير الرياضة للحديث عن استقطاب النجوم وعدالة المنافسة، وتعرض النقاش من زاوية تطوير الرياضة السعودية.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الرياضة",
                  "بودكاست سقراط",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/6t6b15DCGT0"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=%D8%A7%D8%B3%D8%AA%D9%82%D8%B7%D8%A7%D8%A8%20%D8%A7%D9%84%D9%86%D8%AC%D9%88%D9%85%20%D9%88%D8%B9%D8%AF%D8%A7%D9%84%D8%A9%20%D8%A7%D9%84%D9%85%D9%86%D8%A7%D9%81%D8%B3%D8%A9%20%D9%85%D8%B9%20%D9%88%D8%B2%D9%8A%D8%B1%20%D8%A7%D9%84%D8%B1%D9%8A%D8%A7%D8%B6%D8%A9%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%B3%D9%82%D8%B1%D8%A7%D8%B7"
                  ]
            ]
      },
      "كيف يمكن فهمك للقرآن أن يغيّر حياتك بالكامل؟ | د. نايف بن نهار | بودكاست بدون ورق": {
            "watchUrl": "https://youtu.be/Pfj4niPP0DY",
            "pageUrl": "https://www.youtube.com/results?search_query=%D9%83%D9%8A%D9%81%20%D9%8A%D9%85%D9%83%D9%86%20%D9%81%D9%87%D9%85%D9%83%20%D9%84%D9%84%D9%82%D8%B1%D8%A2%D9%86%20%D8%A3%D9%86%20%D9%8A%D8%BA%D9%8A%D9%91%D8%B1%20%D8%AD%D9%8A%D8%A7%D8%AA%D9%83%20%D8%A8%D8%A7%D9%84%D9%83%D8%A7%D9%85%D9%84%D8%9F%20%7C%20%D8%AF.%20%D9%86%D8%A7%D9%8A%D9%81%20%D8%A8%D9%86%20%D9%86%D9%87%D8%A7%D8%B1%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%A8%D8%AF%D9%88%D9%86%20%D9%88%D8%B1%D9%82",
            "category": "الإسلامية",
            "programName": "بودكاست بدون ورق",
            "lead": "بودكاست بدون ورق: الحلقة مع د. نايف بن نهار تناقش كيف يغيّر فهم القرآن حياة الإنسان، وتربط المعرفة بالعمل اليومي.",
            "programBrief": "بدون ورق برنامج حواري معرفي يطرح أسئلة فكرية ودينية واجتماعية مع ضيوف متخصصين.",
            "episodeBrief": "الحلقة مع د. نايف بن نهار تناقش كيف يغيّر فهم القرآن حياة الإنسان، وتربط المعرفة بالعمل اليومي.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الإسلامية",
                  "بودكاست بدون ورق",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/Pfj4niPP0DY"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=%D9%83%D9%8A%D9%81%20%D9%8A%D9%85%D9%83%D9%86%20%D9%81%D9%87%D9%85%D9%83%20%D9%84%D9%84%D9%82%D8%B1%D8%A2%D9%86%20%D8%A3%D9%86%20%D9%8A%D8%BA%D9%8A%D9%91%D8%B1%20%D8%AD%D9%8A%D8%A7%D8%AA%D9%83%20%D8%A8%D8%A7%D9%84%D9%83%D8%A7%D9%85%D9%84%D8%9F%20%7C%20%D8%AF.%20%D9%86%D8%A7%D9%8A%D9%81%20%D8%A8%D9%86%20%D9%86%D9%87%D8%A7%D8%B1%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%A8%D8%AF%D9%88%D9%86%20%D9%88%D8%B1%D9%82"
                  ]
            ]
      },
      "إعادة اكتشاف الصلاة | بودكاست فنجان": {
            "watchUrl": "https://youtu.be/Zy_vOjKjcWA",
            "pageUrl": "https://www.youtube.com/results?search_query=%D8%A5%D8%B9%D8%A7%D8%AF%D8%A9%20%D8%A7%D9%83%D8%AA%D8%B4%D8%A7%D9%81%20%D8%A7%D9%84%D8%B5%D9%84%D8%A7%D8%A9%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D9%81%D9%86%D8%AC%D8%A7%D9%86",
            "category": "الإسلامية",
            "programName": "بودكاست فنجان",
            "lead": "بودكاست فنجان: الحلقة تعيد النظر في معنى الصلاة، وتعرضها بوصفها عبادة مركزية تتصل بالسكينة والانضباط والحضور.",
            "programBrief": "فنجان برنامج حواري طويل من ثمانية، يفتح مساحة واسعة للضيف حتى يشرح تجربته وفكرته من دون اختصار مخل.",
            "episodeBrief": "الحلقة تعيد النظر في معنى الصلاة، وتعرضها بوصفها عبادة مركزية تتصل بالسكينة والانضباط والحضور.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الإسلامية",
                  "بودكاست فنجان",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/Zy_vOjKjcWA"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=%D8%A5%D8%B9%D8%A7%D8%AF%D8%A9%20%D8%A7%D9%83%D8%AA%D8%B4%D8%A7%D9%81%20%D8%A7%D9%84%D8%B5%D9%84%D8%A7%D8%A9%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D9%81%D9%86%D8%AC%D8%A7%D9%86"
                  ]
            ]
      },
      "حين يتحول الدعاء إلى يقين | بودكاست أروقة": {
            "watchUrl": "https://youtu.be/UmoXguPAsAs",
            "pageUrl": "https://www.youtube.com/results?search_query=%D8%AD%D9%8A%D9%86%20%D9%8A%D8%AA%D8%AD%D9%88%D9%84%20%D8%A7%D9%84%D8%AF%D8%B9%D8%A7%D8%A1%20%D8%A5%D9%84%D9%89%20%D9%8A%D9%82%D9%8A%D9%86%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%A3%D8%B1%D9%88%D9%82%D8%A9",
            "category": "الإسلامية",
            "programName": "بودكاست أروقة",
            "lead": "بودكاست أروقة: الحلقة تتناول الدعاء عندما يتحول إلى يقين، وتوضح علاقة التوكل والانتظار والثقة بالله.",
            "programBrief": "أروقة برنامج يفتح موضوعات دينية وتربوية بأسلوب هادئ يربط الفكرة بحياة المستمع اليومية.",
            "episodeBrief": "الحلقة تتناول الدعاء عندما يتحول إلى يقين، وتوضح علاقة التوكل والانتظار والثقة بالله.",
            "more": [
                  "تفتح الحلقة مساحة أوسع لفهم موضوعها من خلال عنوانها وضيفها ومحورها الرئيسي، وتمنح المتابع صورة مرتبة عن الفكرة قبل الانتقال إلى المشاهدة الكاملة.",
                  "يمكن الوصول إلى الحلقة مباشرة من زر المشاهدة، وتبقى الصورة المصغرة مأخوذة من الفيديو نفسه."
            ],
            "tags": [
                  "الإسلامية",
                  "بودكاست أروقة",
                  "بودكاست"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/UmoXguPAsAs"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=%D8%AD%D9%8A%D9%86%20%D9%8A%D8%AA%D8%AD%D9%88%D9%84%20%D8%A7%D9%84%D8%AF%D8%B9%D8%A7%D8%A1%20%D8%A5%D9%84%D9%89%20%D9%8A%D9%82%D9%8A%D9%86%20%7C%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%A3%D8%B1%D9%88%D9%82%D8%A9"
                  ]
            ]
      },
      "لماذا الوظيفة هي أسرع طريق نحو الثراء؟ | من بودكاست غلاف": {
            "watchUrl": "https://youtu.be/Brs2qH4Te0M",
            "pageUrl": "https://www.youtube.com/results?search_query=%D9%84%D9%85%D8%A7%D8%B0%D8%A7%20%D8%A7%D9%84%D9%88%D8%B8%D9%8A%D9%81%D8%A9%20%D9%87%D9%8A%20%D8%A3%D8%B3%D8%B1%D8%B9%20%D8%B7%D8%B1%D9%8A%D9%82%20%D9%86%D8%AD%D9%88%20%D8%A7%D9%84%D8%AB%D8%B1%D8%A7%D8%A1%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%BA%D9%84%D8%A7%D9%81",
            "category": "الأعمال",
            "programName": "بودكاست غلاف",
            "lead": "بودكاست غلاف يطرح في هذه الحلقة سؤال العلاقة بين الوظيفة وبناء الثروة، ويناقش كيف يمكن للدخل المنتظم أن يكون بداية عملية للاستقرار المالي والنمو.",
            "programBrief": "غلاف برنامج معرفي وتجاري يشرح الأفكار الاقتصادية وريادة الأعمال والاختيارات المهنية بلغة حوارية قريبة من الواقع.",
            "episodeBrief": "الحلقة تتناول فكرة أن الوظيفة قد تكون طريقًا سريعًا نحو الثراء عندما تُدار بوعي مالي، من خلال الانضباط في الدخل، وبناء المهارات، واختيار الفرص المناسبة بدل النظر للوظيفة كقيد دائم.",
            "more": [
                  "يفتح النقاش زاوية مختلفة عن الصورة الشائعة للثراء، فيربط بين الراتب والاستثمار والتعلم وتوسيع الخيارات بدل الاكتفاء بفكرة الدخل الشهري فقط.",
                  "وتساعد الحلقة على النظر للمسار المهني كمنصة بداية يمكن أن تقود إلى فرص مالية أوسع عند استخدامها بطريقة منظمة."
            ],
            "tags": [
                  "الأعمال",
                  "بودكاست غلاف",
                  "وظيفة"
            ],
            "sources": [
                  [
                        "رابط الحلقة على يوتيوب",
                        "https://youtu.be/Brs2qH4Te0M"
                  ],
                  [
                        "صفحة البرنامج أو البحث عنه على يوتيوب",
                        "https://www.youtube.com/results?search_query=%D9%84%D9%85%D8%A7%D8%B0%D8%A7%20%D8%A7%D9%84%D9%88%D8%B8%D9%8A%D9%81%D8%A9%20%D9%87%D9%8A%20%D8%A3%D8%B3%D8%B1%D8%B9%20%D8%B7%D8%B1%D9%8A%D9%82%20%D9%86%D8%AD%D9%88%20%D8%A7%D9%84%D8%AB%D8%B1%D8%A7%D8%A1%20%D8%A8%D9%88%D8%AF%D9%83%D8%A7%D8%B3%D8%AA%20%D8%BA%D9%84%D8%A7%D9%81"
                  ]
            ]
      }
};

    const PROGRAM_FILTERS = [
      { key:'all', label:'الكل' },
      { key:'مميز', label:'مميز' },
      { key:'الأعمال', label:'الأعمال' },
      { key:'الرياضة', label:'الرياضة' },
      { key:'الإسلامية', label:'الإسلامية' },
      { key:'أخرى', label:'أخرى' }
    ];

    function makeItem(section, entry, idx){
      const topic = String(entry.title || '').replace(/^(خبر|تقرير|مقال|تحقيق):\s*/,'').trim();
      let src = (entry.src && !/^(REPLACE_ME|ضع_هنى_رابط_الصورة|ضع_هنا_رابط_الصورة|\s*)$/u.test(String(entry.src).trim())) ? String(entry.src).trim() : realImage(section, entry.title, idx, 0);
      const gallery = [realImage(section, entry.title, idx, 0), realImage(section, entry.title, idx, 1), realImage(section, entry.title, idx, 2)];
      let lead = '';
      let body = [];
      let more = [];
      let tags = [];
      let sources = [];
      let watchUrl = '';
      let watchTitle = '';

      if (section !== 'programs' && (entry.lead || entry.body || entry.more)) {
        lead = entry.lead || topic;
        body = entry.body || [];
        more = entry.more || [];
        tags = entry.tags || [section === 'articles' ? 'مقال' : section === 'investigations' ? 'تحقيق' : section === 'reports' ? 'تقرير' : 'خبر'];
        sources = entry.sources || [];
      } else if (section === 'programs') {
        const media = PROGRAM_VIDEO_MAP[topic] || {
          watchUrl: entry.url || '#',
          pageUrl: entry.pageUrl || ('https://www.youtube.com/results?search_query=' + encodeURIComponent(topic)),
          category: 'أخرى',
          programName: 'برنامج بودكاست',
          lead: topic,
          programBrief: 'نبذة البرنامج مرتبطة بعنوان الحلقة ومصدرها المرئي.',
          episodeBrief: topic,
          more: [topic],
          tags: ['أخرى', 'بودكاست'],
          sources: [['رابط الحلقة على يوتيوب', entry.url || '#'], ['صفحة البرنامج أو نتائج البرنامج على يوتيوب', entry.pageUrl || ('https://www.youtube.com/results?search_query=' + encodeURIComponent(topic))]]
        };

        watchUrl = media.watchUrl;
        watchTitle = topic;
        lead = media.lead;
        body = [
          `<strong>نبذة عن البرنامج:</strong> ${media.programBrief}`,
          `<strong>نبذة عن الحلقة:</strong> ${media.episodeBrief}`
        ];
        more = media.more || [];
        tags = media.tags || [media.category || 'أخرى', 'بودكاست'];
        sources = media.sources || [['رابط الحلقة على يوتيوب', watchUrl], ['صفحة البرنامج أو نتائج البرنامج على يوتيوب', media.pageUrl]];
      } else if (section === 'articles') {
        lead = `${topic} مادة تحريرية مستقلة تشرح عنوانها مباشرة دون تكرار أو خروج عن مساره.`;
        body = [
          `تبدأ الفكرة من ${topic}، ثم تنتقل إلى أثرها على طريقة عرض المحتوى وفهم الجمهور له.`,
          `تعتمد الصياغة على لغة مباشرة ومرتبة، بحيث تمنح القارئ خلفية مفهومة وتبقي الموضوع في مساره.`,
          `الصورة هنا تعمل كمدخل بصري للموضوع، وتساعد على تمييزه دون تغيير معناه.`
        ];
        more = [
          `تتوسع القراءة في ${topic} من زاوية أوضح، مع الحفاظ على نفس العنوان ونفس السياق.`,
          `القراءة الإضافية لا تنقل القارئ إلى موضوع آخر، بل تكمل الفقرة الأولى وتدعمها بتفسير أهدأ.`,
          `وبذلك يظهر المقال مستقلًا بعنوانه وصورته ونبرته الخاصة.`
        ];
        tags = ['مقال', 'تحليل', 'لغة'];
        sources = [['Apple Podcasts', 'https://podcasts.apple.com/'], ['YouTube', 'https://www.youtube.com/']];
      } else if (section === 'investigations') {
        lead = `${topic} يفتح سؤالًا محددًا ويقدم شواهده داخل نفس الموضوع دون انتقال إلى عناوين أخرى.`;
        body = [
          `في ${topic} لا تكفي الجملة السريعة؛ لذلك يشرح التحقيق السبب والسياق والأثر بطريقة منظمة.`,
          `ويحاول النص ربط التفاصيل ببعضها حتى تظهر الصورة كاملة أمام القارئ دون مبالغة أو تشتيت.`,
          `الصورة المصاحبة تحفظ هوية التحقيق وتجعله واضحًا داخل القسم.`
        ];
        more = [
          `تتسع القراءة في ${topic}، تتضح العلاقة بين المعلومة والسياق والنتيجة التي يريد التحقيق الوصول إليها.`,
          `ويظهر الفرق بين عرض سريع للعنوان وقراءة أوسع تفهم لماذا صار الموضوع مهمًا.`,
          `وتبقى الصياغة متزنة حتى تخدم الفكرة ولا تطغى عليها.`
        ];
        tags = ['تحقيق', 'سياق', 'تحليل'];
        sources = [['وزارة الإعلام', 'https://www.medi.gov.sa/'], ['الهيئة العامة لتنظيم الإعلام', 'https://gcam.gov.sa/']];
      } else if (section === 'reports') {
        lead = `${topic} يرصد مسار الموضوع من بدايته إلى أثره بطريقة مرتبة ومتصلة.`;
        body = [
          `يعرض التقرير ${topic} في فقرات قصيرة ومترابطة، مع لغة رسمية لا تخرج عن محوره.`,
          `وتأتي الصورة بوصفها جزءًا من الرسالة البصرية للموضوع، لا مجرد إضافة شكلية.`,
          `لذلك يبقى النص واضحًا في القراءة السريعة، ويزداد تفصيلًا عند فتح المزيد.`
        ];
        more = [
          `يكمل التقرير شرح ${topic} من دون تكرار أو خروج عن الفكرة.`,
          `النص الإضافي يضيف طبقة أخرى للموضوع، ويمنحه قيمة أوضح داخل القسم.`,
          `وبذلك يحتفظ كل تقرير بعنوانه وصورته وقصته الخاصة.`
        ];
        tags = ['تقرير', 'استماع', 'سعودي'];
        sources = [['Apple Podcasts', 'https://podcasts.apple.com/'], ['Spotify', 'https://open.spotify.com/']];
      } else {
        lead = `يرصد ${topic} في المشهد السعودي بلغة تحريرية رسمية بعيدة عن العامية والتكرار.`;
        body = [
          `يتقدم ${topic} بوصفه موضوعًا ذا صلة مباشرة بالبنية الصوتية والإعلامية السعودية، مع صورة تناسبه.`,
          `تفتح الفقرات الأولى السياق من دون تكرار العنوان، وتقدم المعنى بسرعة ووضوح.`,
          `وتمنحك المساحة نصًا واضحًا يمكن قراءته بسرعة أو فتحه بالتفصيل دون أن يفقد هويته.`
        ];
        more = [
          `وعندما تتوسع القراءة في ${topic} نرى كيف تتقاطع المنصة والجمهور والصياغة والهوية البصرية في مشهد سعودي واحد.`,
          ` من أي مادة أخرى؛ فهو مبني على عنوانه الخاص وصورته الخاصة وتفسيره الخاص.`,
          `، ويشعر القارئ أن كل عنصر يروي شيئًا جديدًا بالفعل.`
        ];
        tags = ['خبر', 'سعودي', 'صوت'];
        sources = [['وكالة الأنباء السعودية', 'https://www.spa.gov.sa/'], ['وزارة الإعلام', 'https://www.medi.gov.sa/']];
      }

      return { id: `${section}-${idx+1}-${hashCode(topic)}`, section, title: entry.title, src, lead, body, more, tags, sources, gallery, watchUrl, watchTitle, category: section === 'programs' ? ((PROGRAM_VIDEO_MAP[topic] && PROGRAM_VIDEO_MAP[topic].category) || 'أخرى') : '' };
    }

function buildItems(section){ return IMAGE_MANIFEST[section].map((entry, idx) => makeItem(section, entry, idx)); }


    const ITEMS = {
      programs: buildItems('programs'),
      articles: buildItems('articles'),
      investigations: buildItems('investigations'),
      reports: buildItems('reports'),
      news: buildItems('news')
    };

    const ALL_ITEMS = [...ITEMS.programs, ...ITEMS.articles, ...ITEMS.investigations, ...ITEMS.reports, ...ITEMS.news];

    function sectionImage(section, item, idx){ return item.src || realImage(section, item.title, idx, 0); }

    function renderCards(container, items, section, buttonText='اقرأ التفاصيل') {
      container.innerHTML = items.map((item, idx) => `
        <article class="card rounded-[2rem] overflow-hidden card-hover soft bg-white section-box">
          <div class="image-frame"><img src="${sectionImage(section, item, idx)}" alt="${item.title}"></div>
          <div class="p-6">
            <div class="flex flex-wrap items-center gap-2 mb-4">
              <span class="chip px-3 py-1 rounded-full text-sm font-black">${section === 'programs' ? 'برنامج' : section === 'articles' ? 'مقال' : section === 'investigations' ? 'تحقيق' : section === 'reports' ? 'تقرير' : 'خبر'}</span>
              <span class="text-sm text-[var(--olive)] font-bold">${item.title.replace(/^(خبر|تقرير|مقال|تحقيق):\s*/, '')}</span>
            </div>
            <h3 class="display-font text-2xl font-black text-[var(--brown)] leading-tight">${item.title}</h3>
            <p class="mt-4 leading-8 text-[var(--text)]">${item.lead}</p>
            <button type="button" class="mt-5 bg-[var(--olive)] text-white px-5 py-3 rounded-2xl font-black hover:scale-[1.03] soft" data-open="${item.id}">${buttonText}</button>
          </div>
        </article>
      `).join('');
    }

    function sortPrograms(list){
      return [...list].sort((a, b) => a.title.localeCompare(b.title, 'ar'));
    }

    function renderProgramSearch(){
      const q = state.programQuery.trim().toLowerCase();
      const active = state.programFilter || 'all';
      $('#programFilterBar').innerHTML = PROGRAM_FILTERS.map(f => `
        <button type="button" class="px-4 py-2 rounded-full border ${active === f.key ? 'bg-[var(--brown)] text-white border-[var(--brown)]' : 'bg-white text-[var(--brown)] border-black/10'} font-bold soft" data-program-filter="${f.key}">${f.label}</button>
      `).join('');
      let items = ITEMS.programs.filter(p => active === 'all' || p.category === active);
      items = sortPrograms(items).filter(p => !q || p.title.toLowerCase().includes(q) || p.lead.toLowerCase().includes(q) || (p.category || '').toLowerCase().includes(q));
      renderCards($('#programGrid'), items, 'programs', 'اقرأ التفاصيل');
    }

    function renderReferences(){
      const staticRefs = [
        ['وزارة الإعلام السعودية','الموقع الرسمي لوزارة الإعلام','مرجع مؤسسي','https://www.medi.gov.sa/'],
        ['الهيئة العامة لتنظيم الإعلام','الجهة المنظمة للمحتوى الإعلامي','مرجع تنظيمي','https://gcam.gov.sa/'],
        ['منصة رؤية السعودية 2030','المرجع الوطني للتحول','مرجع رسمي','https://www.vision2030.gov.sa/'],
        ['وكالة الأنباء السعودية','مستودع الأخبار والصور الوطنية','مرجع خبري','https://www.spa.gov.sa/'],
        ['YouTube','مصدر مشاهدة الحلقات المرئية','مرجع مرئي','https://www.youtube.com/']
      ];
      const programRefs = ITEMS.programs.flatMap(item => (item.sources || []).map(src => [item.title, src[0], 'مصدر برنامج', src[1]]));
      const allRefs = [...staticRefs, ...programRefs];
      $('#referencesGrid').innerHTML = `
        <div class="card rounded-[1.5rem] p-5">
          <div class="text-sm text-[var(--olive)] font-bold mb-3">المراجع</div>
          <p class="leading-8">تضم هذه الصفحة المراجع العامة ومصادر البرامج، ومنها روابط الحلقات وصفحات البرامج على YouTube.</p>
        </div>
        ${allRefs.map((r,i)=>`
          <div class="card rounded-[1.5rem] p-5">
            <div class="flex gap-4">
              <div class="mt-1 text-[var(--brown)] text-2xl leading-none">${i+1}.</div>
              <div class="min-w-0">
                <p class="text-lg md:text-xl leading-9 font-medium text-[var(--text)]">${r[0]} — ${r[1]}. (${r[2]}).</p>
                <p class="mt-3 text-sm"><span class="text-[var(--olive)] font-bold">رابط الاسترجاع من:</span><br><a class="ref-link" href="${r[3]}" target="_blank" rel="noopener noreferrer">${r[3]}</a></p>
              </div>
            </div>
          </div>`).join('')}
      `;
    }

    function setPage(page){
      $$('.page').forEach(p => p.classList.remove('active'));
      $('#page-' + page).classList.add('active');
      state.previous = state.page;
      state.page = page;
      $$('.nav-btn').forEach(btn => btn.classList.remove('nav-active'));
      const active = $(`.nav-btn[data-page="${page}"]`);
      if (active) active.classList.add('nav-active');
      window.scrollTo({ top:0, behavior:'smooth' });
      if (page === 'programs') renderProgramSearch();
      if (page === 'references') renderReferences();
    }

    function openItem(id){
      const item = ALL_ITEMS.find(x => x.id === id);
      if (!item) return;
      state.current = item;
      $('#detailModal').classList.remove('hidden', 'overlay-hidden');
      $('#detailModal').classList.add('overlay-visible');
      document.body.style.overflow = 'hidden';
      $('#detailKicker').textContent = item.section === 'programs' ? 'برنامج' : item.section === 'articles' ? 'مقال' : item.section === 'investigations' ? 'تحقيق' : item.section === 'reports' ? 'تقرير' : 'خبر';
      $('#detailTitle').textContent = item.title;
      $('#detailImage').src = item.src;
      $('#detailLabel').textContent = item.section === 'programs' ? 'برنامج' : item.section === 'articles' ? 'مقال' : item.section === 'investigations' ? 'تحقيق' : item.section === 'reports' ? 'تقرير' : 'خبر';
      $('#detailMeta').textContent = item.title.replace(/^(خبر|تقرير|مقال|تحقيق):\s*/, '');
      $('#detailType').textContent = item.section === 'programs' ? 'برنامج مرئي/صوتي' : item.section === 'articles' ? 'مقال ثقافي' : item.section === 'investigations' ? 'تحقيق صحفي/تحليلي' : item.section === 'reports' ? 'تقرير تحليلي' : 'خبر صحفي';
      $('#detailLead').textContent = item.lead;
      $('#detailBody').innerHTML = item.body.filter(p => String(p).trim()).map(p => `<p>${p}</p>`).join('');
      $('#detailTags').innerHTML = item.tags.map(t => `<span class="chip px-3 py-1 rounded-full text-sm font-bold">${t}</span>`).join('');
      const watchArea = $('#detailWatchArea');
      const sourcesBox = $('#detailSources');

      if (item.section === 'programs') {
        const watchUrl = item.watchUrl || (item.sources && item.sources[0] && item.sources[0][1]) || '#';
        watchArea.classList.remove('hidden');
        watchArea.innerHTML = `
          <a href="${watchUrl}" target="_blank" rel="noopener noreferrer" class="inline-flex items-center justify-center px-6 py-4 rounded-2xl bg-[var(--brown)] text-white font-black shadow-lg soft hover:scale-[1.02]">مشاهدة الحلقة على يوتيوب</a>
        `;
        sourcesBox.classList.add('hidden');
        sourcesBox.innerHTML = '';
      } else {
        watchArea.classList.add('hidden');
        watchArea.innerHTML = '';
        sourcesBox.classList.add('hidden');
        sourcesBox.innerHTML = '';
      }

      if (item.more && item.more.length) { $('#moreBtn').classList.remove('hidden'); } else { $('#moreBtn').classList.add('hidden'); }
      $('#moreBox').classList.add('hidden');
      $('#moreBody').innerHTML = '';
    }

    function showMore(){
      if (!state.current) return;
      const item = state.current;
      const full = [...item.body, ...item.more];
      $('#detailBody').innerHTML = full.filter(p => String(p).trim()).map(p => `<p>${p}</p>`).join('');
      $('#moreBtn').classList.add('hidden');
      $('#moreBox').classList.add('hidden');
      $('#moreBody').innerHTML = full.filter(p => String(p).trim()).map(p => `<p>${p}</p>`).join('');
    }

    function closeDetail(){
      const modal = $('#detailModal');
      modal.classList.add('overlay-hidden');
      modal.classList.remove('overlay-visible');
      setTimeout(() => modal.classList.add('hidden'), 180);
      document.body.style.overflow = '';
    }

    function openDev(){
      const m = $('#devModal');
      m.classList.remove('hidden', 'overlay-hidden');
      m.classList.add('overlay-visible');
      document.body.style.overflow = 'hidden';
    }

    function closeDev(){
      const m = $('#devModal');
      m.classList.add('overlay-hidden');
      m.classList.remove('overlay-visible');
      setTimeout(() => m.classList.add('hidden'), 180);
      document.body.style.overflow = '';
    }

    function setMood(mood){
      $('#currentMood').textContent = mood;
      $('#moodRecommendation').innerHTML = `<div class="display-font text-xl font-black text-[var(--brown)] mb-2">${mood}</div><p class="leading-8">${moods[mood]}</p>`;
      toast(`تم اختيار مود ${mood}`);
    }

    function updateHours(v){ $('#hoursValue').textContent = `${v} ساعة`; }
    function nextQuote(){ state.quoteIndex = (state.quoteIndex + 1) % quotes.length; $('#quoteBox').textContent = quotes[state.quoteIndex]; }
    function quiz(key){
      const map = {
        fanjan:'أنت تميل إلى الحوار العميق والأسئلة التي تفتح المعنى خطوة خطوة.',
        jinaya:'أنت تفضّل الإيقاع المشوق الذي يبني التوتر ثم يكشفه بهدوء.',
        kanbat:'أنت تحب المساحة الهادئة التي تسمح للفكرة أن تتنفس.',
        abjora:'أنت تفضّل المحتوى الذي يوازن بين الفائدة والتنظيم والوضوح.'
      };
      $('#quizResult').textContent = map[key];
    }
    function recommend(){
      const item = recommendations[Math.floor(Math.random() * recommendations.length)];
      $('#recommendBox').classList.remove('hidden');
      $('#recommendTitle').textContent = item.title;
      $('#recommendText').textContent = item.text;
    }
    function syncVotes(){
      localStorage.setItem('mulham_votes_v32', JSON.stringify(state.votes));
      $('#voteFanjan').textContent = state.votes.fanjan;
      $('#voteJinaya').textContent = state.votes.jinaya;
      $('#voteMosho').textContent = state.votes.mosho;
      $('#voteSardyat').textContent = state.votes.sardyat;
    }
    function voteOnce(){
      if (state.voted){ toast('تم التصويت من هذا المتصفح مسبقًا'); return; }
      state.votes.fanjan += 1;
      state.voted = true;
      localStorage.setItem('mulham_voted_once_v4', '1');
      syncVotes();
      $('#voteBtn').disabled = true;
      $('#voteBtn').textContent = 'تم التصويت';
      $('#voteBtn').classList.add('opacity-60');
      toast('تم تسجيل صوتك');
    }

    function renderAll(){
      $('#siteLogo').src = USER_LOGO_URL;
      $('#homeFlag').src = "https://media.discordapp.net/attachments/1327007975604355153/1505598972473901187/content.png?ex=6a0b35cf&is=6a09e44f&hm=abdc2c4916bb0dc4566ac7c34a3792c694449d9601e531e7d7a90b20129891e3&=&format=webp&quality=lossless&width=1872&height=749";
      renderCards($('#programGrid'), ITEMS.programs, 'programs', 'اقرأ التفاصيل');
      renderCards($('#articleGrid'), ITEMS.articles, 'articles', 'اقرأ التفاصيل');
      renderCards($('#investigationGrid'), ITEMS.investigations, 'investigations', 'اقرأ التفاصيل');
      renderCards($('#reportGrid'), ITEMS.reports, 'reports', 'اقرأ التفاصيل');
      renderCards($('#newsGrid'), ITEMS.news, 'news', 'اقرأ التفاصيل');
      renderReferences();
      $('#currentMood').textContent = 'ضحك';
      $('#moodRecommendation').textContent = moods['ضحك'];
      $('#hoursValue').textContent = '8 ساعة';
      $('#quoteBox').textContent = quotes[0];
      syncVotes();
      setPage('home');
    }

    window.app = {
      showPage:setPage, openItem, closeDetail, showMore, openDev, closeDev,
      setMood, updateHours, nextQuote, quiz, recommend, voteOnce,
      filterPrograms:(q)=>{ state.programQuery = q || ''; renderProgramSearch(); },
      setProgramFilter:(f)=>{ state.programFilter = f || 'all'; renderProgramSearch(); }
    };

    document.addEventListener('DOMContentLoaded', renderAll);

    document.addEventListener('click', (e) => {
      const btn = e.target.closest('button, a');
      if (!btn) return;
      if (btn.hasAttribute('data-open')) { openItem(btn.getAttribute('data-open')); return; }
      if (btn.hasAttribute('data-page')) { setPage(btn.getAttribute('data-page')); return; }
      if (btn.hasAttribute('data-page-jump')) { setPage(btn.getAttribute('data-page-jump')); return; }
      if (btn.hasAttribute('data-program-filter')) { state.programFilter = btn.getAttribute('data-program-filter') || 'all'; renderProgramSearch(); return; }
      if (btn.hasAttribute('data-mood')) { setMood(btn.getAttribute('data-mood')); return; }
      if (btn.hasAttribute('data-quiz')) { quiz(btn.getAttribute('data-quiz')); return; }
      if (btn.id === 'recommendBtn') { recommend(); return; }
      if (btn.id === 'voteBtn') { voteOnce(); return; }
      if (btn.id === 'quoteBtn') { nextQuote(); return; }
      if (btn.id === 'moreBtn') { showMore(); return; }
      if (btn.id === 'logoBtn') { setPage('home'); return; }
      if (btn.id === 'devBtn') { openDev(); return; }
      if (btn.hasAttribute('data-close-modal')) { closeDetail(); return; }
      if (btn.hasAttribute('data-close-dev')) { closeDev(); return; }
    });

    document.addEventListener('input', (e) => {
      if (e.target && e.target.id === 'hoursSlider') updateHours(e.target.value);
      if (e.target && e.target.id === 'programSearch') { state.programQuery = e.target.value; renderProgramSearch(); }
    });

    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') {
        if (!$('#detailModal').classList.contains('hidden')) closeDetail();
        if (!$('#devModal').classList.contains('hidden')) closeDev();
      }
    });
  </script>
</body>
</html>
