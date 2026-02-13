<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>القرآن الكريم - قرآن يتلى آناء الليل وأطراف النهار</title>
<meta name="description" content="القرآن الكريم - قراءة واستماع وترجمة وتفسير">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Amiri+Quran&family=Amiri:wght@400;700&family=Cairo:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
:root{
--pr:#0D4A3E;--pr2:#1A7A5F;--pr3:#0a3a30;
--gd:#C8A951;--gd2:#A68B3A;--gdl:rgba(200,169,81,.12);
--bg:#F4EDE4;--bg2:#FAF6EE;--bg3:#EFEBE3;--bg4:#FFF;
--tx:#2C1810;--tx2:#5A4A3A;--tx3:#8A7A6A;
--bd:#DDD4C8;--bd2:#C8BCA8;
--sh:0 2px 16px rgba(0,0,0,.08);
--rd:12px;--rd2:8px;
--fq:'Amiri Quran','Amiri',serif;--fa:'Amiri',serif;--fu:'Cairo',sans-serif;
--qs:28px;--ts:15px;
--hh:56px;--ph:72px;
}
[data-t=dark]{
--pr:#3ECFB5;--pr2:#2DB89E;--pr3:#1a5a4a;
--gd:#DAA520;--gd2:#B8860B;--gdl:rgba(218,165,32,.1);
--bg:#0C1117;--bg2:#141C25;--bg3:#1A242F;--bg4:#1E2A36;
--tx:#D8CEBC;--tx2:#A89A88;--tx3:#6A5E52;
--bd:#2A3642;--bd2:#344050;
--sh:0 2px 16px rgba(0,0,0,.3);
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{font-family:var(--fu);background:var(--bg);color:var(--tx);overflow:hidden;height:100vh;transition:background .3s,color .3s}
::-webkit-scrollbar{width:5px}
::-webkit-scrollbar-track{background:transparent}
::-webkit-scrollbar-thumb{background:var(--gd);border-radius:3px}
button{cursor:pointer;font-family:var(--fu)}
select,input{font-family:var(--fu)}

/* ═══ HEADER ═══ */
.hdr{position:fixed;top:0;left:0;right:0;height:var(--hh);background:linear-gradient(135deg,var(--pr),var(--pr2));display:flex;align-items:center;justify-content:space-between;padding:0 16px;z-index:100;box-shadow:0 3px 20px rgba(0,0,0,.25)}
.hdr *{color:#fff}
.h-r{display:flex;align-items:center;gap:10px}
.h-logo{width:36px;height:36px;flex-shrink:0}
.h-logo svg{width:100%;height:100%;fill:var(--gd)}
.h-ti{font-size:15px;font-weight:700;line-height:1.3}
.h-sub{font-size:9.5px;opacity:.75}
.h-l{display:flex;gap:5px}
.hb{width:36px;height:36px;border-radius:50%;border:none;background:rgba(255,255,255,.13);display:flex;align-items:center;justify-content:center;font-size:16px;transition:.2s}
.hb:hover{background:rgba(255,255,255,.25)}

/* ═══ LAYOUT ═══ */
.wrap{display:flex;height:calc(100vh - var(--hh) - var(--ph));margin-top:var(--hh)}

/* ═══ LEFT PANEL ═══ */
.lp{width:380px;background:var(--bg3);border-right:1px solid var(--bd);display:flex;flex-direction:column;overflow:hidden;transition:width .3s}
.lp-ctrl{padding:10px 12px;border-bottom:1px solid var(--bd);display:flex;flex-direction:column;gap:7px;background:var(--bg4);flex-shrink:0}
.ctrl-row{display:flex;gap:6px}
.ctrl-row>*{flex:1}
.csel{padding:7px 10px;border:1px solid var(--bd);border-radius:var(--rd2);background:var(--bg2);color:var(--tx);font-size:12px;outline:none;transition:.2s;width:100%}
.csel:focus{border-color:var(--gd)}
.ctrl-label{font-size:10px;color:var(--tx3);margin-bottom:2px;display:block}
.ctrl-grp{display:flex;flex-direction:column}

/* tabs */
.lp-tabs{display:flex;border-bottom:1px solid var(--bd);background:var(--bg4);flex-shrink:0}
.ltab{flex:1;padding:9px 8px;border:none;background:none;font-size:12px;font-weight:600;color:var(--tx3);border-bottom:2px solid transparent;transition:.2s}
.ltab:hover{color:var(--tx)}
.ltab.act{color:var(--pr);border-bottom-color:var(--gd)}

/* tab content */
.lp-body{flex:1;overflow-y:auto;padding:0}
.tab-c{display:none;padding:12px}
.tab-c.act{display:block}

/* translation verses */
.tr-ay{padding:10px 12px;border-bottom:1px solid var(--bd);cursor:pointer;transition:.15s;display:flex;gap:8px;line-height:1.8}
.tr-ay:hover{background:var(--gdl)}
.tr-ay.hl{background:var(--gdl);border-right:3px solid var(--gd)}
.tr-num{min-width:28px;height:28px;display:flex;align-items:center;justify-content:center;background:var(--pr);color:#fff;border-radius:50%;font-size:11px;font-weight:700;flex-shrink:0;margin-top:2px}
.tr-tx{font-size:var(--ts);color:var(--tx2)}

/* search */
.sch-box{position:relative;margin-bottom:10px}
.sch-inp{width:100%;padding:9px 36px 9px 12px;border:1px solid var(--bd);border-radius:var(--rd);background:var(--bg2);color:var(--tx);font-size:13px;outline:none}
.sch-inp:focus{border-color:var(--gd)}
.sch-ic{position:absolute;right:10px;top:50%;transform:translateY(-50%);font-size:14px;color:var(--tx3)}
.sch-res{max-height:300px;overflow-y:auto}
.sch-item{padding:8px 10px;border-bottom:1px solid var(--bd);cursor:pointer;font-size:12px;line-height:1.6;transition:.15s}
.sch-item:hover{background:var(--gdl)}
.sch-item b{color:var(--pr)}

/* surah list in search */
.sur-item{display:flex;align-items:center;gap:8px;padding:8px 10px;border-bottom:1px solid var(--bd);cursor:pointer;transition:.15s}
.sur-item:hover{background:var(--gdl)}
.sur-item.act{background:var(--pr);color:#fff;border-radius:var(--rd2)}
.sur-n{width:28px;height:28px;display:flex;align-items:center;justify-content:center;font-size:10px;font-weight:700;border:1.5px solid var(--gd);border-radius:50%;transform:rotate(45deg);flex-shrink:0;color:var(--gd)}
.sur-n span{transform:rotate(-45deg)}
.sur-item.act .sur-n{border-color:rgba(255,255,255,.4);color:#fff}
.sur-nm{font-size:13px;font-weight:600}
.sur-inf{font-size:10px;color:var(--tx3)}
.sur-item.act .sur-inf{color:rgba(255,255,255,.6)}

/* ═══ RIGHT PANEL ═══ */
.rp{flex:1;overflow-y:auto;background:var(--bg2);display:flex;flex-direction:column}
.rp-inner{max-width:720px;width:100%;margin:0 auto;padding:20px 24px}

/* decorative frame */
.mf{border:2px solid var(--gd);border-radius:var(--rd);padding:3px;background:var(--bg2);min-height:200px;position:relative}
.mf-inner{border:1px solid var(--bd2);border-radius:calc(var(--rd) - 3px);padding:22px 20px}

/* surah header ornament */
.s-hdr{text-align:center;margin-bottom:18px;padding:14px 20px;background:linear-gradient(135deg,var(--pr),var(--pr2));border-radius:var(--rd2);position:relative;overflow:hidden}
.s-hdr::before,.s-hdr::after{content:'✦';position:absolute;top:50%;transform:translateY(-50%);color:var(--gd);font-size:18px;opacity:.5}
.s-hdr::before{right:16px}
.s-hdr::after{left:16px}
.s-nm{font-family:var(--fq);font-size:28px;color:#fff;margin-bottom:2px}
.s-inf{font-size:11px;color:rgba(255,255,255,.7);display:flex;justify-content:center;gap:14px}

.bsm{text-align:center;font-family:var(--fq);font-size:26px;color:var(--pr);padding:10px;margin-bottom:14px}

/* ayahs */
.ay-wrap{line-height:3;text-align:justify;direction:rtl}
.ay-t{font-family:var(--fq);font-size:var(--qs);cursor:pointer;transition:.15s;padding:1px 3px;border-radius:3px}
.ay-t:hover{color:var(--pr)}
.ay-t.playing{background:var(--gdl);color:var(--pr)}
.ay-n{display:inline-flex;align-items:center;justify-content:center;width:32px;height:32px;font-size:12px;font-weight:700;color:var(--gd);margin:0 2px;vertical-align:middle;cursor:pointer;position:relative;font-family:var(--fu);transition:.2s}
.ay-n::before{content:'';position:absolute;width:100%;height:100%;border:1.5px solid var(--gd);border-radius:50%;transform:rotate(45deg)}
.ay-n:hover{color:var(--pr)}
.ay-n:hover::before{border-color:var(--pr)}

/* page/juz info */
.pg-info{text-align:center;margin-top:16px;padding-top:12px;border-top:1px solid var(--bd);font-size:11px;color:var(--tx3);display:flex;justify-content:center;gap:16px}

/* surah nav */
.s-nav{display:flex;justify-content:space-between;margin-top:16px}
.s-nb{display:flex;align-items:center;gap:4px;padding:7px 14px;background:var(--pr);color:#fff;border:none;border-radius:var(--rd2);font-size:12px;font-weight:600;transition:.2s}
.s-nb:hover{background:var(--pr2)}
.s-nb:disabled{opacity:.35;cursor:not-allowed}

/* font controls */
.fctrl{display:flex;align-items:center;justify-content:center;gap:6px;margin-bottom:12px}
.fcb{width:28px;height:28px;border-radius:50%;border:1px solid var(--bd);background:var(--bg);color:var(--tx);font-size:14px;display:flex;align-items:center;justify-content:center;transition:.2s}
.fcb:hover{border-color:var(--gd);color:var(--gd)}
.fclbl{font-size:11px;color:var(--tx3);min-width:24px;text-align:center}

/* welcome */
.welc{display:flex;flex-direction:column;align-items:center;justify-content:center;min-height:60vh;text-align:center;padding:30px}
.welc-ic{width:80px;height:80px;margin-bottom:14px}
.welc-ic svg{width:100%;height:100%;fill:var(--gd)}
.welc h1{font-size:26px;color:var(--pr);font-family:var(--fq);margin-bottom:6px}
.welc p{color:var(--tx2);font-size:14px;margin-bottom:16px}
.welc-v{font-family:var(--fq);font-size:20px;color:var(--pr);padding:16px 22px;background:var(--gdl);border:1px solid var(--gd);border-radius:var(--rd);max-width:500px;line-height:2.2}
.welc small{color:var(--tx3);font-size:12px;margin-top:8px;display:block}

/* ═══ AUDIO PLAYER ═══ */
.apl{position:fixed;bottom:0;left:0;right:0;height:var(--ph);background:var(--bg4);border-top:1px solid var(--bd);display:flex;align-items:center;padding:0 14px;gap:10px;z-index:100;box-shadow:0 -2px 15px rgba(0,0,0,.06)}
.pl-info{min-width:0;flex-shrink:0;max-width:160px}
.pl-sn{font-size:12px;font-weight:600;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.pl-ay{font-size:10px;color:var(--tx3)}
.pl-btns{display:flex;align-items:center;gap:3px;flex-shrink:0}
.plb{width:34px;height:34px;border-radius:50%;border:none;background:none;color:var(--tx);font-size:16px;display:flex;align-items:center;justify-content:center;transition:.2s}
.plb:hover{background:var(--gdl)}
.plb.main{width:40px;height:40px;background:var(--pr);color:#fff;font-size:18px}
.plb.main:hover{background:var(--pr2)}
.pl-prg{flex:1;display:flex;align-items:center;gap:6px;min-width:0}
.prg-bar{flex:1;height:4px;background:var(--bd);border-radius:2px;cursor:pointer;overflow:hidden}
.prg-fill{height:100%;background:var(--gd);width:0%;border-radius:2px;transition:width .1s}
.prg-time{font-size:10px;color:var(--tx3);min-width:32px;text-align:center;flex-shrink:0}
.pl-rec{flex-shrink:0}
.pl-rec select{padding:4px 6px;font-size:11px;border:1px solid var(--bd);border-radius:var(--rd2);background:var(--bg);color:var(--tx);outline:none}

/* ═══ CONTEXT MENU ═══ */
.ctx{display:none;position:fixed;background:var(--bg4);border:1px solid var(--bd);border-radius:var(--rd2);padding:4px;box-shadow:0 4px 20px rgba(0,0,0,.15);z-index:200}
.ctx.show{display:flex;gap:2px}
.ctx-b{padding:5px 10px;border:none;background:none;font-size:12px;color:var(--tx);border-radius:4px;white-space:nowrap;transition:.15s}
.ctx-b:hover{background:var(--gdl);color:var(--pr)}

/* ═══ LOADING ═══ */
.ldg{display:flex;flex-direction:column;align-items:center;justify-content:center;padding:40px}
.spin{width:36px;height:36px;border:3px solid var(--bd);border-top-color:var(--gd);border-radius:50%;animation:sp .7s linear infinite}
@keyframes sp{to{transform:rotate(360deg)}}
.ldg span{margin-top:10px;font-size:12px;color:var(--tx3)}

/* ═══ MOBILE ═══ */
.mob-tabs{display:none;position:fixed;top:var(--hh);left:0;right:0;background:var(--bg4);border-bottom:1px solid var(--bd);z-index:90}
.mob-tabs button{flex:1;padding:10px;border:none;background:none;font-size:13px;font-weight:600;color:var(--tx3);border-bottom:2px solid transparent}
.mob-tabs button.act{color:var(--pr);border-bottom-color:var(--gd)}

@media(max-width:900px){
.lp{position:fixed;top:var(--hh);left:0;right:0;bottom:var(--ph);width:100%;z-index:80;transform:translateX(-100%);transition:transform .3s}
.lp.open{transform:translateX(0)}
.rp{margin-right:0}
.mob-tabs{display:flex}
.wrap{flex-direction:column;margin-top:calc(var(--hh) + 42px)}
.rp-inner{padding:14px}
:root{--qs:22px;--ts:13px}
.s-nm{font-size:22px}
.bsm{font-size:20px}
.apl{flex-wrap:wrap;height:auto;padding:6px 10px;gap:4px}
.pl-prg{order:-1;width:100%;flex-basis:100%}
.pl-info{max-width:120px}
.pl-rec select{font-size:10px}
}
@media(max-width:480px){
:root{--qs:19px;--ts:12px}
.s-hdr{padding:10px}
.s-nm{font-size:20px}
.mf-inner{padding:14px 12px}
}

/* ═══ FOOTER ═══ */
.ftr{background:var(--pr3);color:rgba(255,255,255,.8);text-align:center;padding:20px 16px;font-size:11px;line-height:2}
.ftr a{color:var(--gd)}
.ftr hr{border:none;height:1px;background:rgba(255,255,255,.1);margin:8px auto;max-width:100px}
</style>
</head>
<body>

<!-- ═══ HEADER ═══ -->
<header class="hdr">
<div class="h-r">
<div class="h-logo"><svg viewBox="0 0 100 100"><path d="M50 8C50 8 26 3 6 17L6 83C26 73 50 77 50 77C50 77 74 73 94 83L94 17C74 3 50 8 50 8Z" opacity=".9"/><line x1="50" y1="12" x2="50" y2="77" stroke="#fff" stroke-width="1.5"/><circle cx="50" cy="30" r="6" fill="none" stroke="#fff" stroke-width="1"/><circle cx="50" cy="30" r="2" fill="#fff"/></svg></div>
<div><div class="h-ti">القرآن الكريم</div><div class="h-sub">قرآن يتلى أطراف الليل وآناء النهار</div></div>
</div>
<div class="h-l">
<button class="hb" onclick="toggleTheme()" title="الوضع الليلي/النهاري">🌙</button>
<button class="hb" onclick="toggleLP()" title="لوحة التحكم">☰</button>
</div>
</header>

<!-- ═══ MOBILE TABS ═══ -->
<div class="mob-tabs" id="mobTabs">
<button class="act" onclick="showMobPanel('quran')">📖 القرآن</button>
<button onclick="showMobPanel('trans')">🌐 الترجمة</button>
</div>

<!-- ═══ MAIN LAYOUT ═══ -->
<div class="wrap">

<!-- LEFT PANEL -->
<aside class="lp" id="leftPanel">

<div class="lp-ctrl">
<div class="ctrl-row">
<div class="ctrl-grp">
<label class="ctrl-label">🌐 اللغة / Language</label>
<select class="csel" id="langSel" onchange="changeLang()"></select>
</div>
</div>
<div class="ctrl-row">
<div class="ctrl-grp">
<label class="ctrl-label">📖 السورة</label>
<select class="csel" id="surahSel" onchange="loadSurah(this.value)"></select>
</div>
</div>
<div class="ctrl-row">
<div class="ctrl-grp">
<label class="ctrl-label">📑 الجزء</label>
<select class="csel" id="juzSel" onchange="loadJuz(this.value)">
<option value="">اختر الجزء</option>
</select>
</div>
<div class="ctrl-grp">
<label class="ctrl-label">📄 الصفحة</label>
<input type="number" class="csel" id="pageInp" min="1" max="604" placeholder="1-604" onchange="loadPage(this.value)">
</div>
</div>
<div class="ctrl-row">
<div class="ctrl-grp">
<label class="ctrl-label">🎙️ القارئ</label>
<select class="csel" id="reciterSel" onchange="changeReciter()"></select>
</div>
</div>
</div>

<div class="lp-tabs">
<button class="ltab act" onclick="switchTab('trans',this)">🌐 الترجمة</button>
<button class="ltab" onclick="switchTab('tafsir',this)">📖 التفسير</button>
<button class="ltab" onclick="switchTab('search',this)">🔍 البحث</button>
<button class="ltab" onclick="switchTab('index',this)">📋 الفهرس</button>
</div>

<div class="lp-body">
<!-- Translation Tab -->
<div class="tab-c act" id="tab-trans">
<div id="transContent"><p style="padding:20px;text-align:center;color:var(--tx3)">اختر سورة للبدء</p></div>
</div>
<!-- Tafsir Tab -->
<div class="tab-c" id="tab-tafsir">
<div id="tafsirContent"><p style="padding:20px;text-align:center;color:var(--tx3)">اختر سورة لعرض التفسير</p></div>
</div>
<!-- Search Tab -->
<div class="tab-c" id="tab-search">
<div class="sch-box"><span class="sch-ic">🔍</span><input class="sch-inp" id="schInp" placeholder="ابحث في القرآن الكريم..." onkeyup="doSearch(event)"></div>
<div class="sch-res" id="schRes"></div>
</div>
<!-- Index Tab -->
<div class="tab-c" id="tab-index">
<div id="surahIndex"></div>
</div>
</div>
</aside>

<!-- RIGHT PANEL -->
<main class="rp" id="rightPanel">
<div class="rp-inner">

<!-- Welcome -->
<div class="welc" id="welcScreen">
<div class="welc-ic"><svg viewBox="0 0 100 100"><path d="M50 8C50 8 26 3 6 17L6 83C26 73 50 77 50 77C50 77 74 73 94 83L94 17C74 3 50 8 50 8Z" opacity=".9"/><line x1="50" y1="12" x2="50" y2="77" stroke="#fff" stroke-width="1.5"/><circle cx="50" cy="30" r="6" fill="none" stroke="#fff" stroke-width="1"/><circle cx="50" cy="30" r="2" fill="#fff"/></svg></div>
<h1>القرآن الكريم</h1>
<p>قرآن يتلى أطراف الليل وآناء النهار</p>
<div class="welc-v">﴿ إِنَّ هَـٰذَا ٱلۡقُرۡءَانَ يَهۡدِي لِلَّتِي هِيَ أَقۡوَمُ وَيُبَشِّرُ ٱلۡمُؤۡمِنِينَ ٱلَّذِينَ يَعۡمَلُونَ ٱلصَّـٰلِحَـٰتِ أَنَّ لَهُمۡ أَجۡرٗا كَبِيرٗا ﴾</div>
<small>سورة الإسراء - الآية ٩</small>
</div>

<!-- Quran Content -->
<div id="quranView" style="display:none">
<div class="fctrl">
<button class="fcb" onclick="chgFont(-2)">−</button>
<span class="fclbl" id="fontLbl">28</span>
<button class="fcb" onclick="chgFont(2)">+</button>
</div>
<div class="mf">
<div class="mf-inner">
<div class="s-hdr" id="sHdr"><div class="s-nm" id="sNm"></div><div class="s-inf" id="sInf"></div></div>
<div class="bsm" id="bsm">بِسۡمِ ٱللَّهِ ٱلرَّحۡمَـٰنِ ٱلرَّحِيمِ</div>
<div class="ay-wrap" id="ayWrap"></div>
<div class="pg-info" id="pgInfo"></div>
</div>
</div>
<div class="s-nav">
<button class="s-nb" id="prevB" onclick="navSurah(-1)">→ السابقة</button>
<button class="s-nb" id="nextB" onclick="navSurah(1)">التالية ←</button>
</div>
</div>

<!-- Footer -->
<footer class="ftr" id="ftr">
<hr>
<p><strong>القرآن الكريم - قرآن يتلى أطراف الليل وآناء النهار</strong></p>
<hr>
<p>النص القرآني: AlQuran Cloud API (مفتوح المصدر - رخصة MIT)</p>
<p>التلاوات: EveryAyah.com (متاحة للاستخدام المجاني)</p>
<p>تفسير الجلالين: ملك عام (القرن التاسع الهجري)</p>
<p>الترجمات من مصادر مفتوحة عبر AlQuran Cloud API</p>
<p>الخطوط: Amiri و Cairo (رخصة SIL المفتوحة)</p>
<hr>
<p>⚠️ هذا الموقع <strong>غير تابع لأي جهة رسمية</strong></p>
<p>📧 <a href="mailto:ali.ibrahim2150@gmail.com">ali.ibrahim2150@gmail.com</a></p>
<hr>
<p>تصميم وبرمجة خاصة © <span id="yr"></span> | المحتوى من مصادر ملك عام ومفتوحة</p>
</footer>

</div>
</main>
</div>

<!-- ═══ CONTEXT MENU ═══ -->
<div class="ctx" id="ctxMenu">
<button class="ctx-b" onclick="playSelAy()">▶ تشغيل</button>
<button class="ctx-b" onclick="showSelTafsir()">📖 تفسير</button>
<button class="ctx-b" onclick="copySelAy()">📋 نسخ</button>
</div>

<!-- ═══ AUDIO PLAYER ═══ -->
<div class="apl">
<div class="pl-info"><div class="pl-sn" id="plSn">القرآن الكريم</div><div class="pl-ay" id="plAy">—</div></div>
<div class="pl-btns">
<button class="plb" onclick="prevAyAudio()">⏮</button>
<button class="plb main" id="ppBtn" onclick="togglePP()">▶</button>
<button class="plb" onclick="nextAyAudio()">⏭</button>
<button class="plb" id="rpBtn" onclick="toggleRp()" style="font-size:13px">🔁</button>
</div>
<div class="pl-prg">
<span class="prg-time" id="curT">0:00</span>
<div class="prg-bar" onclick="seekAu(event)"><div class="prg-fill" id="prgFill"></div></div>
<span class="prg-time" id="durT">0:00</span>
</div>
<div class="pl-rec"><select class="csel" id="recSel2" onchange="syncReciter(this.value)" style="font-size:10px;padding:4px"></select></div>
</div>

<script>
// ════════════════════════════════════════
// DATA
// ════════════════════════════════════════
const S=[
{n:1,a:"الفاتحة",c:7,t:"مكية"},{n:2,a:"البقرة",c:286,t:"مدنية"},{n:3,a:"آل عمران",c:200,t:"مدنية"},
{n:4,a:"النساء",c:176,t:"مدنية"},{n:5,a:"المائدة",c:120,t:"مدنية"},{n:6,a:"الأنعام",c:165,t:"مكية"},
{n:7,a:"الأعراف",c:206,t:"مكية"},{n:8,a:"الأنفال",c:75,t:"مدنية"},{n:9,a:"التوبة",c:129,t:"مدنية"},
{n:10,a:"يونس",c:109,t:"مكية"},{n:11,a:"هود",c:123,t:"مكية"},{n:12,a:"يوسف",c:111,t:"مكية"},
{n:13,a:"الرعد",c:43,t:"مدنية"},{n:14,a:"إبراهيم",c:52,t:"مكية"},{n:15,a:"الحجر",c:99,t:"مكية"},
{n:16,a:"النحل",c:128,t:"مكية"},{n:17,a:"الإسراء",c:111,t:"مكية"},{n:18,a:"الكهف",c:110,t:"مكية"},
{n:19,a:"مريم",c:98,t:"مكية"},{n:20,a:"طه",c:135,t:"مكية"},{n:21,a:"الأنبياء",c:112,t:"مكية"},
{n:22,a:"الحج",c:78,t:"مدنية"},{n:23,a:"المؤمنون",c:118,t:"مكية"},{n:24,a:"النور",c:64,t:"مدنية"},
{n:25,a:"الفرقان",c:77,t:"مكية"},{n:26,a:"الشعراء",c:227,t:"مكية"},{n:27,a:"النمل",c:93,t:"مكية"},
{n:28,a:"القصص",c:88,t:"مكية"},{n:29,a:"العنكبوت",c:69,t:"مكية"},{n:30,a:"الروم",c:60,t:"مكية"},
{n:31,a:"لقمان",c:34,t:"مكية"},{n:32,a:"السجدة",c:30,t:"مكية"},{n:33,a:"الأحزاب",c:73,t:"مدنية"},
{n:34,a:"سبأ",c:54,t:"مكية"},{n:35,a:"فاطر",c:45,t:"مكية"},{n:36,a:"يس",c:83,t:"مكية"},
{n:37,a:"الصافات",c:182,t:"مكية"},{n:38,a:"ص",c:88,t:"مكية"},{n:39,a:"الزمر",c:75,t:"مكية"},
{n:40,a:"غافر",c:85,t:"مكية"},{n:41,a:"فصلت",c:54,t:"مكية"},{n:42,a:"الشورى",c:53,t:"مكية"},
{n:43,a:"الزخرف",c:89,t:"مكية"},{n:44,a:"الدخان",c:59,t:"مكية"},{n:45,a:"الجاثية",c:37,t:"مكية"},
{n:46,a:"الأحقاف",c:35,t:"مكية"},{n:47,a:"محمد",c:38,t:"مدنية"},{n:48,a:"الفتح",c:29,t:"مدنية"},
{n:49,a:"الحجرات",c:18,t:"مدنية"},{n:50,a:"ق",c:45,t:"مكية"},{n:51,a:"الذاريات",c:60,t:"مكية"},
{n:52,a:"الطور",c:49,t:"مكية"},{n:53,a:"النجم",c:62,t:"مكية"},{n:54,a:"القمر",c:55,t:"مكية"},
{n:55,a:"الرحمن",c:78,t:"مدنية"},{n:56,a:"الواقعة",c:96,t:"مكية"},{n:57,a:"الحديد",c:29,t:"مدنية"},
{n:58,a:"المجادلة",c:22,t:"مدنية"},{n:59,a:"الحشر",c:24,t:"مدنية"},{n:60,a:"الممتحنة",c:13,t:"مدنية"},
{n:61,a:"الصف",c:14,t:"مدنية"},{n:62,a:"الجمعة",c:11,t:"مدنية"},{n:63,a:"المنافقون",c:11,t:"مدنية"},
{n:64,a:"التغابن",c:18,t:"مدنية"},{n:65,a:"الطلاق",c:12,t:"مدنية"},{n:66,a:"التحريم",c:12,t:"مدنية"},
{n:67,a:"الملك",c:30,t:"مكية"},{n:68,a:"القلم",c:52,t:"مكية"},{n:69,a:"الحاقة",c:52,t:"مكية"},
{n:70,a:"المعارج",c:44,t:"مكية"},{n:71,a:"نوح",c:28,t:"مكية"},{n:72,a:"الجن",c:28,t:"مكية"},
{n:73,a:"المزمل",c:20,t:"مكية"},{n:74,a:"المدثر",c:56,t:"مكية"},{n:75,a:"القيامة",c:40,t:"مكية"},
{n:76,a:"الإنسان",c:31,t:"مدنية"},{n:77,a:"المرسلات",c:50,t:"مكية"},{n:78,a:"النبأ",c:40,t:"مكية"},
{n:79,a:"النازعات",c:46,t:"مكية"},{n:80,a:"عبس",c:42,t:"مكية"},{n:81,a:"التكوير",c:29,t:"مكية"},
{n:82,a:"الانفطار",c:19,t:"مكية"},{n:83,a:"المطففين",c:36,t:"مكية"},{n:84,a:"الانشقاق",c:25,t:"مكية"},
{n:85,a:"البروج",c:22,t:"مكية"},{n:86,a:"الطارق",c:17,t:"مكية"},{n:87,a:"الأعلى",c:19,t:"مكية"},
{n:88,a:"الغاشية",c:26,t:"مكية"},{n:89,a:"الفجر",c:30,t:"مكية"},{n:90,a:"البلد",c:20,t:"مكية"},
{n:91,a:"الشمس",c:15,t:"مكية"},{n:92,a:"الليل",c:21,t:"مكية"},{n:93,a:"الضحى",c:11,t:"مكية"},
{n:94,a:"الشرح",c:8,t:"مكية"},{n:95,a:"التين",c:8,t:"مكية"},{n:96,a:"العلق",c:19,t:"مكية"},
{n:97,a:"القدر",c:5,t:"مكية"},{n:98,a:"البينة",c:8,t:"مدنية"},{n:99,a:"الزلزلة",c:8,t:"مدنية"},
{n:100,a:"العاديات",c:11,t:"مكية"},{n:101,a:"القارعة",c:11,t:"مكية"},{n:102,a:"التكاثر",c:8,t:"مكية"},
{n:103,a:"العصر",c:3,t:"مكية"},{n:104,a:"الهمزة",c:9,t:"مكية"},{n:105,a:"الفيل",c:5,t:"مكية"},
{n:106,a:"قريش",c:4,t:"مكية"},{n:107,a:"الماعون",c:7,t:"مكية"},{n:108,a:"الكوثر",c:3,t:"مكية"},
{n:109,a:"الكافرون",c:6,t:"مكية"},{n:110,a:"النصر",c:3,t:"مدنية"},{n:111,a:"المسد",c:5,t:"مكية"},
{n:112,a:"الإخلاص",c:4,t:"مكية"},{n:113,a:"الفلق",c:5,t:"مكية"},{n:114,a:"الناس",c:6,t:"مكية"}
];

const LANGS=[
{id:'ar.jalalayn',lb:'العربية - تفسير الجلالين',lc:'ar',dr:'rtl'},
{id:'en.sahih',lb:'English (Saheeh Intl)',lc:'en',dr:'ltr'},
{id:'en.asad',lb:'English (Muhammad Asad)',lc:'en',dr:'ltr'},
{id:'fr.hamidullah',lb:'Français (Hamidullah)',lc:'fr',dr:'ltr'},
{id:'es.asad',lb:'Español (Asad)',lc:'es',dr:'ltr'},
{id:'pt.elhayek',lb:'Português (El-Hayek)',lc:'pt',dr:'ltr'},
{id:'it.piccardo',lb:'Italiano (Piccardo)',lc:'it',dr:'ltr'},
{id:'nl.keyzer',lb:'Nederlands (Keyzer)',lc:'nl',dr:'ltr'},
{id:'ru.kuliev',lb:'Русский (Кулиев)',lc:'ru',dr:'ltr'},
{id:'tr.ates',lb:'Türkçe (Ateş)',lc:'tr',dr:'ltr'},
{id:'zh.majian',lb:'中文 (Ma Jian)',lc:'zh',dr:'ltr'},
{id:'ja.japanese',lb:'日本語',lc:'ja',dr:'ltr'},
{id:'hi.hindi',lb:'हिन्दी',lc:'hi',dr:'ltr'},
{id:'uk.yakubovych',lb:'Українська',lc:'uk',dr:'ltr'},
{id:'de.bubenheim',lb:'Deutsch (Bubenheim)',lc:'de',dr:'ltr'},
{id:'ur.jalandhry',lb:'اردو (جالندھری)',lc:'ur',dr:'rtl'},
{id:'bn.bengali',lb:'বাংলা',lc:'bn',dr:'ltr'},
{id:'ms.basmeih',lb:'Bahasa Melayu',lc:'ms',dr:'ltr'},
{id:'id.indonesian',lb:'Bahasa Indonesia',lc:'id',dr:'ltr'},
{id:'ko.korean',lb:'한국어',lc:'ko',dr:'ltr'},
{id:'sw.barwani',lb:'Kiswahili',lc:'sw',dr:'ltr'},
{id:'sq.ahmeti',lb:'Shqip (Albanian)',lc:'sq',dr:'ltr'},
{id:'bs.mlivo',lb:'Bosanski',lc:'bs',dr:'ltr'},
{id:'az.musayev',lb:'Azərbaycanca',lc:'az',dr:'ltr'},
{id:'fa.makarem',lb:'فارسی (مکارم)',lc:'fa',dr:'rtl'},
{id:'tg.ayati',lb:'Тоҷикӣ',lc:'tg',dr:'ltr'},
{id:'th.thai',lb:'ภาษาไทย',lc:'th',dr:'ltr'}
];

const RECITERS=[
{id:'Alafasy_128kbps',lb:'مشاري العفاسي'},
{id:'Abdul_Basit_Murattal_192kbps',lb:'عبد الباسط - مرتل'},
{id:'Husary_128kbps',lb:'محمود خليل الحصري'},
{id:'Minshawy_Murattal_128kbps',lb:'المنشاوي - مرتل'},
{id:'Abdurrahmaan_As-Sudais_192kbps',lb:'عبدالرحمن السديس'},
{id:'Abu_Bakr_Ash-Shaatree_128kbps',lb:'أبو بكر الشاطري'},
{id:'Saood_ash-Shuraym_128kbps',lb:'سعود الشريم'},
{id:'Hani_Rifai_192kbps',lb:'هاني الرفاعي'},
{id:'Maher_AlMuaiqly_128kbps',lb:'ماهر المعيقلي'},
{id:'Muhammad_Jibreel_128kbps',lb:'محمد جبريل'}
];

// ════════════════════════════════════════
// STATE
// ════════════════════════════════════════
let curSurah=null, curAyahs=[], curTrans=[], curTafsir=[];
let selAyNum=null, playIdx=0, isPlay=false, isRpt=false;
let curLang=null, curReciter=null;
let audio=new Audio();
let fontSize=parseInt(localStorage.getItem('fs')||'28');

// ════════════════════════════════════════
// INIT
// ════════════════════════════════════════
document.addEventListener('DOMContentLoaded',()=>{
document.getElementById('yr').textContent=new Date().getFullYear();

// Populate selects
populateSelects();
detectLang();
applyTheme(localStorage.getItem('thm')||'light');
document.documentElement.style.setProperty('--qs',fontSize+'px');
document.getElementById('fontLbl').textContent=fontSize;

// Audio events
audio.addEventListener('timeupdate',updPrg);
audio.addEventListener('ended',onEnd);
audio.addEventListener('loadedmetadata',()=>{
    document.getElementById('durT').textContent=fmtT(audio.duration);
});

// Click outside ctx
document.addEventListener('click',e=>{
    if(!e.target.closest('.ay-n')&&!e.target.closest('.ctx'))
        document.getElementById('ctxMenu').classList.remove('show');
});

// Load last
const last=localStorage.getItem('lastS');
if(last) loadSurah(parseInt(last));

// Build surah index
buildIndex();
});

function populateSelects(){
    // Surah select
    const ss=document.getElementById('surahSel');
    ss.innerHTML='<option value="">اختر السورة</option>';
    S.forEach(s=>{ss.innerHTML+=`<option value="${s.n}">${s.n}. ${s.a}</option>`});

    // Juz select
    const js=document.getElementById('juzSel');
    for(let i=1;i<=30;i++) js.innerHTML+=`<option value="${i}">الجزء ${i}</option>`;

    // Language select
    const ls=document.getElementById('langSel');
    LANGS.forEach(l=>{ls.innerHTML+=`<option value="${l.id}">${l.lb}</option>`});

    // Reciter selects
    const rs=document.getElementById('reciterSel');
    const rs2=document.getElementById('recSel2');
    RECITERS.forEach(r=>{
        rs.innerHTML+=`<option value="${r.id}">${r.lb}</option>`;
        rs2.innerHTML+=`<option value="${r.id}">${r.lb}</option>`;
    });
    curReciter=RECITERS[0].id;
}

function detectLang(){
    const bl=navigator.language.substring(0,2);
    const match=LANGS.find(l=>l.lc===bl);
    const def=match?match.id:'en.sahih';
    document.getElementById('langSel').value=def;
    curLang=def;
}

function buildIndex(){
    const el=document.getElementById('surahIndex');
    let h='';
    S.forEach(s=>{
        h+=`<div class="sur-item" id="idx-${s.n}" onclick="loadSurah(${s.n})">
            <div class="sur-n"><span>${s.n}</span></div>
            <div><div class="sur-nm">سورة ${s.a}</div>
            <div class="sur-inf">${s.t} | ${s.c} آية</div></div></div>`;
    });
    el.innerHTML=h;
}

// ════════════════════════════════════════
// LOAD SURAH
// ════════════════════════════════════════
async function loadSurah(num){
    num=parseInt(num);
    if(!num||num<1||num>114) return;
    curSurah=S.find(s=>s.n===num);

    // Update UI
    document.getElementById('welcScreen').style.display='none';
    document.getElementById('quranView').style.display='block';
    document.getElementById('surahSel').value=num;
    document.getElementById('sNm').textContent='سورة '+curSurah.a;
    document.getElementById('sInf').innerHTML=`<span>${curSurah.t}</span><span>${curSurah.c} آية</span>`;
    document.getElementById('bsm').style.display=(num===1||num===9)?'none':'block';
    document.getElementById('prevB').disabled=(num<=1);
    document.getElementById('nextB').disabled=(num>=114);
    document.getElementById('plSn').textContent='سورة '+curSurah.a;
    document.getElementById('plAy').textContent='—';
    localStorage.setItem('lastS',num);

    // Update index highlighting
    document.querySelectorAll('.sur-item').forEach(el=>el.classList.remove('act'));
    const idx=document.getElementById('idx-'+num);
    if(idx){idx.classList.add('act');idx.scrollIntoView({block:'nearest'})}

    // Stop audio
    stopAu();

    // Show loading
    document.getElementById('ayWrap').innerHTML='<div class="ldg"><div class="spin"></div><span>جارٍ تحميل السورة...</span></div>';
    document.getElementById('transContent').innerHTML='<div class="ldg"><div class="spin"></div><span>جارٍ تحميل الترجمة...</span></div>';

    // Close mobile panel
    if(window.innerWidth<=900) document.getElementById('leftPanel').classList.remove('open');

    // Scroll to top
    document.getElementById('rightPanel').scrollTo({top:0,behavior:'smooth'});

    // Fetch Arabic
    try{
        const res=await fetch(`https://api.alquran.cloud/v1/surah/${num}/quran-uthmani`);
        const data=await res.json();
        if(data.code===200){curAyahs=data.data.ayahs;renderAyahs();}
        else throw new Error();
    }catch(e){
        document.getElementById('ayWrap').innerHTML=errMsg(num);
    }

    // Fetch translation
    fetchTrans(num);
    // Fetch tafsir
    fetchTafsir(num);
}

function renderAyahs(){
    let h='';
    curAyahs.forEach((a,i)=>{
        h+=`<span class="ay-t" id="ay-${a.numberInSurah}" data-i="${i}">${a.text}</span>`;
        h+=`<span class="ay-n" onclick="showCtx(event,${a.numberInSurah})">${a.numberInSurah}</span> `;
    });
    document.getElementById('ayWrap').innerHTML=h;

    // Page/Juz info
    if(curAyahs.length>0){
        const first=curAyahs[0];
        document.getElementById('pgInfo').innerHTML=
            `<span>الصفحة: ${first.page}</span><span>الجزء: ${first.juz}</span><span>الحزب: ${first.hizbQuarter}</span>`;
    }
}

// ════════════════════════════════════════
// FETCH TRANSLATION
// ════════════════════════════════════════
async function fetchTrans(num){
    const lang=document.getElementById('langSel').value;
    curLang=lang;
    try{
        const res=await fetch(`https://api.alquran.cloud/v1/surah/${num}/${lang}`);
        const data=await res.json();
        if(data.code===200){
            curTrans=data.data.ayahs;
            renderTrans();
        }else throw new Error();
    }catch(e){
        document.getElementById('transContent').innerHTML=
            `<p style="padding:20px;text-align:center;color:#c0392b">❌ هذه الترجمة غير متاحة حالياً<br>جرّب لغة أخرى</p>`;
        curTrans=[];
    }
}

function renderTrans(){
    const dir=LANGS.find(l=>l.id===curLang);
    const d=dir?dir.dr:'ltr';
    let h='';
    curTrans.forEach(a=>{
        h+=`<div class="tr-ay" id="tr-${a.numberInSurah}" dir="${d}" onclick="hlAy(${a.numberInSurah})" style="text-align:${d==='rtl'?'right':'left'}">
            <span class="tr-num">${a.numberInSurah}</span>
            <span class="tr-tx">${a.text}</span></div>`;
    });
    document.getElementById('transContent').innerHTML=h;
}

// ════════════════════════════════════════
// FETCH TAFSIR (Jalalayn)
// ════════════════════════════════════════
async function fetchTafsir(num){
    try{
        const res=await fetch(`https://api.alquran.cloud/v1/surah/${num}/ar.jalalayn`);
        const data=await res.json();
        if(data.code===200){
            curTafsir=data.data.ayahs;
            renderTafsir();
        }else throw new Error();
    }catch(e){
        document.getElementById('tafsirContent').innerHTML=
            '<p style="padding:20px;text-align:center;color:var(--tx3)">تعذر تحميل التفسير</p>';
        curTafsir=[];
    }
}

function renderTafsir(){
    let h='';
    curTafsir.forEach((a,i)=>{
        const arTxt=curAyahs[i]?curAyahs[i].text:'';
        h+=`<div class="tr-ay" id="tf-${a.numberInSurah}" onclick="hlAy(${a.numberInSurah})" style="flex-direction:column;gap:4px">
            <div style="font-family:var(--fq);font-size:16px;color:var(--pr);background:var(--gdl);padding:6px 10px;border-radius:6px;line-height:2">﴿ ${arTxt} ﴾ [${a.numberInSurah}]</div>
            <div class="tr-tx" style="padding-right:8px">${a.text}</div></div>`;
    });
    document.getElementById('tafsirContent').innerHTML=h;
}

// ════════════════════════════════════════
// LOAD BY JUZ
// ════════════════════════════════════════
async function loadJuz(num){
    num=parseInt(num);
    if(!num) return;
    document.getElementById('welcScreen').style.display='none';
    document.getElementById('quranView').style.display='block';
    document.getElementById('sNm').textContent='الجزء '+num;
    document.getElementById('sInf').innerHTML='';
    document.getElementById('bsm').style.display='none';
    document.getElementById('ayWrap').innerHTML='<div class="ldg"><div class="spin"></div><span>جارٍ تحميل الجزء...</span></div>';
    document.getElementById('transContent').innerHTML='<div class="ldg"><div class="spin"></div><span>...</span></div>';
    stopAu();

    try{
        const [arRes,trRes]=await Promise.all([
            fetch(`https://api.alquran.cloud/v1/juz/${num}/quran-uthmani`),
            fetch(`https://api.alquran.cloud/v1/juz/${num}/${curLang}`)
        ]);
        const arData=await arRes.json();
        const trData=await trRes.json();
        if(arData.code===200){
            curAyahs=arData.data.ayahs;
            renderJuzAyahs();
        }
        if(trData.code===200){
            curTrans=trData.data.ayahs;
            renderTrans();
        }
    }catch(e){
        document.getElementById('ayWrap').innerHTML='<div class="ldg"><span style="color:#c0392b">❌ خطأ في التحميل</span></div>';
    }
}

function renderJuzAyahs(){
    let h='',lastSurah=0;
    curAyahs.forEach((a,i)=>{
        if(a.surah.number!==lastSurah){
            lastSurah=a.surah.number;
            h+=`<div class="s-hdr" style="margin:14px 0"><div class="s-nm" style="font-size:20px">سورة ${a.surah.name}</div></div>`;
        }
        h+=`<span class="ay-t" id="ay-${a.number}" data-i="${i}">${a.text}</span>`;
        h+=`<span class="ay-n" onclick="playAyDirect(${a.surah.number},${a.numberInSurah})">${a.numberInSurah}</span> `;
    });
    document.getElementById('ayWrap').innerHTML=h;
    document.getElementById('pgInfo').innerHTML='';
}

// ════════════════════════════════════════
// LOAD BY PAGE
// ════════════════════════════════════════
async function loadPage(num){
    num=parseInt(num);
    if(!num||num<1||num>604) return;
    document.getElementById('welcScreen').style.display='none';
    document.getElementById('quranView').style.display='block';
    document.getElementById('sNm').textContent='الصفحة '+num;
    document.getElementById('sInf').innerHTML='';
    document.getElementById('bsm').style.display='none';
    document.getElementById('ayWrap').innerHTML='<div class="ldg"><div class="spin"></div><span>جارٍ تحميل الصفحة...</span></div>';
    document.getElementById('transContent').innerHTML='<div class="ldg"><div class="spin"></div><span>...</span></div>';
    stopAu();

    try{
        const [arRes,trRes]=await Promise.all([
            fetch(`https://api.alquran.cloud/v1/page/${num}/quran-uthmani`),
            fetch(`https://api.alquran.cloud/v1/page/${num}/${curLang}`)
        ]);
        const arData=await arRes.json();
        const trData=await trRes.json();
        if(arData.code===200){
            curAyahs=arData.data.ayahs;
            renderJuzAyahs();
        }
        if(trData.code===200){
            curTrans=trData.data.ayahs;
            renderTrans();
        }
    }catch(e){
        document.getElementById('ayWrap').innerHTML='<div class="ldg"><span style="color:#c0392b">❌ خطأ في التحميل</span></div>';
    }
}

// ════════════════════════════════════════
// LANGUAGE CHANGE
// ════════════════════════════════════════
function changeLang(){
    curLang=document.getElementById('langSel').value;
    if(curSurah) fetchTrans(curSurah.n);
}

// ════════════════════════════════════════
// SEARCH
// ════════════════════════════════════════
let schTimer;
function doSearch(e){
    clearTimeout(schTimer);
    const q=document.getElementById('schInp').value.trim();
    if(q.length<2){document.getElementById('schRes').innerHTML='';return;}

    // Search surah names first
    let h='';
    S.filter(s=>s.a.includes(q)||String(s.n)===q).forEach(s=>{
        h+=`<div class="sch-item" onclick="loadSurah(${s.n})">📖 <b>سورة ${s.a}</b> (${s.n}) - ${s.t} - ${s.c} آية</div>`;
    });

    // API search (debounced)
    schTimer=setTimeout(async()=>{
        try{
            const res=await fetch(`https://api.alquran.cloud/v1/search/${encodeURIComponent(q)}/all/quran-uthmani`);
            const data=await res.json();
            if(data.code===200 && data.data.matches){
                data.data.matches.slice(0,30).forEach(m=>{
                    h+=`<div class="sch-item" onclick="loadSurah(${m.surah.number})">
                        <b>سورة ${m.surah.name} [${m.numberInSurah}]</b><br>
                        <span style="font-family:var(--fq);font-size:16px">${m.text}</span></div>`;
                });
            }
            document.getElementById('schRes').innerHTML=h||'<p style="padding:20px;text-align:center;color:var(--tx3)">لا توجد نتائج</p>';
        }catch(e){
            document.getElementById('schRes').innerHTML=h||'<p style="padding:20px;text-align:center;color:var(--tx3)">خطأ في البحث</p>';
        }
    },500);

    document.getElementById('schRes').innerHTML=h;
}

// ════════════════════════════════════════
// CONTEXT MENU
// ════════════════════════════════════════
function showCtx(e,num){
    e.stopPropagation();
    selAyNum=num;
    const ctx=document.getElementById('ctxMenu');
    ctx.classList.add('show');
    const r=e.target.getBoundingClientRect();
    let top=r.bottom+4,left=r.left;
    if(top+40>window.innerHeight) top=r.top-40;
    if(left+200>window.innerWidth) left=window.innerWidth-210;
    ctx.style.top=top+'px';ctx.style.left=left+'px';
}

function playSelAy(){
    document.getElementById('ctxMenu').classList.remove('show');
    if(!curSurah||!selAyNum) return;
    playIdx=curAyahs.findIndex(a=>a.numberInSurah===selAyNum);
    if(playIdx>=0) playCurAy();
}

function showSelTafsir(){
    document.getElementById('ctxMenu').classList.remove('show');
    switchTab('tafsir',document.querySelectorAll('.ltab')[1]);
    const el=document.getElementById('tf-'+selAyNum);
    if(el){el.scrollIntoView({behavior:'smooth',block:'center'});el.classList.add('hl');
        setTimeout(()=>el.classList.remove('hl'),2000);}
}

function copySelAy(){
    document.getElementById('ctxMenu').classList.remove('show');
    const ay=curAyahs.find(a=>a.numberInSurah===selAyNum);
    if(!ay) return;
    const txt=`${ay.text} ﴿${selAyNum}﴾ - سورة ${curSurah.a}`;
    navigator.clipboard.writeText(txt).then(()=>alert('تم نسخ الآية')).catch(()=>{
        const ta=document.createElement('textarea');ta.value=txt;
        document.body.appendChild(ta);ta.select();document.execCommand('copy');
        document.body.removeChild(ta);alert('تم نسخ الآية');
    });
}

// ════════════════════════════════════════
// HIGHLIGHT AYAH (sync panels)
// ════════════════════════════════════════
function hlAy(num){
    // Highlight in Arabic panel
    document.querySelectorAll('.ay-t.playing').forEach(e=>e.classList.remove('playing'));
    const arEl=document.getElementById('ay-'+num);
    if(arEl){arEl.classList.add('playing');arEl.scrollIntoView({behavior:'smooth',block:'center'});}

    // Highlight in translation
    document.querySelectorAll('.tr-ay.hl').forEach(e=>e.classList.remove('hl'));
    const trEl=document.getElementById('tr-'+num);
    if(trEl){trEl.classList.add('hl');trEl.scrollIntoView({behavior:'smooth',block:'center'});}
}

// ════════════════════════════════════════
// AUDIO
// ════════════════════════════════════════
function getAuUrl(sNum,aNum){
    const rc=document.getElementById('reciterSel').value;
    return`https://everyayah.com/data/${rc}/${String(sNum).padStart(3,'0')}${String(aNum).padStart(3,'0')}.mp3`;
}

function playCurAy(){
    if(playIdx<0||playIdx>=curAyahs.length) return;
    const ay=curAyahs[playIdx];
    const sn=curSurah?curSurah.n:ay.surah?.number;
    audio.src=getAuUrl(sn,ay.numberInSurah);
    audio.play().catch(e=>console.log(e));
    isPlay=true;updPPBtn();
    hlAy(ay.numberInSurah);
    document.getElementById('plSn').textContent=curSurah?'سورة '+curSurah.a:'القرآن الكريم';
    document.getElementById('plAy').textContent='الآية '+ay.numberInSurah;
}

function playAyDirect(sNum,aNum){
    if(!curSurah) curSurah=S.find(s=>s.n===sNum);
    playIdx=curAyahs.findIndex(a=>a.numberInSurah===aNum&&(a.surah?a.surah.number===sNum:true));
    if(playIdx>=0) playCurAy();
}

function togglePP(){
    if(!audio.src||audio.src===''){
        if(curAyahs.length>0){playIdx=0;playCurAy();}return;
    }
    if(isPlay){audio.pause();isPlay=false;}
    else{audio.play().catch(e=>console.log(e));isPlay=true;}
    updPPBtn();
}

function stopAu(){audio.pause();audio.src='';isPlay=false;playIdx=0;updPPBtn();
    document.querySelectorAll('.ay-t.playing').forEach(e=>e.classList.remove('playing'));
    document.querySelectorAll('.tr-ay.hl').forEach(e=>e.classList.remove('hl'));
    document.getElementById('prgFill').style.width='0%';
    document.getElementById('curT').textContent='0:00';document.getElementById('durT').textContent='0:00';
}

function nextAyAudio(){if(playIdx<curAyahs.length-1){playIdx++;playCurAy();}}
function prevAyAudio(){if(playIdx>0){playIdx--;playCurAy();}}

function onEnd(){
    if(isRpt){audio.currentTime=0;audio.play();return;}
    if(playIdx<curAyahs.length-1){playIdx++;playCurAy();}
    else{isPlay=false;updPPBtn();}
}

function toggleRp(){isRpt=!isRpt;
    const b=document.getElementById('rpBtn');
    b.style.background=isRpt?'var(--gdl)':'';b.style.color=isRpt?'var(--pr)':'';
}

function changeReciter(){
    curReciter=document.getElementById('reciterSel').value;
    document.getElementById('recSel2').value=curReciter;
    if(isPlay) playCurAy();
}
function syncReciter(v){
    document.getElementById('reciterSel').value=v;
    curReciter=v;if(isPlay) playCurAy();
}

function updPrg(){
    if(audio.duration){
        document.getElementById('prgFill').style.width=(audio.currentTime/audio.duration*100)+'%';
        document.getElementById('curT').textContent=fmtT(audio.currentTime);
    }
}

function seekAu(e){
    if(!audio.duration) return;
    const bar=e.currentTarget,r=bar.getBoundingClientRect();
    const pct=(e.clientX-r.left)/r.width;
    audio.currentTime=pct*audio.duration;
}

function updPPBtn(){document.getElementById('ppBtn').textContent=isPlay?'⏸':'▶';}
function fmtT(s){if(!s||isNaN(s))return'0:00';const m=Math.floor(s/60),sc=Math.floor(s%60);return m+':'+(sc<10?'0':'')+sc;}

// ════════════════════════════════════════
// UI HELPERS
// ════════════════════════════════════════
function switchTab(id,btn){
    document.querySelectorAll('.tab-c').forEach(e=>e.classList.remove('act'));
    document.querySelectorAll('.ltab').forEach(e=>e.classList.remove('act'));
    document.getElementById('tab-'+id).classList.add('act');
    if(btn) btn.classList.add('act');
}

function navSurah(d){
    if(!curSurah) return;
    const nx=curSurah.n+d;
    if(nx>=1&&nx<=114) loadSurah(nx);
}

function chgFont(d){
    fontSize=Math.max(16,Math.min(48,fontSize+d));
    document.documentElement.style.setProperty('--qs',fontSize+'px');
    document.getElementById('fontLbl').textContent=fontSize;
    localStorage.setItem('fs',fontSize);
}

function toggleTheme(){
    const cur=document.documentElement.getAttribute('data-t');
    applyTheme(cur==='dark'?'light':'dark');
}
function applyTheme(t){
    if(t==='dark') document.documentElement.setAttribute('data-t','dark');
    else document.documentElement.removeAttribute('data-t');
    localStorage.setItem('thm',t);
}

function toggleLP(){
    const lp=document.getElementById('leftPanel');
    lp.classList.toggle('open');
}

function showMobPanel(p){
    const btns=document.querySelectorAll('.mob-tabs button');
    if(p==='quran'){
        btns[0].classList.add('act');btns[1].classList.remove('act');
        document.getElementById('leftPanel').classList.remove('open');
    }else{
        btns[1].classList.add('act');btns[0].classList.remove('act');
        document.getElementById('leftPanel').classList.add('open');
    }
}

function errMsg(num){
    return`<div class="ldg"><span style="color:#c0392b">❌ خطأ في التحميل<br>
    <button class="s-nb" style="margin-top:10px" onclick="loadSurah(${num})">إعادة المحاولة</button></span></div>`;
}
</script>
</body>
</html>
