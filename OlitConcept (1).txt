<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Olit Concept – The Phone Hub</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;800&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box}
:root{
  --red:#D31A1A;--rl:rgba(211,26,26,0.08);--rb:rgba(211,26,26,0.25);
  --bg:#fff;--bg2:#F8F8F8;--bg3:#F2F2F2;--bg4:#EBEBEB;
  --tx:#111;--tx2:#444;--tx3:#777;
  --bd:#E5E5E5;--sh:0 2px 20px rgba(0,0,0,0.07);--shl:0 8px 40px rgba(0,0,0,0.11);
}
html{scroll-behavior:smooth}
body{background:#fff;color:var(--tx);font-family:'Inter',sans-serif;overflow-x:hidden}
::-webkit-scrollbar{width:4px}::-webkit-scrollbar-thumb{background:var(--red);border-radius:2px}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:100;display:flex;align-items:center;justify-content:space-between;padding:0 5%;height:70px;background:rgba(255,255,255,0.96);backdrop-filter:blur(16px);border-bottom:1px solid var(--bd);box-shadow:0 1px 14px rgba(0,0,0,0.06)}
.logo-nav{display:flex;align-items:center;gap:10px;text-decoration:none}
.logo-nav img{height:46px;width:auto;object-fit:contain;border-radius:4px}
nav ul{display:flex;gap:26px;list-style:none}
nav ul a{color:var(--tx2);text-decoration:none;font-size:13px;font-weight:500;transition:color .2s}
nav ul a:hover{color:var(--red)}
.nav-cta{background:var(--red);color:#fff;border:none;padding:10px 20px;border-radius:6px;font-size:13px;font-weight:600;cursor:pointer;text-decoration:none;box-shadow:0 2px 12px rgba(211,26,26,0.3);transition:opacity .2s}
.nav-cta:hover{opacity:0.87}

/* HERO */
#hero{min-height:100vh;display:grid;grid-template-columns:1fr 1fr;padding-top:70px;overflow:hidden}
.hero-left{padding:70px 5% 70px 6%;display:flex;flex-direction:column;justify-content:center;background:#fff}
.hero-right{position:relative;overflow:hidden;min-height:500px}
.hero-right img{width:100%;height:100%;object-fit:cover;object-position:center top;display:block}
.hero-right::after{content:'';position:absolute;inset:0;background:linear-gradient(90deg,rgba(255,255,255,0.55) 0%,transparent 40%)}
.hero-logo{height:72px;width:auto;object-fit:contain;margin-bottom:20px;display:block;border-radius:6px}
.hero-badge{display:inline-flex;align-items:center;gap:8px;background:var(--rl);border:1px solid var(--rb);color:var(--red);font-size:11px;font-weight:700;letter-spacing:2px;text-transform:uppercase;padding:6px 16px;border-radius:40px;margin-bottom:22px;width:fit-content}
.bdot{width:6px;height:6px;background:var(--red);border-radius:50%;animation:pulse 1.8s infinite}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.4;transform:scale(1.4)}}
h1{font-family:'Playfair Display',serif;font-size:clamp(32px,4vw,56px);line-height:1.07;color:var(--tx);margin-bottom:14px;font-weight:800}
h1 .red{color:var(--red)}
.hero-desc{font-size:15px;color:var(--tx2);line-height:1.75;margin-bottom:20px;max-width:460px}
.tagline{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:32px}
.tpill{background:var(--rl);border:1px solid var(--rb);color:var(--red);font-size:11px;font-weight:700;letter-spacing:1px;text-transform:uppercase;padding:5px 13px;border-radius:20px}
.hbtns{display:flex;gap:12px;flex-wrap:wrap;margin-bottom:40px}
.btn-p{background:var(--red);color:#fff;padding:13px 28px;border-radius:8px;font-size:14px;font-weight:600;border:none;cursor:pointer;text-decoration:none;display:inline-block;transition:all .2s;box-shadow:0 4px 18px rgba(211,26,26,0.3)}
.btn-p:hover{opacity:.87;transform:translateY(-1px)}
.btn-o{background:transparent;color:var(--red);padding:13px 28px;border-radius:8px;font-size:14px;font-weight:600;border:2px solid var(--red);cursor:pointer;text-decoration:none;display:inline-block;transition:all .2s}
.btn-o:hover{background:var(--rl)}
.hstats{display:flex;gap:28px;padding-top:28px;border-top:1px solid var(--bd);flex-wrap:wrap}
.sn{font-size:24px;font-weight:800;color:var(--tx)}.sn span{color:var(--red)}
.sl{font-size:10px;color:var(--tx3);letter-spacing:1px;text-transform:uppercase;margin-top:2px}

/* BRAND BANNER */
#brand-banner{height:340px;overflow:hidden;position:relative}
#brand-banner img{width:100%;height:100%;object-fit:cover;object-position:center 30%}
#brand-banner::after{content:'';position:absolute;inset:0;background:linear-gradient(0deg,rgba(0,0,0,0.6) 0%,rgba(0,0,0,0.1) 60%,transparent)}
.blabel{position:absolute;bottom:32px;left:5%;color:#fff;z-index:2}
.blabel h2{font-family:'Playfair Display',serif;font-size:34px;font-weight:800;text-shadow:0 2px 8px rgba(0,0,0,0.5)}
.blabel p{font-size:14px;color:rgba(255,255,255,0.8);margin-top:6px;letter-spacing:1px}

/* SECTIONS */
section{padding:90px 5%}
.slabel{font-size:11px;font-weight:700;letter-spacing:3px;text-transform:uppercase;color:var(--red);margin-bottom:12px}
.stitle{font-family:'Playfair Display',serif;font-size:clamp(24px,3.5vw,40px);line-height:1.12;margin-bottom:14px;color:var(--tx)}
.sdesc{font-size:15px;color:var(--tx2);line-height:1.72;max-width:540px}
.ctr{text-align:center}.ctr .sdesc{margin:0 auto}

/* SERVICES */
#services{background:var(--bg2)}
.sgrid{display:grid;grid-template-columns:repeat(auto-fit,minmax(210px,1fr));gap:1px;background:var(--bd);margin-top:50px;border:1px solid var(--bd);border-radius:14px;overflow:hidden}
.sc{background:#fff;padding:32px 24px;position:relative;transition:all .25s}
.sc:hover{background:var(--rl)}
.sc::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:var(--red);transform:scaleX(0);transition:transform .3s;transform-origin:left}
.sc:hover::before{transform:scaleX(1)}
.sico{width:48px;height:48px;background:var(--rl);border:1px solid var(--rb);border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:20px;margin-bottom:18px}
.stit{font-size:15px;font-weight:700;margin-bottom:8px}
.sdes{font-size:13px;color:var(--tx2);line-height:1.6}
.sprc{font-size:11px;color:var(--red);font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-top:12px}

/* ABOUT */
#about{background:#fff}
.agrid{display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:center}
.aimg{border-radius:16px;overflow:hidden;box-shadow:var(--shl);border:1px solid var(--bd)}
.aimg img{width:100%;height:430px;object-fit:cover;display:block}
.brow{display:flex;flex-wrap:wrap;gap:8px;margin-top:22px}
.ab{background:var(--rl);border:1px solid var(--rb);color:var(--red);font-size:11px;font-weight:700;letter-spacing:1px;text-transform:uppercase;padding:6px 14px;border-radius:4px}

/* WHY */
#why{background:var(--bg2)}
.wgrid{display:grid;grid-template-columns:1fr 1fr;gap:56px;align-items:center}
.wcards{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-top:8px}
.wcard{background:#fff;border:1px solid var(--bd);border-radius:10px;padding:22px 18px;transition:border-color .25s;box-shadow:var(--sh)}
.wcard:hover{border-color:var(--rb)}
.wnum{font-size:26px;font-weight:800;color:var(--red);opacity:.2;font-family:'Playfair Display',serif;margin-bottom:6px}
.wcard h3{font-size:13px;font-weight:700;margin-bottom:5px}
.wcard p{font-size:12px;color:var(--tx2);line-height:1.6}
.wimg{border-radius:16px;overflow:hidden;box-shadow:var(--shl);border:1px solid var(--bd)}
.wimg img{width:100%;height:460px;object-fit:cover;display:block}

/* GALLERY */
#gallery{display:grid;grid-template-columns:1fr 1fr 1fr;height:280px;overflow:hidden}
.gi{overflow:hidden;position:relative}
.gi img{width:100%;height:100%;object-fit:cover;transition:transform .5s}
.gi:hover img{transform:scale(1.06)}
.gi::after{content:'';position:absolute;inset:0;background:rgba(211,26,26,0);transition:background .3s}
.gi:hover::after{background:rgba(211,26,26,0.1)}

/* PRODUCTS */
#products{background:#fff}
.ptop{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:24px;flex-wrap:wrap;gap:14px}
.ftabs{display:flex;gap:3px;background:var(--bg3);padding:4px;border-radius:8px;border:1px solid var(--bd)}
.ft{padding:7px 15px;border-radius:5px;font-size:12px;font-weight:600;cursor:pointer;transition:all .2s;border:none;background:transparent;color:var(--tx3)}
.ft.active{background:var(--red);color:#fff;box-shadow:0 2px 10px rgba(211,26,26,0.3)}
.ft:not(.active):hover{color:var(--red);background:var(--rl)}
.pgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(185px,1fr));gap:16px}
.pc{background:#fff;border:1px solid var(--bd);border-radius:12px;overflow:hidden;transition:all .25s;box-shadow:var(--sh)}
.pc:hover{transform:translateY(-3px);border-color:var(--rb);box-shadow:var(--shl)}
.pimg{height:140px;background:linear-gradient(135deg,var(--bg3),var(--bg4));display:flex;align-items:center;justify-content:center;font-size:44px;border-bottom:1px solid var(--bd);position:relative}
.pbadge{position:absolute;top:8px;right:8px;background:var(--red);color:#fff;font-size:9px;font-weight:700;letter-spacing:1px;text-transform:uppercase;padding:3px 8px;border-radius:4px}
.pinfo{padding:14px}
.pname{font-size:13px;font-weight:700;margin-bottom:3px}
.pspec{font-size:11px;color:var(--tx3);margin-bottom:10px}
.pprice{font-size:15px;font-weight:800;color:var(--red)}
.pcta{display:block;width:100%;padding:8px;background:transparent;border:1.5px solid var(--rb);border-radius:6px;color:var(--red);font-size:11px;font-weight:700;text-transform:uppercase;cursor:pointer;transition:all .2s;margin-top:8px}
.pcta:hover{background:var(--red);color:#fff}

/* SHARED FORM STYLES */
.fcard{background:#fff;border:1px solid var(--bd);border-radius:16px;padding:48px;margin-top:44px;box-shadow:var(--shl);position:relative;overflow:hidden}
.fcard::before{content:'';position:absolute;top:0;left:0;right:0;height:4px}
.fcard.red-top::before{background:linear-gradient(90deg,var(--red),#ff6b6b,var(--red))}
.fcard.orange-top::before{background:linear-gradient(90deg,#f97316,#fbbf24,#f97316)}
.fgrid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-top:24px}
.fg{display:flex;flex-direction:column;gap:6px}
.fg.full{grid-column:1/-1}
.fg label{font-size:11px;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;color:var(--tx3)}
.fg input,.fg select,.fg textarea{background:var(--bg2);border:1.5px solid var(--bd);border-radius:8px;padding:11px 14px;font-size:14px;color:var(--tx);font-family:'Inter',sans-serif;outline:none;transition:border-color .2s}
.fg input:focus,.fg select:focus,.fg textarea:focus{border-color:var(--red);background:#fff}
.fg select{appearance:none;cursor:pointer}
.fg textarea{resize:vertical;min-height:88px}
.srow{grid-column:1/-1;display:flex;gap:14px;align-items:center;flex-wrap:wrap}
.snote{font-size:12px;color:var(--tx3)}
.smsg{display:none;margin-top:14px;padding:13px 18px;border-radius:8px;font-size:13px;font-weight:500}
.smsg.green{background:rgba(34,197,94,0.08);border:1px solid rgba(34,197,94,0.3);color:#16a34a}
.smsg.orange{background:rgba(249,115,22,0.08);border:1px solid rgba(249,115,22,0.3);color:#ea580c}
.avrow{display:flex;align-items:center;gap:10px;margin-bottom:8px}
.avdot{width:8px;height:8px;background:#22c55e;border-radius:50%;animation:pulse 1.8s infinite}
.avtext{font-size:12px;color:#16a34a;font-weight:700;letter-spacing:1px;text-transform:uppercase}

/* COMPLAINT SECTION */
#complaints{background:#fff}
.cmp-inner{max-width:820px;margin:0 auto}
.cmp-header{display:flex;align-items:center;gap:16px;margin-bottom:8px}
.cmp-icon{width:56px;height:56px;background:rgba(249,115,22,0.1);border:1px solid rgba(249,115,22,0.3);border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:24px;flex-shrink:0}
.rating-row{display:flex;gap:8px;margin-top:4px}
.star{font-size:26px;cursor:pointer;transition:transform .15s;filter:grayscale(1);opacity:.4}
.star.active,.star:hover{filter:none;opacity:1;transform:scale(1.15)}
.rating-label{font-size:12px;color:var(--tx3);margin-top:6px;height:16px}
.priority-chips{display:flex;gap:8px;flex-wrap:wrap;margin-top:4px}
.pchip{padding:7px 14px;border-radius:20px;font-size:12px;font-weight:600;cursor:pointer;border:1.5px solid var(--bd);background:#fff;color:var(--tx2);transition:all .2s}
.pchip:hover{border-color:var(--rb)}
.pchip.sel-low{background:#dcfce7;border-color:#86efac;color:#16a34a}
.pchip.sel-medium{background:#fef9c3;border-color:#fde047;color:#a16207}
.pchip.sel-high{background:#fee2e2;border-color:#fca5a5;color:#dc2626}
.pchip.sel-urgent{background:#fce7f3;border-color:#f9a8d4;color:#be185d}
.tickets{margin-top:40px}
.tickets h3{font-size:13px;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(--tx3);margin-bottom:16px;padding-bottom:10px;border-bottom:1px solid var(--bd)}
#ticket-list{display:flex;flex-direction:column;gap:12px}
.ticket{background:var(--bg2);border:1px solid var(--bd);border-radius:10px;padding:16px 20px;display:flex;align-items:flex-start;gap:14px}
.tkt-badge{padding:4px 10px;border-radius:20px;font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:1px;flex-shrink:0;margin-top:2px}
.tkt-open{background:#fee2e2;color:#dc2626}
.tkt-resolved{background:#dcfce7;color:#16a34a}
.tkt-info{flex:1}
.tkt-title{font-size:13px;font-weight:700;color:var(--tx);margin-bottom:3px}
.tkt-meta{font-size:11px;color:var(--tx3)}
.empty-tickets{text-align:center;padding:32px;color:var(--tx3);font-size:14px}

/* REPAIR */
#repair{background:var(--bg2)}
.rinner{max-width:800px;margin:0 auto}

/* LOCATIONS */
#locations{background:#fff}
.lgrid{display:grid;grid-template-columns:1fr 1fr;gap:18px;margin-top:44px}
.lcard{background:var(--bg2);border:1px solid var(--bd);border-radius:12px;padding:0;overflow:hidden;transition:all .25s;box-shadow:var(--sh)}
.lcard:hover{border-color:var(--rb);box-shadow:var(--shl)}
.lcard img{width:100%;height:180px;object-fit:cover;display:block}
.lcard-body{padding:22px}
.ltag{display:inline-block;background:var(--rl);border:1px solid var(--rb);color:var(--red);font-size:10px;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;padding:4px 12px;border-radius:4px;margin-bottom:10px}
.lcity{font-size:18px;font-weight:700;margin-bottom:6px}
.laddr{font-size:13px;color:var(--tx2);line-height:1.6;margin-bottom:14px}
.lcons{display:flex;flex-direction:column;gap:8px}
.lline{display:flex;align-items:center;gap:10px;font-size:13px;color:var(--tx2)}
.lico{width:28px;height:28px;background:var(--rl);border:1px solid var(--rb);border-radius:6px;display:flex;align-items:center;justify-content:center;font-size:13px;flex-shrink:0}

/* CONTACT */
#contact{background:var(--bg2);text-align:center}
.cinner{max-width:620px;margin:0 auto}
.socrow{display:flex;gap:10px;justify-content:center;margin-top:30px;flex-wrap:wrap}
.socbtn{display:flex;align-items:center;gap:9px;background:#fff;border:1px solid var(--bd);border-radius:8px;padding:11px 18px;text-decoration:none;color:var(--tx);font-size:13px;font-weight:600;transition:all .25s;box-shadow:var(--sh)}
.socbtn:hover{border-color:var(--rb);color:var(--red);background:var(--rl)}
.ceostrip{margin-top:36px;padding:22px 26px;background:#fff;border:1px solid var(--bd);border-radius:12px;display:flex;align-items:center;gap:18px;text-align:left;box-shadow:var(--sh)}
.ceoav{width:50px;height:50px;border-radius:50%;background:var(--red);display:flex;align-items:center;justify-content:center;font-size:17px;font-weight:700;color:#fff;flex-shrink:0}
.ceoname{font-size:15px;font-weight:700}
.ceorole{font-size:11px;color:var(--red);font-weight:700;letter-spacing:.5px;text-transform:uppercase;margin-top:2px}
.ceoemail{font-size:12px;color:var(--tx3);margin-top:3px}

/* FOOTER */
footer{background:#111;padding:32px 5%;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:14px}
.flogo{height:34px;width:auto;object-fit:contain;filter:brightness(0) invert(1);border-radius:4px}
.ftxt{font-size:12px;color:rgba(255,255,255,0.4)}
.fnums{display:flex;gap:14px;flex-wrap:wrap}
.fnum{font-size:12px;color:rgba(255,255,255,0.6);font-weight:500}
.rstrip{height:4px;background:linear-gradient(90deg,var(--red),#ff6b6b,var(--red))}

/* FLOAT */
.wafloat{position:fixed;bottom:28px;right:28px;z-index:200;width:54px;height:54px;background:#25D366;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:26px;box-shadow:0 4px 20px rgba(37,211,102,0.4);text-decoration:none;transition:transform .2s}
.wafloat:hover{transform:scale(1.1)}

/* REVEAL */
.reveal{opacity:0;transform:translateY(22px);transition:opacity .65s ease,transform .65s ease}
.reveal.visible{opacity:1;transform:none}

@media(max-width:900px){
  #hero{grid-template-columns:1fr}.hero-right{display:none}
  .agrid,.wgrid{grid-template-columns:1fr}
  .wcards{grid-template-columns:1fr 1fr}
  nav ul{display:none}
  .fgrid{grid-template-columns:1fr}
  .lgrid{grid-template-columns:1fr}
  #gallery{grid-template-columns:1fr 1fr}
  footer{flex-direction:column;text-align:center}
  .ceostrip{flex-direction:column;text-align:center}
  .fcard{padding:28px 20px}
}
</style>
</head>
<body>

<a href="https://wa.me/2348130060812" class="wafloat" target="_blank">💬</a>

<!-- NAV -->
<nav>
  <a href="#" class="logo-nav">
    <img src="https://i.ibb.co/XZxWmTpq/IMG-20260602-WA0010.jpg" alt="Olit Concept Logo">
  </a>
  <ul>
    <li><a href="#services">Services</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#products">Phones</a></li>
    <li><a href="#repair">Book Repair</a></li>
    <li><a href="#complaints">Complaints</a></li>
    <li><a href="#locations">Locations</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#repair" class="nav-cta">Book a Repair</a>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-left reveal">
    <img class="hero-logo" src="https://i.ibb.co/XZxWmTpq/IMG-20260602-WA0010.jpg" alt="Olit Concept">
    <div class="hero-badge"><span class="bdot"></span>Nigeria's Premier Phone Hub</div>
    <h1>We Fix. We Buy.<br>We Sell. <span class="red">We Swap.</span></h1>
    <p class="hero-desc">Fast, reliable and affordable phone repairs at Olit Concept — Nigeria's trusted phone hub with locations in Ile-Ife and Abuja.</p>
    <div class="tagline">
      <span class="tpill">Screen Repair</span>
      <span class="tpill">Battery</span>
      <span class="tpill">Water Damage</span>
      <span class="tpill">Unlock</span>
    </div>
    <div class="hbtns">
      <a href="#repair" class="btn-p">📅 Book a Repair</a>
      <a href="#products" class="btn-o">Browse Phones</a>
    </div>
    <div class="hstats">
      <div><div class="sn">5K<span>+</span></div><div class="sl">Repairs Done</div></div>
      <div><div class="sn">2<span>+</span></div><div class="sl">Locations</div></div>
      <div><div class="sn">1hr</div><div class="sl">Avg Turnaround</div></div>
      <div><div class="sn">90<span>d</span></div><div class="sl">Warranty</div></div>
    </div>
  </div>
  <div class="hero-right">
    <img src="https://i.ibb.co/dwM0Gz4V/IMG-20260602-WA0008.jpg" alt="Olit Concept Store">
  </div>
</section>

<!-- BRAND BANNER -->
<div id="brand-banner">
  <img src="https://i.ibb.co/cHzPLT9/IMG-20260602-WA0011.jpg" alt="Olit Concept Branding">
  <div class="blabel">
    <h2>The Phone Hub</h2>
    <p>We Fix / We Buy / We Sell &amp; We Swap</p>
  </div>
</div>

<!-- SERVICES -->
<section id="services">
  <div class="reveal ctr">
    <div class="slabel">What We Do</div>
    <div class="stitle">Expert Services, Unbeatable Speed</div>
  </div>
  <div class="sgrid reveal">
    <div class="sc"><div class="sico">🔧</div><div class="stit">Screen Repair</div><div class="sdes">OEM-quality displays for iPhones, Samsung, Tecno, Infinix & more.</div><div class="sprc">From ₦8,000</div></div>
    <div class="sc"><div class="sico">🔋</div><div class="stit">Battery Replacement</div><div class="sdes">Genuine batteries restored in 30 minutes. Full capacity guaranteed.</div><div class="sprc">From ₦5,500</div></div>
    <div class="sc"><div class="sico">💧</div><div class="stit">Water Damage</div><div class="sdes">Emergency recovery with ultrasonic cleaning and board-level repair.</div><div class="sprc">From ₦12,000</div></div>
    <div class="sc"><div class="sico">📱</div><div class="stit">Buy & Sell</div><div class="sdes">Best market rates for your device. New and quality refurbished phones in stock.</div><div class="sprc">Best Market Rate</div></div>
    <div class="sc"><div class="sico">🔄</div><div class="stit">Phone Swap</div><div class="sdes">Upgrade seamlessly — swap your current phone for something better.</div><div class="sprc">Fair Valuations</div></div>
    <div class="sc"><div class="sico">⚙️</div><div class="stit">Software & Unlock</div><div class="sdes">Factory unlock, OS flash, iCloud bypass, virus removal, data recovery.</div><div class="sprc">From ₦3,000</div></div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="agrid reveal">
    <div class="aimg"><img src="https://i.ibb.co/dwM0Gz4V/IMG-20260602-WA0008.jpg" alt="Olit Concept Store Interior"></div>
    <div>
      <div class="slabel">Our Store</div>
      <div class="stitle">Walk In,<br>Walk Out Fixed.</div>
      <p class="sdesc">Our stores are stocked wall-to-wall with premium devices and equipped with professional repair benches. Most repairs are done in under an hour — while you wait.</p>
      <div class="brow">
        <span class="ab">iPhones</span><span class="ab">Samsung</span><span class="ab">Infinix</span>
        <span class="ab">Tecno</span><span class="ab">Accessories</span><span class="ab">Repairs</span>
      </div>
    </div>
  </div>
</section>

<!-- WHY -->
<section id="why">
  <div class="wgrid reveal">
    <div>
      <div class="slabel">Why Choose Us</div>
      <div class="stitle">Fast. Honest.<br>Guaranteed.</div>
      <p class="sdesc" style="margin-bottom:22px">Thousands of Nigerians trust Olit Concept for their phone needs.</p>
      <div class="wcards">
        <div class="wcard"><div class="wnum">01</div><h3>Certified Technicians</h3><p>Expert staff trained across all major phone brands and models.</p></div>
        <div class="wcard"><div class="wnum">02</div><h3>Genuine Parts</h3><p>OEM-grade quality — no cheap substitutes, ever.</p></div>
        <div class="wcard"><div class="wnum">03</div><h3>90-Day Warranty</h3><p>Every repair backed by a full 90-day guarantee.</p></div>
        <div class="wcard"><div class="wnum">04</div><h3>No Hidden Fees</h3><p>Free diagnosis. Clear quote. What we say is what you pay.</p></div>
      </div>
    </div>
    <div class="wimg">
      <img src="https://i.ibb.co/wNN3KfQF/IMG-20260602-WA0006.jpg" alt="Phone Repair Service">
    </div>
  </div>
</section>

<!-- GALLERY -->
<div id="gallery">
  <div class="gi"><img src="https://i.ibb.co/84PmF62k/IMG-20260602-WA0007.jpg" alt="Olit Concept"></div>
  <div class="gi"><img src="https://i.ibb.co/cHzPLT9/IMG-20260602-WA0011.jpg" alt="Olit Concept Branding"></div>
  <div class="gi"><img src="https://i.ibb.co/wNN3KfQF/IMG-20260602-WA0006.jpg" alt="Phone Repair"></div>
</div>

<!-- PRODUCTS -->
<section id="products">
  <div class="ptop reveal">
    <div><div class="slabel">Our Inventory</div><div class="stitle">Premium Devices</div></div>
    <div class="ftabs">
      <button class="ft active" onclick="filterP('all',this)">All</button>
      <button class="ft" onclick="filterP('iphone',this)">iPhone</button>
      <button class="ft" onclick="filterP('android',this)">Android</button>
      <button class="ft" onclick="filterP('accessories',this)">Accessories</button>
    </div>
  </div>
  <div class="pgrid reveal" id="prod-grid"></div>
</section>

<!-- REPAIR BOOKING -->
<section id="repair">
  <div class="rinner">
    <div class="reveal ctr">
      <div class="slabel">Book Online</div>
      <div class="stitle">Schedule Your Repair</div>
      <p class="sdesc" style="margin:0 auto">Fill in your details and we'll confirm your slot within the hour.</p>
    </div>
    <div class="fcard red-top reveal">
      <div class="avrow"><div class="avdot"></div><span class="avtext">Available Now — Walk-ins Welcome</span></div>
      <p style="font-size:14px;color:var(--tx2)">Or call: <strong>08130060812 / 09161468759</strong></p>
      <div class="fgrid">
        <div class="fg"><label>Full Name *</label><input id="r-name" type="text" placeholder="e.g. Bolu Adeyemi"></div>
        <div class="fg"><label>Phone Number *</label><input id="r-phone" type="tel" placeholder="e.g. 0812 000 0000"></div>
        <div class="fg"><label>Device Model *</label><input id="r-device" type="text" placeholder="e.g. iPhone 13 Pro"></div>
        <div class="fg">
          <label>Issue Type *</label>
          <select id="r-issue">
            <option value="">Select issue...</option>
            <option>Cracked / Broken Screen</option>
            <option>Battery Not Charging</option>
            <option>Water Damage</option>
            <option>Software / Unlock Issue</option>
            <option>Camera Not Working</option>
            <option>Speaker / Mic Problem</option>
            <option>Phone Won't Turn On</option>
            <option>Other</option>
          </select>
        </div>
        <div class="fg">
          <label>Preferred Location *</label>
          <select id="r-loc">
            <option value="">Select branch...</option>
            <option>Mayfair, Ile-Ife — Osun State</option>
            <option>Dawaki, Abuja — FCT</option>
          </select>
        </div>
        <div class="fg"><label>Preferred Date</label><input id="r-date" type="date"></div>
        <div class="fg full"><label>Additional Notes</label><textarea id="r-notes" placeholder="Describe the issue in more detail (optional)..."></textarea></div>
        <div class="srow">
          <button class="btn-p" id="repair-btn" onclick="submitRepair()">📧 Submit Booking</button>
          <span class="snote">🔒 Your details are safe with us</span>
        </div>
      </div>
      <div class="smsg green" id="repair-msg">✅ Email client opening — please send the pre-filled email. We'll call you to confirm shortly!</div>
    </div>
  </div>
</section>

<!-- ✦ COMPLAINTS SECTION ✦ -->
<section id="complaints">
  <div class="cmp-inner">
    <div class="reveal">
      <div class="cmp-header">
        <div class="cmp-icon">📣</div>
        <div>
          <div class="slabel">Customer Feedback</div>
          <div class="stitle" style="margin-bottom:6px">File a Complaint</div>
        </div>
      </div>
      <p class="sdesc">We take every complaint seriously. Your feedback helps us serve you better. All complaints are reviewed within 24 hours.</p>
    </div>
    <div class="fcard orange-top reveal">
      <div style="display:flex;align-items:center;gap:10px;margin-bottom:16px">
        <span style="font-size:20px">⚠️</span>
        <p style="font-size:14px;color:var(--tx2)">Your complaint goes directly to management at <strong>olitconceptbusiness@gmail.com</strong></p>
      </div>

      <!-- STAR RATING -->
      <div class="fg" style="margin-bottom:18px">
        <label>Rate Your Experience *</label>
        <div class="rating-row" id="star-row">
          <span class="star" data-val="1">★</span>
          <span class="star" data-val="2">★</span>
          <span class="star" data-val="3">★</span>
          <span class="star" data-val="4">★</span>
          <span class="star" data-val="5">★</span>
        </div>
        <div class="rating-label" id="rating-label">Click to rate</div>
      </div>

      <!-- PRIORITY -->
      <div class="fg" style="margin-bottom:18px">
        <label>Priority Level *</label>
        <div class="priority-chips" id="priority-chips">
          <span class="pchip" data-p="Low" onclick="selectPriority(this)">🟢 Low</span>
          <span class="pchip" data-p="Medium" onclick="selectPriority(this)">🟡 Medium</span>
          <span class="pchip" data-p="High" onclick="selectPriority(this)">🔴 High</span>
          <span class="pchip" data-p="Urgent" onclick="selectPriority(this)">🚨 Urgent</span>
        </div>
      </div>

      <div class="fgrid">
        <div class="fg"><label>Full Name *</label><input id="c-name" type="text" placeholder="Your full name"></div>
        <div class="fg"><label>Phone Number *</label><input id="c-phone" type="tel" placeholder="e.g. 0812 000 0000"></div>
        <div class="fg"><label>Email Address</label><input id="c-email" type="email" placeholder="your@email.com"></div>
        <div class="fg">
          <label>Complaint Category *</label>
          <select id="c-cat">
            <option value="">Select category...</option>
            <option>Repair Quality</option>
            <option>Customer Service / Staff Conduct</option>
            <option>Pricing / Overcharge</option>
            <option>Delayed Repair</option>
            <option>Device Damage During Repair</option>
            <option>Wrong Parts Used</option>
            <option>Warranty / Refund Issue</option>
            <option>Missing Items / Accessories</option>
            <option>Other</option>
          </select>
        </div>
        <div class="fg">
          <label>Branch Involved *</label>
          <select id="c-branch">
            <option value="">Select branch...</option>
            <option>Mayfair, Ile-Ife — Osun State</option>
            <option>Dawaki, Abuja — FCT</option>
          </select>
        </div>
        <div class="fg"><label>Date of Incident</label><input id="c-date" type="date"></div>
        <div class="fg full"><label>Describe Your Complaint *</label><textarea id="c-desc" style="min-height:110px" placeholder="Please describe what happened in as much detail as possible..."></textarea></div>
        <div class="fg full"><label>Desired Resolution</label><textarea id="c-res" style="min-height:70px" placeholder="What outcome would you like? (e.g. refund, re-repair, apology...)"></textarea></div>
        <div class="srow">
          <button class="btn-p" id="complaint-btn" style="background:#f97316;box-shadow:0 4px 18px rgba(249,115,22,0.3)" onclick="submitComplaint()">📣 Submit Complaint</button>
          <span class="snote">📋 You'll receive a reference number by email</span>
        </div>
      </div>
      <div class="smsg orange" id="complaint-msg"></div>
    </div>

    <!-- TICKETS LOG -->
    <div class="tickets reveal">
      <h3>Recent Submissions <span id="ticket-count" style="color:var(--red)"></span></h3>
      <div id="ticket-list"><div class="empty-tickets">No complaints submitted yet in this session.</div></div>
    </div>
  </div>
</section>

<!-- LOCATIONS -->
<section id="locations">
  <div class="reveal ctr">
    <div class="slabel">Find Us</div>
    <div class="stitle">Two Locations, One Standard</div>
    <p class="sdesc">Walk in anytime — no appointment needed for most repairs.</p>
  </div>
  <div class="lgrid reveal">
    <div class="lcard">
      <img src="https://i.ibb.co/dwM0Gz4V/IMG-20260602-WA0008.jpg" alt="Ile-Ife Store">
      <div class="lcard-body">
        <div class="ltag">📍 Flagship Store</div>
        <div class="lcity">Ile-Ife, Osun State</div>
        <div class="laddr">Lawyer Oladapo Complex, besides Country Kitchen, Mayfair, Ile-Ife, Osun State, Nigeria.</div>
        <div class="lcons">
          <div class="lline"><div class="lico">📞</div>08130060812</div>
          <div class="lline"><div class="lico">📞</div>09161468759</div>
          <div class="lline"><div class="lico">✉️</div>olitconceptbusiness@gmail.com</div>
        </div>
      </div>
    </div>
    <div class="lcard">
      <img src="https://i.ibb.co/84PmF62k/IMG-20260602-WA0007.jpg" alt="Abuja Store">
      <div class="lcard-body">
        <div class="ltag">📍 Branch</div>
        <div class="lcity">Dawaki, Abuja — FCT</div>
        <div class="laddr">Dawaki, Federal Capital Territory, Abuja, Nigeria.</div>
        <div class="lcons">
          <div class="lline"><div class="lico">📞</div>08130060812</div>
          <div class="lline"><div class="lico">📞</div>09161468759</div>
          <div class="lline"><div class="lico">✉️</div>olitconceptbusiness@gmail.com</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="cinner reveal">
    <div class="slabel">Stay Connected</div>
    <div class="stitle">Follow Olit Concept</div>
    <p class="sdesc">Stay updated with new devices, repair tips and special deals.</p>
    <div class="socrow">
      <a href="https://www.tiktok.com/@olit.concept?_r=1&_t=ZS-96tiXB3kNfh" class="socbtn" target="_blank">🎵 TikTok</a>
      <a href="https://www.instagram.com/tayo__adelakin?igsh=MWJ6dnY0dWxpdmcxNQ%3D%3D&utm_source=qr" class="socbtn" target="_blank">📸 Instagram</a>
      <a href="mailto:olitconceptbusiness@gmail.com" class="socbtn">✉️ Email Us</a>
      <a href="https://wa.me/2348130060812" class="socbtn" target="_blank">💬 WhatsApp</a>
    </div>
    <div class="ceostrip reveal">
      <div class="ceoav">AA</div>
      <div>
        <div class="ceoname">Adelakin Ayuba A.</div>
        <div class="ceorole">Chief Executive Officer</div>
        <div class="ceoemail">olitconceptbusiness@gmail.com</div>
      </div>
    </div>
  </div>
</section>

<div class="rstrip"></div>
<footer>
  <img class="flogo" src="https://i.ibb.co/XZxWmTpq/IMG-20260602-WA0010.jpg" alt="Olit Concept">
  <span class="ftxt">© 2025 Olit Concept. The Phone Hub. All rights reserved.</span>
  <div class="fnums">
    <span class="fnum">📞 08130060812</span>
    <span class="fnum">📞 09161468759</span>
  </div>
</footer>

<script>
/* ── PRODUCTS ── */
const prods=[
  {n:"iPhone 15 Pro",s:"256GB · Titanium",p:"₦780,000",b:"New",c:"iphone",e:"📱"},
  {n:"iPhone 14",s:"128GB · Midnight",p:"₦520,000",b:"",c:"iphone",e:"📱"},
  {n:"iPhone 12",s:"64GB · Red · Refurb",p:"₦280,000",b:"Hot",c:"iphone",e:"📱"},
  {n:"iPhone XR",s:"64GB · White · Refurb",p:"₦185,000",b:"",c:"iphone",e:"📱"},
  {n:"Samsung S24",s:"256GB · Phantom Black",p:"₦620,000",b:"New",c:"android",e:"📲"},
  {n:"Infinix Note 40",s:"256GB · Titanium",p:"₦145,000",b:"",c:"android",e:"📲"},
  {n:"Tecno Camon 30",s:"128GB · Basalt",p:"₦118,000",b:"",c:"android",e:"📲"},
  {n:"Tempered Glass",s:"Universal · 2-Pack",p:"₦1,500",b:"",c:"accessories",e:"🛡️"},
  {n:"Fast Charger",s:"65W · USB-C",p:"₦8,500",b:"",c:"accessories",e:"⚡"},
];
function renderP(f){
  const g=document.getElementById('prod-grid');
  const items=f==='all'?prods:prods.filter(p=>p.c===f);
  g.innerHTML=items.map(p=>`<div class="pc"><div class="pimg">${p.e}${p.b?`<span class="pbadge">${p.b}</span>`:''}</div><div class="pinfo"><div class="pname">${p.n}</div><div class="pspec">${p.s}</div><div class="pprice">${p.p}</div><button class="pcta" onclick="inquire('${p.n}')">Inquire / Order</button></div></div>`).join('');
}
function filterP(cat,btn){
  document.querySelectorAll('.ft').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');renderP(cat);
}
function inquire(n){window.open(`https://wa.me/2348130060812?text=Hi%20Olit%20Concept!%20I%27m%20interested%20in%20the%20${encodeURIComponent(n)}.%20Is%20it%20available%3F`,'_blank')}

/* ── REPAIR BOOKING ── */
function submitRepair(){
  const v=id=>document.getElementById(id).value.trim();
  const name=v('r-name'),phone=v('r-phone'),device=v('r-device');
  const issue=document.getElementById('r-issue').value,loc=document.getElementById('r-loc').value;
  if(!name||!phone||!device||!issue||!loc){alert('Please fill in all required fields (*).');return;}
  const date=v('r-date'),notes=v('r-notes');
  const body=`New Repair Booking — Olit Concept%0A%0AName: ${encodeURIComponent(name)}%0APhone: ${encodeURIComponent(phone)}%0ADevice: ${encodeURIComponent(device)}%0AIssue: ${encodeURIComponent(issue)}%0ALocation: ${encodeURIComponent(loc)}%0ADate: ${encodeURIComponent(date||'Not specified')}%0ANotes: ${encodeURIComponent(notes||'None')}`;
  window.open(`mailto:olitconceptbusiness@gmail.com?subject=Repair%20Booking%20-%20${encodeURIComponent(name)}&body=${body}`);
  document.getElementById('repair-msg').style.display='block';
  const btn=document.getElementById('repair-btn');btn.textContent='✓ Submitted';btn.style.opacity='.6';btn.disabled=true;
}

/* ── STAR RATING ── */
let selectedRating=0;
const ratingLabels=['','😞 Very Poor','😕 Poor','😐 Average','😊 Good','😄 Excellent'];
document.querySelectorAll('.star').forEach(s=>{
  s.addEventListener('click',()=>{
    selectedRating=+s.dataset.val;
    document.querySelectorAll('.star').forEach((st,i)=>{st.classList.toggle('active',i<selectedRating)});
    document.getElementById('rating-label').textContent=ratingLabels[selectedRating];
  });
  s.addEventListener('mouseenter',()=>{
    const v=+s.dataset.val;
    document.querySelectorAll('.star').forEach((st,i)=>st.classList.toggle('active',i<v));
  });
  s.parentElement.addEventListener('mouseleave',()=>{
    document.querySelectorAll('.star').forEach((st,i)=>st.classList.toggle('active',i<selectedRating));
  });
});

/* ── PRIORITY CHIPS ── */
let selectedPriority='';
function selectPriority(el){
  document.querySelectorAll('.pchip').forEach(c=>{c.className='pchip'});
  const p=el.dataset.p;
  selectedPriority=p;
  const cls={Low:'sel-low',Medium:'sel-medium',High:'sel-high',Urgent:'sel-urgent'};
  el.classList.add(cls[p]||'');
}

/* ── COMPLAINTS ── */
let tickets=[];
function submitComplaint(){
  const v=id=>document.getElementById(id).value.trim();
  const name=v('c-name'),phone=v('c-phone'),email=v('c-email');
  const cat=document.getElementById('c-cat').value,branch=document.getElementById('c-branch').value;
  const date=v('c-date'),desc=v('c-desc'),res=v('c-res');
  if(!name||!phone||!cat||!branch||!desc){alert('Please fill in all required fields (*).');return;}
  if(!selectedRating){alert('Please rate your experience.');return;}
  if(!selectedPriority){alert('Please select a priority level.');return;}
  const ref='OC-'+Date.now().toString(36).toUpperCase().slice(-6);
  const body=
    `CUSTOMER COMPLAINT — Olit Concept%0A%0A` +
    `Reference: ${ref}%0A` +
    `Name: ${encodeURIComponent(name)}%0A` +
    `Phone: ${encodeURIComponent(phone)}%0A` +
    `Email: ${encodeURIComponent(email||'Not provided')}%0A` +
    `Rating: ${selectedRating}/5 stars%0A` +
    `Priority: ${selectedPriority}%0A` +
    `Category: ${encodeURIComponent(cat)}%0A` +
    `Branch: ${encodeURIComponent(branch)}%0A` +
    `Date of Incident: ${encodeURIComponent(date||'Not specified')}%0A%0A` +
    `Complaint:%0A${encodeURIComponent(desc)}%0A%0A` +
    `Desired Resolution:%0A${encodeURIComponent(res||'Not specified')}`;
  window.open(`mailto:olitconceptbusiness@gmail.com?subject=Customer%20Complaint%20[${ref}]%20-%20${encodeURIComponent(name)}&body=${body}`);

  // Add to ticket list
  tickets.unshift({ref,name,cat,branch,priority:selectedPriority,rating:selectedRating,status:'Open'});
  renderTickets();

  // Show success
  const msg=document.getElementById('complaint-msg');
  msg.style.display='block';
  msg.textContent=`✅ Complaint submitted! Your reference number is ${ref}. We'll respond within 24 hours.`;

  // Disable button
  const btn=document.getElementById('complaint-btn');btn.textContent='✓ Complaint Filed';btn.style.opacity='.6';btn.disabled=true;

  // Reset rating & priority visually
  selectedRating=0;selectedPriority='';
}

function renderTickets(){
  const list=document.getElementById('ticket-list');
  const cnt=document.getElementById('ticket-count');
  cnt.textContent=tickets.length?`(${tickets.length})`:'';
  if(!tickets.length){list.innerHTML='<div class="empty-tickets">No complaints submitted yet in this session.</div>';return;}
  list.innerHTML=tickets.map(t=>`
    <div class="ticket">
      <span class="tkt-badge tkt-${t.status==='Open'?'open':'resolved'}">${t.status}</span>
      <div class="tkt-info">
        <div class="tkt-title">${t.cat} — ${t.branch}</div>
        <div class="tkt-meta">Ref: <strong>${t.ref}</strong> &nbsp;·&nbsp; ${t.name} &nbsp;·&nbsp; Priority: ${t.priority} &nbsp;·&nbsp; Rating: ${'★'.repeat(t.rating)}${'☆'.repeat(5-t.rating)}</div>
      </div>
    </div>`).join('');
}

renderP('all');
const obs=new IntersectionObserver(es=>{es.forEach(e=>{if(e.isIntersecting)e.target.classList.add('visible')});},{threshold:0.08});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));
</script>
</body>
</html>
