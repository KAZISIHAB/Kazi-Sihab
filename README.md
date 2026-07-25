    <!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>Make Money — বট</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Hind+Siliguri:wght@400;500;600;700&family=Sora:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --emerald-950:#07211a;
    --emerald-900:#0b2f24;
    --emerald-800:#0f3d2e;
    --emerald-700:#155a41;
    --teal-400:#2fe0b5;
    --teal-300:#7ef2d4;
    --gold-400:#ffc94d;
    --gold-300:#ffe08a;
    --coral-500:#ff6a5c;
    --ivory:#f4efdf;
    --ivory-dim:#c9d6cd;
    --line:rgba(255,201,77,0.16);
    --safe-top: env(safe-area-inset-top, 0px);
    --safe-bottom: env(safe-area-inset-bottom, 0px);
  }
  *{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent;}
  html,body{height:100%;}
  body{
    font-family:'Hind Siliguri','Sora',system-ui,sans-serif;
    background:
      radial-gradient(circle at 15% -10%, #1a4a37 0%, transparent 45%),
      radial-gradient(circle at 110% 5%, #123d2c 0%, transparent 40%),
      linear-gradient(160deg, var(--emerald-950) 0%, #051a14 100%);
    color:var(--ivory);
    display:flex; justify-content:center;
    min-height:100vh;
  }
  body::before{
    content:"";
    position:fixed; inset:0;
    background-image:
      radial-gradient(1px 1px at 20px 30px, rgba(255,201,77,0.35) 0, transparent 100%),
      radial-gradient(1px 1px at 140px 90px, rgba(126,242,212,0.3) 0, transparent 100%),
      radial-gradient(1.5px 1.5px at 260px 40px, rgba(255,201,77,0.25) 0, transparent 100%),
      radial-gradient(1px 1px at 340px 160px, rgba(126,242,212,0.25) 0, transparent 100%);
    background-repeat:repeat; background-size:380px 220px;
    opacity:.55; pointer-events:none; z-index:0;
  }

  /* full phone-screen frame */
  .app-shell{
    width:100%; max-width:460px;
    min-height:100vh;
    display:flex; flex-direction:column;
    position:relative; z-index:1;
    background:linear-gradient(180deg, rgba(15,61,46,0.4), rgba(5,20,15,0.55));
  }

  /* ===== TOP BAR (like a bot header) ===== */
  .topbar{
    padding:calc(12px + var(--safe-top)) 16px 12px;
    display:flex; align-items:center; gap:11px;
    background:rgba(5,18,14,0.75);
    backdrop-filter:blur(14px); -webkit-backdrop-filter:blur(14px);
    border-bottom:1px solid var(--line);
    position:sticky; top:0; z-index:20;
  }
  .bot-avatar{
    width:42px;height:42px;border-radius:14px;
    background:conic-gradient(from 210deg, var(--gold-300), var(--gold-400), #b8860b, var(--gold-300));
    display:flex;align-items:center;justify-content:center;
    font-weight:800; color:#3a2a00; font-size:18px;
    box-shadow:0 4px 12px rgba(255,201,77,0.35);
    flex-shrink:0;
  }
  .bot-meta{flex:1; min-width:0;}
  .bot-name{
    font-family:'Sora',sans-serif; font-weight:800; font-size:16px;
    display:flex; align-items:center; gap:6px; color:var(--ivory);
  }
  .bot-name .verified{color:var(--teal-300); font-size:13px;}
  .bot-status{
    font-size:11.5px; color:var(--teal-300); font-weight:600;
    display:flex; align-items:center; gap:5px; margin-top:1px;
  }
  .dot-live{
    width:7px;height:7px;border-radius:50%; background:var(--teal-400);
    box-shadow:0 0 0 3px rgba(47,224,181,0.2);
    animation:pulse-dot 1.8s infinite;
  }
  @keyframes pulse-dot{0%,100%{opacity:1;}50%{opacity:.4;}}
  .topbar-action{
    width:38px;height:38px;border-radius:50%;
    background:rgba(255,255,255,0.06);
    display:flex;align-items:center;justify-content:center;
    color:var(--ivory-dim); font-size:15px; border:1px solid var(--line);
    cursor:pointer;
  }

  /* ===== SCROLL CONTENT ===== */
  .content{
    flex:1; padding:16px 14px 12px;
    padding-bottom:calc(96px + var(--safe-bottom));
  }

  /* greeting hero */
  .greet-hero{
    border-radius:26px; padding:18px 18px 20px;
    margin-bottom:14px;
    background:linear-gradient(135deg, #124430 0%, #0c3628 55%, #0a2e22 100%);
    border:1px solid var(--line);
    position:relative; overflow:hidden;
  }
  .greet-hero::after{
    content:""; position:absolute; top:-45%; right:-15%;
    width:190px;height:190px;border-radius:50%;
    background:radial-gradient(circle, rgba(255,201,77,0.16), transparent 70%);
  }
  .greet-line{
    display:flex; justify-content:space-between; align-items:flex-start; gap:10px;
  }
  .greet-text .hi{font-size:13px; color:var(--ivory-dim); font-weight:600;}
  .greet-text .name{
    font-family:'Sora',sans-serif; font-size:19px; font-weight:700; color:var(--ivory);
    margin-top:2px; display:flex; align-items:center; gap:6px;
  }
  .id-pill{
    font-size:11.5px;color:var(--ivory-dim);
    background:rgba(0,0,0,0.28);
    padding:3px 11px;border-radius:30px;
    display:inline-block;margin-top:6px;
    border:1px solid rgba(126,242,212,0.2);
  }
  .login-pill{
    background:linear-gradient(145deg, var(--teal-300), var(--teal-400));
    border:none;border-radius:40px;
    padding:9px 14px;font-weight:700;font-size:12px;
    color:var(--emerald-950); white-space:nowrap; cursor:pointer;
    box-shadow:0 6px 14px rgba(47,224,181,0.32);
    flex-shrink:0;
  }
  .login-pill:active{transform:scale(0.95);}

  .balance-block{margin-top:16px;}
  .balance-label{font-size:11.5px;letter-spacing:.6px;text-transform:uppercase;color:var(--ivory-dim);font-weight:600;}
  .balance-value{
    font-family:'Sora',sans-serif; font-size:36px; font-weight:800; margin-top:3px;
    background:linear-gradient(90deg, var(--gold-300), var(--gold-400) 60%, #ffb020);
    -webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;
    display:flex;align-items:baseline;gap:6px;
  }
  .balance-value small{font-size:13px;color:var(--ivory-dim);-webkit-text-fill-color:var(--ivory-dim);font-weight:600;}

  .progress-wrap{margin-top:13px;}
  .progress-labels{display:flex;justify-content:space-between;font-size:11px;color:var(--ivory-dim);margin-bottom:6px;}
  .progress-track{height:7px;border-radius:30px;background:rgba(0,0,0,0.35);overflow:hidden;border:1px solid rgba(255,255,255,0.05);}
  .progress-fill{height:100%;border-radius:30px;background:linear-gradient(90deg, var(--teal-400), var(--gold-400));width:84%;box-shadow:0 0 10px rgba(47,224,181,0.5);}

  /* quick action grid — bot main-menu style */
  .quick-title{
    font-size:13px; font-weight:700; color:var(--ivory-dim);
    margin:6px 4px 10px; display:flex; align-items:center; gap:6px;
  }
  .quick-title i{color:var(--gold-400);}
  .quick-grid{
    display:grid; grid-template-columns:repeat(4,1fr); gap:9px;
    margin-bottom:18px;
  }
  .quick-btn{
    background:rgba(5,20,15,0.55);
    border:1px solid var(--line); border-radius:18px;
    padding:12px 4px 10px; text-align:center; cursor:pointer;
    transition:transform .12s ease, background .12s ease;
  }
  .quick-btn:active{transform:scale(0.93); background:rgba(255,201,77,0.08);}
  .quick-btn .ic{
    width:38px;height:38px;border-radius:12px; margin:0 auto 6px;
    display:flex;align-items:center;justify-content:center; font-size:16px;
  }
  .quick-btn .lb{font-size:10.5px; color:var(--ivory-dim); font-weight:600; line-height:1.2;}
  .ic-gold{background:linear-gradient(135deg, var(--gold-300), var(--gold-400)); color:var(--emerald-950);}
  .ic-teal{background:linear-gradient(135deg, var(--teal-300), var(--teal-400)); color:var(--emerald-950);}
  .ic-coral{background:linear-gradient(135deg, #ff9d8f, var(--coral-500)); color:#3a0f0a;}
  .ic-lav{background:linear-gradient(135deg, #b39ddb, #8467c9); color:#1d1233;}

  /* stat mini row */
  .stats-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:16px;}
  .stat-card{background:rgba(5,20,15,0.55);border-radius:20px;padding:13px 10px;text-align:center;border:1px solid var(--line);}
  .stat-card i{color:var(--gold-400);font-size:15px;margin-bottom:4px;}
  .stat-card .value{font-family:'Sora',sans-serif;font-size:18px;font-weight:800;color:var(--ivory);}
  .stat-card .label{color:var(--ivory-dim);font-size:10.5px;font-weight:600;margin-top:2px;}

  /* section pages (payment/ads/refer) */
  .page{display:none; animation:fade .28s ease;}
  .page.active-page{display:block;}
  @keyframes fade{0%{opacity:.4;transform:translateY(8px);}100%{opacity:1;transform:translateY(0);}}

  .section-head{
    display:flex; align-items:center; gap:8px; margin:4px 4px 12px;
  }
  .section-head i{color:var(--gold-400); font-size:16px;}
  .section-head span{font-family:'Sora',sans-serif; font-weight:700; font-size:16px;}

  .panel{
    background:rgba(5,20,15,0.55); border-radius:22px; padding:16px 16px;
    border:1px solid var(--line); margin-bottom:14px;
  }
  .panel-title{display:flex;justify-content:space-between;align-items:center;color:var(--ivory);font-weight:700;font-size:14px;}
  .chip{background:linear-gradient(120deg, var(--teal-300), var(--teal-400));color:var(--emerald-950);font-weight:700;font-size:11.5px;padding:3px 12px;border-radius:40px;}
  .chip-gold{background:linear-gradient(120deg, var(--gold-300), var(--gold-400));}

  .row-item{
    background:rgba(0,0,0,0.28); padding:11px 14px; border-radius:16px;
    display:flex;justify-content:space-between;align-items:center;
    color:var(--ivory-dim); font-size:13px; border-left:3px solid var(--gold-400); margin-top:10px;
  }
  .row-item .badge{background:var(--gold-400);color:var(--emerald-950);font-weight:700;padding:2px 11px;border-radius:40px;font-size:11.5px;}

  .refer-code{
    background:rgba(0,0,0,0.35); padding:10px 18px; border-radius:60px;
    font-family:'Sora',sans-serif; font-size:18px; font-weight:700; letter-spacing:2.2px;
    color:var(--gold-300); border:1.5px dashed var(--gold-400); margin-top:12px; text-align:center;
  }
  .refer-stats{display:flex;justify-content:space-between;margin:13px 0 4px;color:var(--ivory-dim);font-size:13px;}
  .refer-stats i{color:var(--teal-300);margin-right:5px;}

  .withdraw-row{display:flex;gap:8px;flex-wrap:wrap;margin:12px 0;}
  .withdraw-option{
    background:rgba(0,0,0,0.3); padding:9px 14px; border-radius:40px;
    font-size:12.5px; font-weight:600; color:var(--ivory-dim);
    border:1px solid rgba(255,201,77,0.22); display:flex;align-items:center;gap:6px;
    cursor:pointer; transition:.15s; min-height:38px;
  }
  .withdraw-option i{color:var(--gold-400);}
  .withdraw-option.selected{background:linear-gradient(120deg, var(--gold-300), var(--gold-400));color:var(--emerald-950);border-color:transparent;}
  .withdraw-option.selected i{color:var(--emerald-950);}

  .input-group{
    background:rgba(0,0,0,0.4); border-radius:50px; padding:4px 16px;
    display:flex;align-items:center; border:1px solid rgba(255,255,255,0.08); margin:10px 0;
  }
  .input-group i{color:#7b9284;margin-right:10px;}
  .input-group input{background:transparent;border:none;padding:14px 0;color:var(--ivory);font-weight:500;width:100%;outline:none;font-size:15px;}
  .input-group input::placeholder{color:#5f7869;}

  .btn-gold{
    background:linear-gradient(145deg, var(--gold-300), var(--gold-400));
    border:none;padding:15px 0;width:100%;border-radius:50px;
    font-weight:800;color:var(--emerald-950);font-size:15px;
    box-shadow:0 10px 20px rgba(255,201,77,0.28); margin-top:12px; cursor:pointer; transition:.15s;
    min-height:48px;
  }
  .btn-gold:active{transform:scale(0.97);}
  .btn-teal{background:linear-gradient(145deg, var(--teal-300), var(--teal-400)); box-shadow:0 10px 20px rgba(47,224,181,0.28);}

  .mini-text{color:#7b9284;font-size:11px;margin-top:10px;display:flex;gap:14px;flex-wrap:wrap;justify-content:center;}
  .mini-text i{color:var(--gold-400);}

  .ad-slot{background:rgba(0,0,0,0.32);padding:13px;border-radius:18px;text-align:center;border:1px solid rgba(255,201,77,0.18);cursor:pointer;transition:.15s;min-height:88px;}
  .ad-slot:active{transform:scale(0.95);}
  .ad-slot i{color:var(--gold-400);font-size:21px;}
  .ad-slot .t{color:var(--ivory);font-weight:600;font-size:13px;margin-top:4px;}
  .ad-slot .p{color:var(--ivory-dim);font-size:11px;}
  .ad-grid{margin-top:16px;display:grid;grid-template-columns:1fr 1fr;gap:10px;}

  .footer-note{margin-top:6px;text-align:center;color:#5f7869;font-size:10.5px;}

  /* ===== BOTTOM NAV (fixed, bot-style) ===== */
  .bottom-nav{
    position:fixed; bottom:0; left:50%; transform:translateX(-50%);
    width:100%; max-width:460px;
    display:flex;
    background:rgba(5,16,12,0.9);
    backdrop-filter:blur(18px); -webkit-backdrop-filter:blur(18px);
    border-top:1px solid var(--line);
    padding:8px 8px calc(8px + var(--safe-bottom));
    z-index:30;
  }
  .nav-btn{
    flex:1; background:transparent; border:none; cursor:pointer;
    display:flex; flex-direction:column; align-items:center; gap:4px;
    padding:7px 0; color:var(--ivory-dim); position:relative;
    min-height:52px; justify-content:center;
  }
  .nav-btn .nav-ic{
    width:26px;height:26px; display:flex;align-items:center;justify-content:center;
    font-size:16px; border-radius:9px; transition:.2s;
  }
  .nav-btn .nav-lb{font-size:10px; font-weight:600; transition:.2s;}
  .nav-btn.active .nav-ic{
    background:linear-gradient(145deg, var(--gold-300), var(--gold-400));
    color:var(--emerald-950);
    box-shadow:0 4px 12px rgba(255,201,77,0.4);
  }
  .nav-btn.active .nav-lb{color:var(--gold-300);}
  .nav-btn .nav-dot{
    position:absolute; top:2px; right:22%;
    width:7px;height:7px;border-radius:50%;background:var(--coral-500);
    box-shadow:0 0 0 2px var(--emerald-950);
    display:none;
  }
  .nav-btn.has-alert .nav-dot{display:block;}

  /* toast */
  .toast{
    position:fixed; left:50%; bottom:calc(84px + var(--safe-bottom)); transform:translate(-50%, 16px);
    background:linear-gradient(120deg, var(--gold-300), var(--gold-400));
    color:var(--emerald-950); font-weight:700; font-size:13px;
    padding:11px 20px; border-radius:50px;
    box-shadow:0 14px 30px rgba(0,0,0,0.4);
    display:flex; align-items:center; gap:8px;
    opacity:0; pointer-events:none;
    transition:opacity .25s ease, transform .25s ease;
    z-index:50; max-width:88%; text-align:center;
  }
  .toast.show{opacity:1; transform:translate(-50%, 0);}

  @media (max-width:360px){
    .balance-value{font-size:30px;}
    .quick-grid{gap:7px;}
  }
</style>
</head>
<body>
<div class="app-shell">

  <!-- TOP BAR -->
  <div class="topbar">
    <div class="bot-avatar">৳</div>
    <div class="bot-meta">
      <div class="bot-name">Make Money <i class="fas fa-badge-check verified"></i></div>
      <div class="bot-status"><span class="dot-live"></span> অনলাইন · বট সক্রিয়</div>
    </div>
    <div class="topbar-action" id="notifBtn"><i class="fas fa-bell"></i></div>
  </div>

  <!-- SCROLLABLE CONTENT -->
  <div class="content">

    <!-- GREETING + BALANCE HERO (always visible) -->
    <div class="greet-hero">
      <div class="greet-line">
        <div class="greet-text">
          <div class="hi">স্বাগতম 👋</div>
          <div class="name"><span>আব্দুর রহিম</span></div>
          <div class="id-pill"><i class="far fa-id-card"></i> ID: 8712-4A9F</div>
        </div>
        <button class="login-pill" id="loginBtn"><i class="fas fa-sign-in-alt"></i> লগইন</button>
      </div>

      <div class="balance-block">
        <div class="balance-label"><i class="fas fa-wallet"></i> মোট ব্যালেন্স</div>
        <div class="balance-value" id="balanceValue">৳ 420 <small>টাকা</small></div>
        <div class="progress-wrap">
          <div class="progress-labels"><span>উইথড্র প্রগ্রেস</span><span>৮ / ১০ রেফার</span></div>
          <div class="progress-track"><div class="progress-fill"></div></div>
        </div>
      </div>
    </div>

    <!-- QUICK ACTIONS (bot main-menu style) -->
    <div class="quick-title"><i class="fas fa-th-large"></i> কুইক মেনু</div>
    <div class="quick-grid">
      <div class="quick-btn" data-goto="ads"><div class="ic ic-gold"><i class="fas fa-play"></i></div><div class="lb">এড দেখুন</div></div>
      <div class="quick-btn" data-goto="refer"><div class="ic ic-teal"><i class="fas fa-user-plus"></i></div><div class="lb">রেফার করুন</div></div>
      <div class="quick-btn" data-goto="payment"><div class="ic ic-coral"><i class="fas fa-money-bill-wave"></i></div><div class="lb">উইথড্র</div></div>
      <div class="quick-btn" id="taskBtn"><div class="ic ic-lav"><i class="fas fa-tasks"></i></div><div class="lb">টাস্ক</div></div>
    </div>

    <div class="stats-grid">
      <div class="stat-card"><i class="fas fa-user-plus"></i><div class="value">৮</div><div class="label">মোট রেফার</div></div>
      <div class="stat-card"><i class="fas fa-gift"></i><div class="value">৩০</div><div class="label">ডেইলি বোনাস</div></div>
    </div>

    <!-- ===== HOME PAGE ===== -->
    <div id="page-home" class="page active-page">
      <div class="panel">
        <div class="panel-title"><span><i class="fas fa-gem" style="color:#ffc94d;"></i> প্রথম লগইন বোনাস</span><span class="chip chip-gold">+২০ টাকা</span></div>
        <div class="row-item"><span><i class="fas fa-calendar-day"></i> ডেইলি বোনাস</span><span class="badge">+৩০</span></div>
        <div class="row-item" style="border-left-color:#2fe0b5;"><span><i class="fas fa-flag"></i> মিনিমাম উইথড্র</span><span class="badge" style="background:#2fe0b5;">৫০০৳</span></div>
      </div>
      <div class="panel">
        <div class="panel-title"><span><i class="fas fa-id-card"></i> আপনার রেফার কোড</span><span class="chip">REF-7X9K</span></div>
        <div class="refer-stats"><span><i class="fas fa-user-plus"></i> ৮ জন রেফার করেছেন</span><span><i class="fas fa-coins"></i> ১৬০ টাকা</span></div>
      </div>
    </div>

    <!-- ===== PAYMENT PAGE ===== -->
    <div id="page-payment" class="page">
      <div class="section-head"><i class="fas fa-wallet"></i><span>পেমেন্ট</span></div>
      <div class="panel">
        <div class="panel-title"><span><i class="fas fa-hand-holding-usd" style="color:#ffc94d;"></i> উইথড্র করুন</span></div>
        <div style="color:var(--ivory-dim);font-size:12.5px;display:flex;gap:14px;flex-wrap:wrap;margin-top:8px;">
          <span><i class="fas fa-check-circle" style="color:#2fe0b5;"></i> মিনিমাম ৫০০ টাকা</span>
          <span><i class="fas fa-users"></i> ১০ রেফার প্রয়োজন</span>
        </div>
        <div class="withdraw-row" id="methodRow">
          <span class="withdraw-option selected" data-m="বিকাশ"><i class="fas fa-mobile-alt"></i> বিকাশ</span>
          <span class="withdraw-option" data-m="নগদ"><i class="fas fa-mobile-alt"></i> নগদ</span>
          <span class="withdraw-option" data-m="বাইন্যান্স"><i class="fab fa-bitcoin"></i> বাইন্যান্স</span>
        </div>
        <div class="input-group"><i class="fas fa-phone"></i><input type="text" placeholder="নাম্বার (বিকাশ/নগদ)"></div>
        <div class="input-group"><i class="fas fa-dollar-sign"></i><input type="text" placeholder="এমাউন্ট (টাকা)"></div>
        <button class="btn-gold" id="withdrawBtn"><i class="fas fa-paper-plane"></i> উইথড্র করুন</button>
        <div class="mini-text"><span><i class="fas fa-clock"></i> ২৪-৪৮ ঘণ্টা</span><span><i class="fas fa-shield-alt"></i> নিরাপদ</span></div>
      </div>
    </div>

    <!-- ===== ADS PAGE ===== -->
    <div id="page-ads" class="page">
      <div class="section-head"><i class="fas fa-ad"></i><span>এড দেখে আয় করুন</span></div>
      <div class="panel">
        <div style="display:flex;align-items:center;gap:12px;">
          <i class="fas fa-ad" style="font-size:28px;color:#ffc94d;"></i>
          <div><div style="color:var(--ivory);font-weight:700;">এড ভিউ</div><div style="color:var(--ivory-dim);font-size:12.5px;">প্রতি এড ৫ টাকা</div></div>
          <span class="chip chip-gold" style="margin-left:auto;">+৫</span>
        </div>
        <div class="ad-grid">
          <div class="ad-slot" data-ad="1"><i class="fas fa-play-circle"></i><div class="t">এড ১</div><div class="p">৫ টাকা</div></div>
          <div class="ad-slot" data-ad="2"><i class="fas fa-play-circle"></i><div class="t">এড ২</div><div class="p">৫ টাকা</div></div>
        </div>
        <button class="btn-gold btn-teal" id="watchAdBtn" style="margin-top:16px;"><i class="fas fa-eye"></i> এড দেখুন</button>
      </div>
    </div>

    <!-- ===== REFER PAGE ===== -->
    <div id="page-refer" class="page">
      <div class="section-head"><i class="fas fa-users"></i><span>রেফার করুন</span></div>
      <div class="panel">
        <div class="panel-title"><span><i class="fas fa-link"></i> আপনার রেফার লিংক</span><span class="chip">+২০ টাকা/রেফার</span></div>
        <div class="refer-code">REF-7X9K</div>
        <div class="refer-stats"><span><i class="fas fa-users"></i> ৮ জন রেফার করেছেন</span><span><i class="fas fa-coins"></i> ১৬০ টাকা</span></div>
        <div class="withdraw-row" style="margin-top:4px;">
          <span class="withdraw-option"><i class="fas fa-user-check"></i> রেফার ১: +২০</span>
          <span class="withdraw-option"><i class="fas fa-user-check"></i> রেফার ২: +২০</span>
          <span class="withdraw-option"><i class="fas fa-user-plus"></i> আরো ৬ জন</span>
        </div>
        <button class="btn-gold" id="copyBtn"><i class="fas fa-copy"></i> রেফার কোড কপি</button>
      </div>
      <div style="color:var(--ivory-dim);font-size:12px;text-align:center;padding:6px;">
        <i class="fas fa-info-circle"></i> প্রতি রেফারে ২০ টাকা, উইথড্র করতে ১০ রেফার প্রয়োজন
      </div>
    </div>

    <div class="footer-note"><i class="fas fa-shield-alt"></i> মিনি অ্যাপ ডেমো · সব ফিচার ইন্টারেক্টিভ</div>
  </div>

  <!-- BOTTOM NAV -->
  <div class="bottom-nav">
    <button class="nav-btn active" data-page="page-home"><div class="nav-ic"><i class="fas fa-house"></i></div><div class="nav-lb">হোম</div></button>
    <button class="nav-btn" data-page="page-ads"><div class="nav-ic"><i class="fas fa-ad"></i></div><div class="nav-lb">এড</div></button>
    <button class="nav-btn has-alert" data-page="page-refer"><div class="nav-ic"><i class="fas fa-users"></i></div><div class="nav-lb">রেফার</div><span class="nav-dot"></span></button>
    <button class="nav-btn" data-page="page-payment"><div class="nav-ic"><i class="fas fa-wallet"></i></div><div class="nav-lb">পেমেন্ট</div></button>
  </div>

</div>

<div class="toast" id="toast"></div>

<script>
(function(){
  const navBtns = document.querySelectorAll('.nav-btn');
  const pages = {
    'page-home': document.getElementById('page-home'),
    'page-payment': document.getElementById('page-payment'),
    'page-ads': document.getElementById('page-ads'),
    'page-refer': document.getElementById('page-refer')
  };

  function switchPage(id){
    Object.values(pages).forEach(p=>p.classList.remove('active-page'));
    if(pages[id]) pages[id].classList.add('active-page');
    navBtns.forEach(b=>b.classList.remove('active'));
    const active = Array.from(navBtns).find(b=>b.dataset.page===id);
    if(active){ active.classList.add('active'); active.classList.remove('has-alert'); }
    document.querySelector('.content').scrollTo({top:0, behavior:'smooth'});
  }

  navBtns.forEach(btn=>{
    btn.addEventListener('click', function(){ switchPage(this.dataset.page); });
  });

  document.querySelectorAll('.quick-btn[data-goto]').forEach(btn=>{
    btn.addEventListener('click', function(){ switchPage('page-'+this.dataset.goto); });
  });

  // toast
  const toast = document.getElementById('toast');
  let toastTimer;
  function showToast(msg, icon){
    toast.innerHTML = `<i class="fas ${icon||'fa-check-circle'}"></i> ${msg}`;
    toast.classList.add('show');
    clearTimeout(toastTimer);
    toastTimer = setTimeout(()=>toast.classList.remove('show'), 2400);
  }

  // balance animation
  let balance = 420;
  const balanceEl = document.getElementById('balanceValue');
  function animateBalance(to){
    const from = balance; balance = to;
    const dur=500, start=performance.now();
    function step(now){
      const p = Math.min(1,(now-start)/dur);
      const val = Math.round(from+(to-from)*p);
      balanceEl.innerHTML = `৳ ${val} <small>টাকা</small>`;
      if(p<1) requestAnimationFrame(step);
    }
    requestAnimationFrame(step);
  }

  // login demo
  document.getElementById('loginBtn').addEventListener('click', function(){
    const chars='0123456789ABCDEF'; let id='';
    for(let i=0;i<8;i++) id += chars[Math.floor(Math.random()*chars.length)];
    document.querySelector('.id-pill').innerHTML = `<i class="far fa-id-card"></i> ID: ${id}`;
    showToast(`নতুন আইডি: ${id}`, 'fa-sign-in-alt');
  });

  // notif bell
  document.getElementById('notifBtn').addEventListener('click', function(){
    showToast('কোনো নতুন নোটিফিকেশন নেই', 'fa-bell');
  });

  // task quick button
  document.getElementById('taskBtn').addEventListener('click', function(){
    showToast('আজকের কোনো টাস্ক এখনো যোগ হয়নি', 'fa-tasks');
  });

  // withdraw method select
  document.getElementById('methodRow').addEventListener('click', function(e){
    const opt = e.target.closest('.withdraw-option');
    if(!opt) return;
    this.querySelectorAll('.withdraw-option').forEach(o=>o.classList.remove('selected'));
    opt.classList.add('selected');
  });

  document.getElementById('withdrawBtn').addEventListener('click', function(){
    showToast('উইথড্র অনুরোধ গৃহীত (ডেমো)', 'fa-paper-plane');
  });

  // watch ad
  function watchAd(){
    animateBalance(balance+5);
    showToast('+৫ টাকা যোগ হয়েছে (ডেমো)', 'fa-coins');
  }
  document.getElementById('watchAdBtn').addEventListener('click', watchAd);
  document.querySelectorAll('.ad-slot').forEach(s=>s.addEventListener('click', watchAd));

  // copy referral
  document.getElementById('copyBtn').addEventListener('click', function(){
    showToast('রেফার কোড কপি হয়েছে (ডেমো)', 'fa-copy');
  });
})();
</script>
</body>
</html>    }

        .dark-mode {
            --primary: #A78BFA;
            --primary-dark: #8B5CF6;
            --primary-light: #C4B5FD;
            --secondary: #34D399;
            --secondary-dark: #10B981;
            --accent: #FBBF24;
            --dark: #F9FAFB;
            --darker: #F3F4F6;
            --light: #1F2937;
            --gray: #374151;
            --gray-dark: #4B5563;
            --text: #F9FAFB;
            --text-light: #D1D5DB;
            --shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
            --gradient: linear-gradient(135deg, #1F2937 0%, #374151 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'Nikosh', 'SolaimanLipi', sans-serif;
        }

        body {
            background: var(--light);
            color: var(--text);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            transition: all 0.3s ease;
        }

        .app-container {
            width: 100%;
            max-width: 400px;
            background: var(--light);
            border-radius: 20px;
            box-shadow: var(--shadow);
            overflow: hidden;
            display: flex;
            flex-direction: column;
            height: 95vh;
            position: relative;
        }

        /* Header Styles */
        .header {
            background: var(--gradient);
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
        }

        .header-controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

        .theme-toggle, .language-toggle {
            background: rgba(255, 255, 255, 0.2);
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2em;
            color: white;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .theme-toggle:hover, .language-toggle:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: scale(1.1);
        }

        .app-title {
            font-size: 1.6em;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .app-subtitle {
            font-size: 0.9em;
            opacity: 0.9;
        }

        /* Balance Display - Only in Home */
        .balance-display {
            background: rgba(255, 255, 255, 0.15);
            padding: 20px;
            border-radius: 15px;
            margin: 15px 0;
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            text-align: center;
        }

        .balance-label {
            font-size: 0.9em;
            opacity: 0.9;
            margin-bottom: 8px;
        }

        .balance-amount {
            font-size: 2.5em;
            font-weight: bold;
            margin: 5px 0;
        }

        .min-withdrawal {
            font-size: 0.8em;
            opacity: 0.8;
        }

        /* Main Content */
        .main-content {
            flex: 1;
            padding: 0;
            overflow-y: auto;
            background: var(--light);
        }

        .content-section {
            display: none;
            height: 100%;
            padding: 20px;
        }

        .content-section.active {
            display: block;
        }

        /* Home Section */
        .home-section {
            text-align: center;
        }

        .character-container {
            position: relative;
            margin: 0 auto 25px;
            width: 120px;
            height: 120px;
        }

        .character {
            width: 100%;
            height: 100%;
            background: var(--gradient);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3em;
            color: white;
            box-shadow: 0 10px 25px rgba(139, 92, 246, 0.3);
            border: 4px solid var(--light);
        }

        .character-level {
            position: absolute;
            bottom: -8px;
            right: -8px;
            background: var(--secondary);
            color: white;
            padding: 4px 10px;
            border-radius: 12px;
            font-size: 0.7em;
            font-weight: bold;
            border: 2px solid var(--light);
        }

        .feed-btn {
            background: var(--gradient);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.1em;
            font-weight: bold;
            border-radius: 25px;
            cursor: pointer;
            margin: 15px 0;
            box-shadow: 0 8px 20px rgba(139, 92, 246, 0.4);
            transition: all 0.3s ease;
            width: 100%;
            max-width: 250px;
        }

        .feed-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 25px rgba(139, 92, 246, 0.5);
        }

        .feed-btn:disabled {
            background: var(--text-light);
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .click-counter {
            font-size: 0.9em;
            margin: 10px 0 20px;
            color: var(--text-light);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
            margin: 20px 0;
        }

        .stat-card {
            background: var(--gray);
            padding: 15px;
            border-radius: 12px;
            text-align: center;
            border: 1px solid var(--gray-dark);
        }

        .stat-value {
            font-size: 1.4em;
            font-weight: bold;
            color: var(--primary);
            margin: 5px 0;
        }

        .stat-label {
            font-size: 0.8em;
            color: var(--text-light);
        }

        .welcome-card {
            background: var(--gradient);
            color: white;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            text-align: center;
            box-shadow: 0 8px 20px rgba(139, 92, 246, 0.3);
        }

        .welcome-title {
            font-size: 1.2em;
            font-weight: bold;
            margin-bottom: 5px;
        }

        /* Ads Section */
        .ad-card {
            background: var(--gray);
            padding: 20px;
            margin: 15px 0;
            border-radius: 15px;
            text-align: center;
            border: 1px solid var(--gray-dark);
        }

        .ad-title {
            font-size: 1.2em;
            font-weight: bold;
            margin-bottom: 8px;
            color: var(--primary);
        }

        .ad-description {
            color: var(--text-light);
            margin: 10px 0;
            font-size: 0.9em;
        }

        .countdown-timer {
            font-size: 1em;
            color: var(--primary);
            font-weight: bold;
            margin: 12px 0;
            padding: 8px;
            background: rgba(139, 92, 246, 0.1);
            border-radius: 8px;
            display: none;
        }

        .progress-container {
            margin: 15px 0;
        }

        .progress-label {
            display: flex;
            justify-content: space-between;
            margin-bottom: 6px;
            font-size: 0.85em;
            color: var(--text-light);
        }

        .progress-bar {
            width: 100%;
            height: 8px;
            background: var(--gray-dark);
            border-radius: 4px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: var(--gradient);
            border-radius: 4px;
            transition: width 0.3s ease;
        }

        /* Tasks Section */
        .task-card {
            background: var(--gray);
            padding: 20px;
            margin: 15px 0;
            border-radius: 15px;
            border: 1px solid var(--gray-dark);
        }

        .task-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .task-title {
            font-weight: bold;
            font-size: 1.1em;
            color: var(--text);
        }

        .task-reward {
            background: var(--primary);
            color: white;
            padding: 5px 10px;
            border-radius: 12px;
            font-size: 0.8em;
            font-weight: bold;
        }

        .task-description {
            color: var(--text-light);
            margin-bottom: 12px;
            font-size: 0.9em;
        }

        .task-button {
            background: var(--secondary);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            font-size: 0.9em;
        }

        .task-button:hover {
            background: var(--secondary-dark);
            transform: translateY(-1px);
        }

        .task-status {
            display: inline-block;
            padding: 5px 10px;
            border-radius: 10px;
            font-size: 0.75em;
            margin-top: 8px;
            font-weight: bold;
        }

        .status-active {
            background: var(--secondary);
            color: white;
        }

        /* Withdraw Section */
        .withdraw-card {
            background: var(--gray);
            padding: 20px;
            margin: 15px 0;
            border-radius: 15px;
            border: 1px solid var(--gray-dark);
        }

        .info-grid {
            display: grid;
            gap: 12px;
            margin: 15px 0;
        }

        .info-item {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px solid var(--gray-dark);
            font-size: 0.9em;
        }

        .payment-methods {
            display: grid;
            gap: 10px;
            margin: 15px 0;
        }

        .payment-method {
            padding: 15px;
            border: 2px solid var(--gray-dark);
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            background: var(--light);
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .payment-method:hover {
            border-color: var(--primary);
            transform: translateY(-1px);
        }

        .payment-method.active {
            border-color: var(--primary);
            background: rgba(139, 92, 246, 0.05);
        }

        .payment-icon {
            font-size: 1.8em;
        }

        .payment-details {
            flex: 1;
        }

        .payment-name {
            font-weight: bold;
            margin-bottom: 3px;
            font-size: 0.95em;
        }

        .min-amount {
            font-size: 0.75em;
            color: var(--primary);
        }

        .payment-input {
            width: 100%;
            padding: 10px;
            border: 1px solid var(--gray-dark);
            border-radius: 8px;
            margin-top: 8px;
            background: var(--light);
            color: var(--text);
            display: none;
            font-size: 0.9em;
        }

        .payment-method.active .payment-input {
            display: block;
        }

        .warning-card {
            background: rgba(239, 68, 68, 0.1);
            color: #EF4444;
            padding: 12px;
            border-radius: 8px;
            margin: 15px 0;
            text-align: center;
            border: 1px solid rgba(239, 68, 68, 0.2);
            font-size: 0.85em;
        }

        .withdraw-btn {
            background: var(--gradient);
            color: white;
            border: none;
            padding: 15px;
            width: 100%;
            border-radius: 12px;
            font-size: 1em;
            font-weight: bold;
            cursor: pointer;
            margin-top: 10px;
            box-shadow: 0 8px 20px rgba(139, 92, 246, 0.3);
            transition: all 0.3s ease;
        }

        .withdraw-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 25px rgba(139, 92, 246, 0.4);
        }

        /* Navigation */
        .navigation {
            display: flex;
            background: var(--light);
            border-top: 1px solid var(--gray-dark);
            padding: 8px 12px;
            gap: 4px;
        }

        .nav-item {
            flex: 1;
            text-align: center;
            padding: 10px 4px;
            cursor: pointer;
            transition: all 0.3s ease;
            border-radius: 12px;
            background: var(--gray);
            border: 2px solid transparent;
            font-size: 0.75em;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 4px;
        }

        .nav-item.home {
            flex: 1.2;
            padding: 12px 4px;
            font-size: 0.8em;
            font-weight: bold;
        }

        .nav-item.active {
            background: var(--gradient);
            color: white;
            border-color: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(139, 92, 246, 0.3);
        }

        .nav-item:hover:not(.active) {
            background: var(--gray-dark);
        }

        .nav-icon {
            font-size: 1.2em;
        }

        .nav-item.home .nav-icon {
            font-size: 1.4em;
        }

        /* Animations */
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .pulse {
            animation: pulse 0.5s ease-in-out;
        }

        /* Responsive */
        @media (max-width: 480px) {
            .app-container {
                height: 100vh;
                border-radius: 0;
            }
            
            .header {
                border-radius: 0;
            }
            
            .balance-amount {
                font-size: 2em;
            }
            
            .character-container {
                width: 100px;
                height: 100px;
            }
            
            .feed-btn {
                padding: 12px 25px;
                font-size: 1em;
            }
        }
    </style>
</head>
<body>
    <div class="app-container">
        <!-- Header Section -->
        <div class="header">
            <div class="header-controls">
                <button class="language-toggle" id="languageToggle">EN</button>
                <button class="theme-toggle" id="themeToggle">🌙</button>
            </div>
            <h1 class="app-title" id="appTitle">টম বুম</h1>
            <p class="app-subtitle" id="appSubtitle">খেলতে খেলতে আয় করুন</p>
            
            <!-- Balance Display - Only visible in Home section -->
            <div class="balance-display" id="balanceDisplay">
                <div class="balance-label" id="currentBalanceText">বর্তমান ব্যালেন্স</div>
                <div class="balance-amount" id="currentBalance">০ টাকা</div>
                <div class="min-withdrawal" id="minWithdrawalText">সর্বনিম্ন উত্তোলন: ১৫০০ টাকা</div>
            </div>
        </div>

        <!-- Main Content -->
        <div class="main-content">
            <!-- Home Section -->
            <div id="home-section" class="content-section active">
                <div class="home-section">
                    <div class="character-container">
                        <div class="character">😊</div>
                        <div class="character-level">লেভেল ১</div>
                    </div>
                    
                    <button class="feed-btn" id="feedButton">FEED ME! (5 TK)</button>
                    <div class="click-counter" id="todayClicksText">আজকের ক্লিক: <strong>০/৩</strong></div>
                    
                    <div class="stats-grid">
                        <div class="stat-card">
                            <div class="stat-label" id="levelText">লেভেল</div>
                            <div class="stat-value">১</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-label" id="totalEarnedText">মোট আয়</div>
                            <div class="stat-value">০ টাকা</div>
                        </div>
                    </div>

                    <div class="welcome-card">
                        <h3 class="welcome-title" id="welcomeTitle">স্বাগতম!</h3>
                        <p id="welcomeSubtitle">প্রতিদিন বিজ্ঞাপন দেখে আয় করুন</p>
                    </div>
                </div>
            </div>

            <!-- Ads Section -->
            <div id="ads-section" class="content-section">
                <div class="ad-card">
                    <h3 class="ad-title" id="watchVideoText">ভিডিও বিজ্ঞাপন দেখুন</h3>
                    <p class="ad-description">৩০ সেকেন্ড = ৫ টাকা</p>
                    <button class="feed-btn" id="watchAdButton">WATCH AD (5 TK)</button>
                    <div class="countdown-timer" id="countdownTimer"></div>
                    
                    <div class="progress-container">
                        <div class="progress-label">
                            <span id="dailyLimitText">দৈনিক সীমা: ০/৩০ বিজ্ঞাপন</span>
                            <span id="potentialEarningText">১৫০ টাকা/দিন</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill" style="width: 0%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="ad-card">
                    <h3 class="ad-title" id="todayOfferText">আজকের অফার</h3>
                    <p class="ad-description" id="offerDescription">প্রতিটি বিজ্ঞাপন দেখে ৫ টাকা করে আয় করুন</p>
                    <div style="margin: 15px 0; padding: 12px; background: rgba(6, 214, 160, 0.1); border-radius: 8px;">
                        <div style="margin: 5px 0;">✅ ৩০ সেকেন্ডের ভিডিও</div>
                        <div style="margin: 5px 0;">✅ সহজ প্রক্রিয়া</div>
                        <div style="margin: 5px 0;">✅ তাৎক্ষণিক পেমেন্ট</div>
                    </div>
                </div>
            </div>

            <!-- Tasks Section -->
            <div id="tasks-section" class="content-section">
                <div class="task-card">
                    <div class="task-header">
                        <div class="task-title" id="task1Title">টেলিগ্রাম চ্যানেলে যোগ দিন</div>
                        <div class="task-reward">১৫ টাকা</div>
                    </div>
                    <p class="task-description" id="task1Description">আমাদের অফিসিয়াল টেলিগ্রাম চ্যানেলে যোগ দিন</p>
                    <a href="https://t.me/onlinefreeincomebdjr" target="_blank" class="task-button" id="joinTelegramButton">যোগ দিন</a>
                    <span class="task-status status-active" id="task1Status">চালু</span>
                </div>
            </div>

            <!-- Withdraw Section -->
            <div id="withdraw-section" class="content-section">
                <div class="withdraw-card">
                    <div class="info-grid">
                        <div class="info-item">
                            <span id="minWithdrawalLabel">সর্বনিম্ন উত্তোলন:</span>
                            <span>১৫০০ টাকা</span>
                        </div>
                        <div class="info-item">
                            <span id="currentRateLabel">বর্তমান রেট:</span>
                            <span>১ USD = ১২৪ টাকা</span>
                        </div>
                        <div class="info-item">
                            <span id="yourBalanceLabel">আপনার ব্যালেন্স:</span>
                            <span id="withdrawBalance">০ টাকা</span>
                        </div>
                    </div>

                    <h3 style="text-align: center; margin: 20px 0 15px;" id="selectPaymentMethod">পেমেন্ট মাধ্যম নির্বাচন করুন</h3>
                    
                    <div class="payment-methods">
                        <div class="payment-method" data-method="bkash">
                            <div class="payment-icon">📱</div>
                            <div class="payment-details">
                                <div class="payment-name">বিকাশ</div>
                                <div class="min-amount">ন্যূনতম: ১২০০ টাকা</div>
                                <input type="text" class="payment-input" placeholder="বিকাশ নম্বর লিখুন" id="bkashNumber">
                            </div>
                        </div>
                        
                        <div class="payment-method" data-method="nagad">
                            <div class="payment-icon">💳</div>
                            <div class="payment-details">
                                <div class="payment-name">নগদ</div>
                                <div class="min-amount">ন্যূনতম: ১০০০ টাকা</div>
                                <input type="text" class="payment-input" placeholder="নগদ নম্বর লিখুন" id="nagadNumber">
                            </div>
                        </div>
                        
                        <div class="payment-method" data-method="binance">
                            <div class="payment-icon">₿</div>
                            <div class="payment-details">
                                <div class="payment-name">বাইনান্স</div>
                                <div class="min-amount">ন্যূনতম: ১০ USD</div>
                                <input type="text" class="payment-input" placeholder="বাইনান্স আইডি লিখুন" id="binanceId">
                            </div>
                        </div>
                    </div>

                    <div class="warning-card">
                        ⚠️ <span id="withdrawalWarning">উত্তোলনের জন্য আপনার অ্যাকাউন্টে কমপক্ষে ১৫০০ টাকা থাকতে হবে</span>
                    </div>

                    <button class="withdraw-btn" id="withdrawButton">উত্তোলন অনুরোধ জমা দিন</button>
                </div>
            </div>
        </div>

        <!-- Navigation -->
        <div class="navigation">
            <div class="nav-item home active" onclick="showSection('home')">
                <div class="nav-icon">🏠</div>
                <div id="navHome">হোম</div>
            </div>
            <div class="nav-item" onclick="showSection('ads')">
                <div class="nav-icon">📺</div>
                <div id="navAds">বিজ্ঞাপন</div>
            </div>
            <div class="nav-item" onclick="showSection('tasks')">
                <div class="nav-icon">✅</div>
                <div id="navTasks">টাস্ক</div>
            </div>
            <div class="nav-item" onclick="showSection('withdraw')">
                <div class="nav-icon">💰</div>
                <div id="navWithdraw">উত্তোলন</div>
            </div>
        </div>
    </div>

    <!-- GigaPub Ad Script -->
    <script src="https://ad.gigapub.tech/script?id=3262"></script>

    <script>
        // App State
        let currentLanguage = 'bn';
        let currentTheme = 'light';
        let currentBalance = 0;
        let totalEarnings = 0;
        let adCount = 0;
        let maxAdsPerDay = 30;
        let feedClickCount = 0;
        let isAdInProgress = false;
        let countdownInterval;
        let feedTimerActive = false;

        // Language texts
        const texts = {
            bn: {
                appTitle: 'টম বুম',
                appSubtitle: 'খেলতে খেলতে আয় করুন',
                currentBalanceText: 'বর্তমান ব্যালেন্স',
                minWithdrawalText: 'সর্বনিম্ন উত্তোলন: ১৫০০ টাকা',
                feedButton: 'FEED ME! (5 TK)',
                todayClicksText: 'আজকের ক্লিক: ০/৩',
                levelText: 'লেভেল',
                totalEarnedText: 'মোট আয়',
                welcomeTitle: 'স্বাগতম!',
                welcomeSubtitle: 'প্রতিদিন বিজ্ঞাপন দেখে আয় করুন',
                watchVideoText: 'ভিডিও বিজ্ঞাপন দেখুন',
                dailyLimitText: 'দৈনিক সীমা: ০/৩০ বিজ্ঞাপন',
                potentialEarningText: '১৫০ টাকা/দিন',
                todayOfferText: 'আজকের অফার',
                offerDescription: 'প্রতিটি বিজ্ঞাপন দেখে ৫ টাকা করে আয় করুন',
                task1Title: 'টেলিগ্রাম চ্যানেলে যোগ দিন',
                task1Description: 'আমাদের অফিসিয়াল টেলিগ্রাম চ্যানেলে যোগ দিন',
                task1Status: 'চালু',
                minWithdrawalLabel: 'সর্বনিম্ন উত্তোলন:',
                currentRateLabel: 'বর্তমান রেট:',
                yourBalanceLabel: 'আপনার ব্যালেন্স:',
                selectPaymentMethod: 'পেমেন্ট মাধ্যম নির্বাচন করুন',
                withdrawalWarning: 'উত্তোলনের জন্য আপনার অ্যাকাউন্টে কমপক্ষে ১৫০০ টাকা থাকতে হবে',
                withdrawButton: 'উত্তোলন অনুরোধ জমা দিন',
                navHome: 'হোম',
                navAds: 'বিজ্ঞাপন',
                navTasks: 'টাস্ক',
                navWithdraw: 'উত্তোলন',
                successMessage: 'আপনি ৫ টাকা আয় করেছেন! 🎉',
                withdrawSuccess: 'উত্তোলনের অনুরোধ জমা দেওয়া হয়েছে!',
                insufficientBalance: 'আপনার ব্যালেন্স অপর্যাপ্ত!',
                adLimitReached: 'আজকের বিজ্ঞাপন সীমা শেষ হয়েছে!',
                adInProgress: 'একটি বিজ্ঞাপন ইতিমধ্যে চলছে!',
                feedTimerActive: '২৪ ঘন্টার টাইমার সক্রিয়! আগামী দিন আবার চেষ্টা করুন।',
                adLoading: 'বিজ্ঞাপন লোড হচ্ছে...',
                adError: 'বিজ্ঞাপন লোড করতে সমস্যা হয়েছে! পরে আবার চেষ্টা করুন।'
            },
            en: {
                appTitle: 'Tom Boom',
                appSubtitle: 'Earn while playing',
                currentBalanceText: 'Current Balance',
                minWithdrawalText: 'Minimum Withdrawal: 1500 Taka',
                feedButton: 'FEED ME! (5 TK)',
                todayClicksText: "Today's Clicks: 0/3",
                levelText: 'Level',
                totalEarnedText: 'Total Earned',
                welcomeTitle: 'Welcome!',
                welcomeSubtitle: 'Earn daily by watching ads',
                watchVideoText: 'Watch Video Ads',
                dailyLimitText: 'Daily Limit: 0/30 Ads',
                potentialEarningText: '150 Taka/Day',
                todayOfferText: "Today's Offer",
                offerDescription: 'Earn 5 Taka for each ad you watch',
                task1Title: 'Join Telegram Channel',
                task1Description: 'Join our official Telegram channel',
                task1Status: 'Active',
                minWithdrawalLabel: 'Minimum Withdrawal:',
                currentRateLabel: 'Current Rate:',
                yourBalanceLabel: 'Your Balance:',
                selectPaymentMethod: 'Select Payment Method',
                withdrawalWarning: 'You need at least 1500 Taka in your account to withdraw',
                withdrawButton: 'Submit Withdrawal Request',
                navHome: 'Home',
                navAds: 'Ads',
                navTasks: 'Tasks',
                navWithdraw: 'Withdraw',
                successMessage: 'You earned 5 Taka! 🎉',
                withdrawSuccess: 'Withdrawal request submitted!',
                insufficientBalance: 'Insufficient balance!',
                adLimitReached: "Today's ad limit reached!",
                adInProgress: 'An ad is already in progress!',
                feedTimerActive: '24-hour timer active! Try again tomorrow.',
                adLoading: 'Loading ad...',
                adError: 'Failed to load ad! Please try again later.'
            }
        };

        // Initialize App
        document.addEventListener('DOMContentLoaded', function() {
            initializeApp();
        });

        function initializeApp() {
            // Theme toggle
            document.getElementById('themeToggle').addEventListener('click', toggleTheme);
            
            // Language toggle
            document.getElementById('languageToggle').addEventListener('click', toggleLanguage);
            
            // Feed button
            document.getElementById('feedButton').addEventListener('click', handleFeedClick);
            
            // Watch ad button
            document.getElementById('watchAdButton').addEventListener('click', handleAdWatch);
            
            // Payment method selection
            document.querySelectorAll('.payment-method').forEach(method => {
                method.addEventListener('click', function() {
                    selectPaymentMethod(this);
                });
            });
            
            // Withdraw button
            document.getElementById('withdrawButton').addEventListener('click', handleWithdraw);
            
            // Initialize UI
            updateLanguage();
            updateBalanceDisplay();
            updateProgressBar();
            
            // Select first payment method
            document.querySelector('.payment-method').click();
            
            // Check if feed timer is active
            checkFeedTimer();
        }

        function toggleTheme() {
            if (currentTheme === 'light') {
                document.body.classList.add('dark-mode');
                currentTheme = 'dark';
                this.textContent = '☀️';
            } else {
                document.body.classList.remove('dark-mode');
                currentTheme = 'light';
                this.textContent = '🌙';
            }
        }

        function toggleLanguage() {
            if (currentLanguage === 'bn') {
                currentLanguage = 'en';
                this.textContent = 'BN';
            } else {
                currentLanguage = 'bn';
                this.textContent = 'EN';
            }
            updateLanguage();
        }

        function updateLanguage() {
            const lang = texts[currentLanguage];
            for (const [key, value] of Object.entries(lang)) {
                const element = document.getElementById(key);
                if (element) {
                    element.textContent = value;
                }
            }
            updateBalanceDisplay();
            updateProgressBar();
        }

        function showSection(sectionName) {
            // Hide all sections
            document.querySelectorAll('.content-section').forEach(section => {
                section.classList.remove('active');
            });
            
            // Remove active class from all nav items
            document.querySelectorAll('.nav-item').forEach(nav => {
                nav.classList.remove('active');
            });
            
            // Show selected section
            document.getElementById(sectionName + '-section').classList.add('active');
            
            // Add active class to clicked nav item
            event.currentTarget.classList.add('active');
            
            // Show/hide balance display based on section
            const balanceDisplay = document.getElementById('balanceDisplay');
            if (sectionName === 'home') {
                balanceDisplay.style.display = 'block';
            } else {
                balanceDisplay.style.display = 'none';
            }
        }

        function selectPaymentMethod(element) {
            document.querySelectorAll('.payment-method').forEach(m => {
                m.classList.remove('active');
            });
            element.classList.add('active');
        }

        function handleFeedClick() {
            if (feedTimerActive) {
                alert(texts[currentLanguage].feedTimerActive);
                return;
            }
            
            feedClickCount++;
            
            // Add animation
            this.classList.add('pulse');
            setTimeout(() => {
                this.classList.remove('pulse');
            }, 500);
            
            // Update balance
            currentBalance += 5;
            totalEarnings += 5;
            
            // Update display
            updateBalanceDisplay();
            
            // Update click counter
            document.getElementById('todayClicksText').textContent = 
                currentLanguage === 'bn' ? 
                `আজকের ক্লিক: ${feedClickCount}/৩` : 
                `Today's Clicks: ${feedClickCount}/3`;
            
            // Check if 3 clicks reached
            if (feedClickCount >= 3) {
                activateFeedTimer();
            }
            
            // Show success message
            alert(texts[currentLanguage].successMessage);
        }

        function activateFeedTimer() {
            feedTimerActive = true;
            feedClickCount = 0;
            
            // Store timer activation time
            localStorage.setItem('feedTimerStart', Date.now());
            
            // Update UI
            document.getElementById('feedButton').disabled = true;
            document.getElementById('feedButton').textContent = 
                currentLanguage === 'bn' ? 'টাইমার সক্রিয়' : 'Timer Active';
            
            // Set timeout to reset after 24 hours
            setTimeout(() => {
                resetFeedTimer();
            }, 24 * 60 * 60 * 1000); // 24 hours
        }

        function checkFeedTimer() {
            const timerStart = localStorage.getItem('feedTimerStart');
            if (timerStart) {
                const elapsed = Date.now() - parseInt(timerStart);
                if (elapsed < 24 * 60 * 60 * 1000) {
                    // Timer still active
                    activateFeedTimer();
                    
                    // Set timeout for remaining time
                    setTimeout(() => {
                        resetFeedTimer();
                    }, 24 * 60 * 60 * 1000 - elapsed);
                } else {
                    // Timer expired
                    resetFeedTimer();
                }
            }
        }

        function resetFeedTimer() {
            feedTimerActive = false;
            feedClickCount = 0;
            localStorage.removeItem('feedTimerStart');
            
            // Update UI
            document.getElementById('feedButton').disabled = false;
            document.getElementById('feedButton').textContent = texts[currentLanguage].feedButton;
            document.getElementById('todayClicksText').textContent = 
                currentLanguage === 'bn' ? 'আজকের ক্লিক: ০/৩' : "Today's Clicks: 0/3";
        }

        function handleAdWatch() {
            if (isAdInProgress) {
                alert(texts[currentLanguage].adInProgress);
                return;
            }
            
            if (adCount >= maxAdsPerDay) {
                alert(texts[currentLanguage].adLimitReached);
                return;
            }
            
            // Add animation
            this.classList.add('pulse');
            setTimeout(() => {
                this.classList.remove('pulse');
            }, 500);
            
            // Show GigaPub ad
            showGigaPubAd();
        }

        function showGigaPubAd() {
            isAdInProgress = true;
            const adButton = document.getElementById('watchAdButton');
            adButton.disabled = true;
            adButton.textContent = texts[currentLanguage].adLoading;
            
            // Check if GigaPub is available
            if (typeof window.showGiga !== 'undefined') {
                window.showGiga()
                    .then(() => {
                        // Ad completed successfully
                        adCount++;
                        currentBalance += 5;
                        totalEarnings += 5;
                        
                        updateBalanceDisplay();
                        updateProgressBar();
                        
                        // Start countdown timer
                        startCountdown();
                        
                        // Show success message
                        alert(texts[currentLanguage].successMessage);
                    })
                    .catch(error => {
                        // Ad failed or was closed
                        console.error('GigaPub ad error:', error);
                        alert(texts[currentLanguage].adError);
                    })
                    .finally(() => {
                        // Reset button
                        adButton.disabled = false;
                        adButton.textContent = 'WATCH AD (5 TK)';
                        isAdInProgress = false;
                    });
            } else {
                // GigaPub not available, use fallback
                setTimeout(() => {
                    // Simulate ad completion
                    adCount++;
                    currentBalance += 5;
                    totalEarnings += 5;
                    
                    updateBalanceDisplay();
                    updateProgressBar();
                    
                    // Start countdown timer
                    startCountdown();
                    
                    // Reset button
                    adButton.disabled = false;
                    adButton.textContent = 'WATCH AD (5 TK)';
                    isAdInProgress = false;
                    
                    // Show success message
                    alert(texts[currentLanguage].successMessage);
                }, 3000);
            }
        }

        function startCountdown() {
            let countdown = 5;
            const timerElement = document.getElementById('countdownTimer');
            timerElement.style.display = 'block';
            timerElement.textContent = currentLanguage === 'bn' ? 
                `পরবর্তী বিজ্ঞাপন: ${countdown} সেকেন্ড` : 
                `Next ad: ${countdown} seconds`;
            
            clearInterval(countdownInterval);
            countdownInterval = setInterval(() => {
                countdown--;
                timerElement.textContent = currentLanguage === 'bn' ? 
                    `পরবর্তী বিজ্ঞাপন: ${countdown} সেকেন্ড` : 
                    `Next ad: ${countdown} seconds`;
                
                if (countdown <= 0) {
                    clearInterval(countdownInterval);
                    timerElement.style.display = 'none';
                }
            }, 1000);
        }

        function updateBalanceDisplay() {
            document.getElementById('currentBalance').textContent = 
                currentLanguage === 'bn' ? `${currentBalance} টাকা` : `${currentBalance} Taka`;
            
            document.getElementById('withdrawBalance').textContent = 
                currentLanguage === 'bn' ? `${currentBalance} টাকা` : `${currentBalance} Taka`;
            
            // Update total earned in stats
            document.querySelectorAll('.stat-value')[1].textContent = 
                currentLanguage === 'bn' ? `${totalEarnings} টাকা` : `${totalEarnings} Taka`;
        }

        function updateProgressBar() {
            const progress = (adCount / maxAdsPerDay) * 100;
            document.querySelector('.progress-fill').style.width = `${progress}%`;
            
            document.getElementById('dailyLimitText').textContent = 
                currentLanguage === 'bn' ? 
                `দৈনিক সীমা: ${adCount}/${maxAdsPerDay} বিজ্ঞাপন` : 
                `Daily Limit: ${adCount}/${maxAdsPerDay} Ads`;
        }

        function handleWithdraw() {
            if (currentBalance < 1500) {
                alert(texts[currentLanguage].insufficientBalance);
                return;
            }
            
            const selectedMethod = document.querySelector('.payment-method.active');
            if (!selectedMethod) {
                alert('Please select a payment method');
                return;
            }
            
            const method = selectedMethod.dataset.method;
            let inputField;
            
            switch(method) {
                case 'bkash':
                    inputField = document.getElementById('bkashNumber');
                    break;
                case 'nagad':
                    inputField = document.getElementById('nagadNumber');
                    break;
                case 'binance':
                    inputField = document.getElementById('binanceId');
                    break;
            }
            
            if (!inputField || !inputField.value) {
                alert('Please enter your payment details');
                return;
            }
            
            alert(texts[currentLanguage].withdrawSuccess);
        }
    </script>
</body>
</html>
