# Allison Rice, MD
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Allison Rice, MD | Bariatric &amp; General Surgery</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=EB+Garamond:ital,wght@0,400;0,500;1,400&family=Outfit:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    :root {
      --navy:        #1e3a52;
      --navy-mid:    #2b5278;
      --navy-light:  #3a6d9e;
      --navy-pale:   #e8f0f7;
      --gold:        #b8965a;
      --gold-light:  #d4b07a;
      --gold-pale:   #f7f0e3;
      --white:       #ffffff;
      --off-white:   #f9f7f4;
      --light-bg:    #f3f6f9;
      --text-dark:   #1a2e40;
      --text-mid:    #3d5a72;
      --text-light:  #7a96aa;
      --border:      #d8e4ed;
      --border-lt:   #eaf0f6;
    }
    html { scroll-behavior: smooth; }
    body {
      font-family: "Outfit", sans-serif;
      background: var(--white);
      color: var(--text-dark);
      font-weight: 300;
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 200;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 4rem; height: 66px;
      background: var(--white);
      border-bottom: 1px solid var(--border-lt);
      transition: box-shadow 0.3s;
    }
    .nav-brand { display: flex; align-items: center; gap: 1rem; text-decoration: none; }
    .nav-monogram {
      width: 36px; height: 36px; border-radius: 50%;
      border: 1.5px solid var(--gold);
      display: flex; align-items: center; justify-content: center;
      font-family: "EB Garamond", serif; font-size: 0.95rem;
      color: var(--gold);
    }
    .nav-name { font-family: "EB Garamond", serif; font-size: 1rem; color: var(--text-dark); line-height: 1.2; }
    .nav-cred { font-size: 0.62rem; letter-spacing: 0.13em; text-transform: uppercase; color: var(--text-light); }
    .nav-links { display: flex; gap: 2.25rem; list-style: none; align-items: center; }
    .nav-links a {
      font-size: 0.72rem; font-weight: 400; letter-spacing: 0.13em;
      text-transform: uppercase; color: var(--text-mid); text-decoration: none; transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--navy); }
    .nav-cta {
      padding: 0.5rem 1.25rem !important;
      border: 1px solid var(--navy) !important;
      color: var(--navy) !important; border-radius: 2px;
      transition: background 0.2s, color 0.2s !important;
    }
    .nav-cta:hover { background: var(--navy) !important; color: white !important; }
    .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; padding: 4px; }
    .hamburger span { display: block; width: 22px; height: 1.5px; background: var(--text-mid); }

    /* ── HERO ── */
    .hero {
      min-height: 100vh; padding-top: 66px;
      display: grid; grid-template-columns: 1fr 1fr;
      background: var(--off-white);
      position: relative; overflow: hidden;
    }
    .hero::before {
      content: "";
      position: absolute; inset: 0;
      background:
        radial-gradient(ellipse 60% 70% at 100% 60%, rgba(58,109,158,0.07) 0%, transparent 60%),
        radial-gradient(ellipse 40% 50% at 0% 0%, rgba(184,150,90,0.05) 0%, transparent 50%);
      pointer-events: none;
    }
    .hero-left {
      position: relative; z-index: 2;
      display: flex; flex-direction: column; justify-content: center;
      padding: 5rem 4rem 5rem 5rem;
    }
    .hero-eyebrow {
      display: flex; align-items: center; gap: 0.85rem;
      font-size: 0.67rem; font-weight: 500; letter-spacing: 0.24em; text-transform: uppercase;
      color: var(--gold); margin-bottom: 1.6rem;
      opacity: 0; animation: fadeUp 0.7s ease 0.15s forwards;
    }
    .hero-eyebrow::before { content: ""; width: 28px; height: 1px; background: var(--gold); }
    .hero-name {
      font-family: "EB Garamond", serif;
      font-size: clamp(2rem, 3.8vw, 4.2rem); font-weight: 400; line-height: 1.1;
      color: var(--text-dark); margin-bottom: 0.5rem; white-space: nowrap;
      opacity: 0; animation: fadeUp 0.7s ease 0.28s forwards;
    }
    .hero-specialty {
      font-family: "EB Garamond", serif;
      font-size: clamp(1.1rem, 1.7vw, 1.5rem); font-style: italic; font-weight: 400;
      color: var(--navy-light); margin-bottom: 2rem;
      opacity: 0; animation: fadeUp 0.7s ease 0.38s forwards;
    }
    .hero-rule { width: 50px; height: 1px; background: var(--gold); margin-bottom: 2rem; opacity: 0; animation: fadeIn 0.7s ease 0.48s forwards; }
    .hero-desc {
      font-size: 0.95rem; font-weight: 300; line-height: 1.88;
      color: var(--text-mid); max-width: 420px; margin-bottom: 2.5rem;
      opacity: 0; animation: fadeUp 0.7s ease 0.55s forwards;
    }
    .hero-actions {
      display: flex; gap: 1rem; flex-wrap: wrap;
      opacity: 0; animation: fadeUp 0.7s ease 0.65s forwards;
    }
    .btn-navy {
      display: inline-flex; align-items: center; gap: 0.5rem;
      padding: 0.88rem 2.1rem; background: var(--navy); color: white;
      font-family: "Outfit", sans-serif; font-size: 0.72rem; font-weight: 500;
      letter-spacing: 0.14em; text-transform: uppercase; text-decoration: none;
      border: none; cursor: pointer; border-radius: 2px;
      transition: background 0.25s, transform 0.2s;
    }
    .btn-navy:hover { background: var(--navy-mid); transform: translateY(-2px); }
    .btn-outline {
      display: inline-flex; align-items: center; gap: 0.5rem;
      padding: 0.88rem 2.1rem; background: transparent; color: var(--navy);
      font-family: "Outfit", sans-serif; font-size: 0.72rem; font-weight: 500;
      letter-spacing: 0.14em; text-transform: uppercase; text-decoration: none;
      border: 1px solid var(--border); cursor: pointer; border-radius: 2px;
      transition: all 0.25s;
    }
    .btn-outline:hover { border-color: var(--navy); background: var(--navy-pale); }
    .hero-rating {
      display: inline-flex; align-items: center; gap: 0.75rem;
      margin-top: 2.25rem; padding: 0.65rem 1.1rem;
      background: white; border: 1px solid var(--border);
      border-radius: 2px; width: fit-content; box-shadow: 0 2px 12px rgba(0,0,0,0.04);
      opacity: 0; animation: fadeUp 0.7s ease 0.78s forwards;
    }
    .hero-rating .stars { color: var(--gold); font-size: 0.82rem; letter-spacing: 1px; }
    .hero-rating strong { font-size: 0.9rem; font-weight: 500; color: var(--text-dark); }
    .hero-rating span { font-size: 0.72rem; color: var(--text-light); }

    /* ── HERO RIGHT — PHOTO ── */
    .hero-right {
      position: relative; z-index: 2;
      display: flex; flex-direction: column;
      align-items: center; justify-content: center;
      padding: 2rem 3rem;
    }
    .photo-wrap {
      width: 100%; max-width: 320px;
      opacity: 0; animation: fadeIn 1s ease 0.45s forwards;
    }
    .photo-wrap img {
      width: 100%; display: block;
      border-radius: 3px 3px 0 0;
      object-fit: cover; object-position: top;
      max-height: 420px;
    }
    /* credential bar BELOW photo */
    .photo-credential {
      width: 100%;
      background: var(--navy);
      padding: 0.85rem 1.25rem;
      display: flex; align-items: center; justify-content: space-between;
      border-radius: 0 0 3px 3px;
    }
    .cred-name {
      font-family: "EB Garamond", serif; font-size: 1rem; font-weight: 400;
      color: white; display: block;
    }
    .cred-spec {
      font-size: 0.62rem; letter-spacing: 0.12em; text-transform: uppercase;
      color: rgba(255,255,255,0.48); display: block; margin-top: 1px;
    }
    .cred-badge {
      font-size: 0.58rem; letter-spacing: 0.12em; text-transform: uppercase;
      color: var(--gold); border: 1px solid rgba(184,150,90,0.4);
      padding: 3px 8px; border-radius: 2px; white-space: nowrap; flex-shrink: 0;
    }

    /* ── SHARED ── */
    .section-inner { padding: 6rem 5rem; max-width: 1280px; margin: 0 auto; }
    .label {
      display: flex; align-items: center; gap: 0.75rem;
      font-size: 0.65rem; font-weight: 500; letter-spacing: 0.24em; text-transform: uppercase;
      color: var(--gold); margin-bottom: 0.9rem;
    }
    .label::before { content: ""; width: 22px; height: 1px; background: var(--gold); }
    .heading {
      font-family: "EB Garamond", serif;
      font-size: clamp(1.9rem, 2.8vw, 2.7rem); font-weight: 400; line-height: 1.2;
      color: var(--text-dark); margin-bottom: 1.2rem;
    }
    .heading em { font-style: italic; color: var(--navy-light); }
    .rule { width: 42px; height: 1px; background: var(--gold); opacity: 0.6; margin-bottom: 2.25rem; }

    /* ── ABOUT ── */
    #about { background: var(--white); }
    .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 5.5rem; align-items: start; }
    .about-body p { font-size: 0.94rem; line-height: 1.92; color: var(--text-mid); margin-bottom: 1.2rem; }
    .about-quote {
      font-family: "EB Garamond", serif; font-size: 1.2rem; font-style: italic; line-height: 1.65;
      color: var(--navy-mid); border-left: 2px solid var(--gold);
      padding: 0.25rem 0 0.25rem 1.5rem; margin: 1.75rem 0;
    }

    /* ── PROCEDURES PANEL ── */
    .proc-panel { background: var(--light-bg); border: 1px solid var(--border); border-top: 3px solid var(--gold); }
    .proc-panel-top-header {
      padding: 1.25rem 1.75rem;
      border-bottom: 1px solid var(--border);
    }
    .proc-panel-top-header .label { margin-bottom: 0; }
    .proc-sub-header {
      padding: 0.85rem 1.75rem;
      border-bottom: 1px solid var(--border);
      display: flex; align-items: center; justify-content: space-between; cursor: pointer;
      user-select: none; background: var(--navy-pale);
    }
    .proc-sub-header--alt { background: var(--gold-pale); }
    .proc-sub-title {
      font-size: 0.72rem; font-weight: 500; letter-spacing: 0.14em;
      text-transform: uppercase; color: var(--navy);
    }
    .proc-sub-header--alt .proc-sub-title { color: #7a5a2a; }
    .proc-toggle-btn {
      display: flex; align-items: center; gap: 0.4rem;
      font-size: 0.68rem; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase;
      color: var(--navy-light); background: none; border: 1px solid var(--border);
      padding: 0.35rem 0.8rem; border-radius: 2px; cursor: pointer;
      transition: all 0.2s; white-space: nowrap;
    }
    .proc-toggle-btn:hover { border-color: var(--navy); color: var(--navy); background: white; }
    .proc-toggle-btn svg { transition: transform 0.3s; }
    .proc-toggle-btn.open svg { transform: rotate(180deg); }

    /* scrollable list container */
    .proc-list-wrap {
      max-height: 320px;
      overflow-y: auto;
      transition: max-height 0.4s ease, opacity 0.3s ease;
      opacity: 1;
    }
    .proc-list-wrap.collapsed {
      max-height: 0;
      opacity: 0;
      overflow: hidden;
    }
    /* custom scrollbar */
    .proc-list-wrap::-webkit-scrollbar { width: 4px; }
    .proc-list-wrap::-webkit-scrollbar-track { background: var(--border-lt); }
    .proc-list-wrap::-webkit-scrollbar-thumb { background: var(--border); border-radius: 2px; }
    .proc-list-wrap::-webkit-scrollbar-thumb:hover { background: var(--text-light); }

    .proc-list { list-style: none; }
    .proc-list li {
      display: flex; align-items: center; gap: 1rem;
      padding: 0.72rem 1.75rem;
      border-bottom: 1px solid var(--border-lt);
      font-size: 0.88rem; color: var(--text-mid);
      transition: background 0.15s;
    }
    .proc-list li:last-child { border-bottom: none; }
    .proc-list li:hover { background: var(--navy-pale); }
    .proc-dot { width: 5px; height: 5px; border-radius: 50%; background: var(--gold); flex-shrink: 0; }

    /* fade at bottom of scroll area */
    .proc-scroll-fade {
      position: relative;
    }
    .proc-scroll-fade::after {
      content: "";
      position: absolute; bottom: 0; left: 0; right: 0; height: 32px;
      background: linear-gradient(transparent, var(--light-bg));
      pointer-events: none;
      transition: opacity 0.3s;
    }
    .proc-scroll-fade.collapsed::after { opacity: 0; }

    .proc-count {
      font-size: 0.7rem; color: var(--text-light); padding: 0.6rem 1.75rem;
      border-top: 1px solid var(--border); background: var(--off-white);
      letter-spacing: 0.04em;
    }

    /* ── EDUCATION ── */
    #education { background: var(--white); }
    #procedures { background: var(--light-bg); }
    .edu-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-top: 3rem; }
    .edu-card {
      background: var(--white); border: 1px solid var(--border);
      padding: 2.25rem; position: relative; overflow: hidden;
      transition: transform 0.25s, box-shadow 0.25s;
    }
    .edu-card::before {
      content: ""; position: absolute; top: 0; left: 0; right: 0; height: 2px;
      background: var(--gold); transform: scaleX(0); transform-origin: left; transition: transform 0.3s;
    }
    .edu-card:hover { transform: translateY(-4px); box-shadow: 0 10px 36px rgba(30,58,82,0.08); }
    .edu-card:hover::before { transform: scaleX(1); }
    .edu-icon { width: 32px; height: 32px; color: var(--gold); margin-bottom: 1.1rem; display: block; }
    .edu-tag { font-size: 0.63rem; letter-spacing: 0.2em; text-transform: uppercase; color: var(--gold); display: block; margin-bottom: 0.45rem; }
    .edu-name { font-family: "EB Garamond", serif; font-size: 1.15rem; color: var(--text-dark); margin-bottom: 0.4rem; line-height: 1.3; }
    .edu-detail { font-size: 0.82rem; color: var(--text-light); line-height: 1.65; }
    .edu-badge {
      display: inline-block; margin-top: 1rem;
      font-size: 0.69rem; color: var(--navy-light); background: var(--navy-pale); padding: 3px 10px; border-radius: 20px;
    }

    /* ── LOCATIONS ── */
    #location { background: var(--white); }
    .offices-wrap { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-top: 3rem; }
    .office { border: 1px solid var(--border); overflow: hidden; transition: transform 0.25s, box-shadow 0.25s; }
    .office:hover { transform: translateY(-3px); box-shadow: 0 10px 32px rgba(30,58,82,0.07); }
    .office-head { background: var(--navy); padding: 1.15rem 1.5rem; display: flex; align-items: center; gap: 0.7rem; }
    .office-head svg { width: 15px; height: 15px; color: var(--gold-light); flex-shrink: 0; }
    .office-head-label { font-size: 0.69rem; font-weight: 500; letter-spacing: 0.14em; text-transform: uppercase; color: white; }
    .office-body { padding: 1.5rem; background: var(--off-white); }
    .office-addr { font-size: 0.88rem; line-height: 1.7; color: var(--text-mid); margin-bottom: 1rem; }
    .office-tel {
      display: flex; align-items: center; gap: 0.5rem;
      font-size: 0.95rem; font-weight: 500; color: var(--navy); text-decoration: none; transition: color 0.2s;
    }
    .office-tel svg { width: 13px; height: 13px; }
    .office-tel:hover { color: var(--gold); }
    .office-foot { padding: 0.9rem 1.5rem; background: var(--white); border-top: 1px solid var(--border-lt); }
    .dir-link {
      font-size: 0.69rem; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase;
      color: var(--navy-light); text-decoration: none; display: inline-flex; align-items: center; gap: 0.4rem;
      transition: color 0.2s;
    }
    .dir-link:hover { color: var(--gold); }
    .location-extras { display: grid; grid-template-columns: 1fr; gap: 1.25rem; margin-top: 1.5rem; max-width: 480px; }
    .extra { display: flex; align-items: flex-start; gap: 1rem; border: 1px solid var(--border); padding: 1.25rem 1.5rem; background: var(--light-bg); }
    .extra svg { width: 20px; height: 20px; color: var(--gold); flex-shrink: 0; margin-top: 2px; }
    .extra strong { display: block; font-size: 0.77rem; font-weight: 500; letter-spacing: 0.09em; text-transform: uppercase; color: var(--text-dark); margin-bottom: 0.25rem; }
    .extra p { font-size: 0.84rem; color: var(--text-mid); line-height: 1.6; }

    /* ── REVIEWS ── */
    #reviews { background: var(--light-bg); }
    .reviews-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-top: 3rem; }
    .review {
      background: var(--white); border: 1px solid var(--border);
      padding: 2rem; position: relative; transition: transform 0.25s, box-shadow 0.25s;
    }
    .review:hover { transform: translateY(-3px); box-shadow: 0 10px 32px rgba(30,58,82,0.07); }
    .review-mark { font-family: "EB Garamond", serif; font-size: 4rem; line-height: 1; color: var(--gold-pale); position: absolute; top: 0.25rem; left: 1.1rem; }
    .r-stars { display: flex; gap: 3px; margin-bottom: 1rem; margin-top: 0.5rem; }
    .r-star { width: 13px; height: 13px; color: var(--gold); }
    .r-text { font-family: "EB Garamond", serif; font-size: 1.05rem; font-style: italic; line-height: 1.75; color: var(--text-dark); margin-bottom: 1.2rem; }
    .r-author { font-size: 0.69rem; letter-spacing: 0.12em; text-transform: uppercase; color: var(--text-light); }
    .reviews-footer {
      margin-top: 3rem; padding-top: 2.5rem;
      border-top: 1px solid var(--border);
      display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 1.5rem;
    }
    .rating-summary { display: flex; align-items: center; gap: 1.1rem; }
    .rating-big { font-family: "EB Garamond", serif; font-size: 3rem; color: var(--text-dark); line-height: 1; }
    .rating-detail { display: flex; flex-direction: column; gap: 4px; }
    .rating-detail .r-stars { margin: 0; }
    .rating-detail span { font-size: 0.71rem; color: var(--text-light); }

    /* ── FOOTER ── */
    footer { background: var(--navy); padding: 3rem 5rem; border-top: 1px solid rgba(184,150,90,0.15); }
    .footer-inner { max-width: 1280px; margin: 0 auto; display: flex; align-items: center; justify-content: space-between; gap: 2rem; flex-wrap: wrap; }
    .footer-name { font-family: "EB Garamond", serif; font-size: 1.05rem; color: rgba(255,255,255,0.88); display: block; margin-bottom: 0.2rem; }
    .footer-sub { font-size: 0.66rem; letter-spacing: 0.13em; text-transform: uppercase; color: rgba(255,255,255,0.35); }
    .footer-phones { display: flex; flex-direction: column; gap: 0.35rem; text-align: center; }
    .footer-phones a { font-size: 0.79rem; color: rgba(255,255,255,0.45); text-decoration: none; transition: color 0.2s; }
    .footer-phones a:hover { color: var(--gold-light); }
    .footer-phones a span { color: rgba(255,255,255,0.25); margin-right: 0.4rem; font-size: 0.68rem; letter-spacing: 0.1em; }
    .footer-copy { font-size: 0.7rem; color: rgba(255,255,255,0.22); text-align: right; }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp { from { opacity: 0; transform: translateY(18px); } to { opacity: 1; transform: translateY(0); } }
    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    .reveal { opacity: 0; transform: translateY(20px); transition: opacity 0.65s ease, transform 0.65s ease; }
    .reveal.vis { opacity: 1; transform: translateY(0); }

    /* ── MOBILE MENU ── */
    .mobile-menu {
      display: none; position: fixed; top: 66px; left: 0; right: 0; z-index: 199;
      background: var(--white); border-top: 1px solid var(--border-lt); border-bottom: 1px solid var(--border);
      padding: 1.5rem 2rem; flex-direction: column; gap: 0.25rem;
      box-shadow: 0 8px 24px rgba(0,0,0,0.08);
    }
    .mobile-menu.open { display: flex; }
    .mobile-menu a {
      font-size: 0.83rem; letter-spacing: 0.1em; text-transform: uppercase;
      color: var(--text-mid); text-decoration: none; padding: 0.65rem 0;
      border-bottom: 1px solid var(--border-lt);
    }
    .mobile-menu a:last-child { border-bottom: none; color: var(--navy); font-weight: 500; }

    /* ── EDU GROUPS ── */
    .edu-group-label {
      font-size: 0.68rem; font-weight: 500; letter-spacing: 0.2em; text-transform: uppercase;
      color: var(--text-light); margin-bottom: 1rem; padding-bottom: 0.5rem;
      border-bottom: 1px solid var(--border);
    }
    .edu-grid--3 { display: grid; grid-template-columns: repeat(3,1fr); gap: 1.25rem; }
    .edu-grid--2 { display: grid; grid-template-columns: repeat(2,1fr); gap: 1.25rem; }

    /* ── PROC PANELS SIDE BY SIDE ── */
    .proc-panels-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; }

    /* ── NEW PATIENTS ── */
    #newpatients { background: var(--navy); }
    .newpt-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center; }
    #newpatients .label { color: var(--gold-light); }
    #newpatients .label::before { background: var(--gold-light); }
    #newpatients .heading { color: white; }
    #newpatients .rule { background: var(--gold); }
    .newpt-cards { display: flex; flex-direction: column; gap: 1rem; }
    .newpt-card {
      display: flex; justify-content: space-between; align-items: center;
      background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.12);
      padding: 1.1rem 1.5rem; text-decoration: none;
      transition: background 0.2s, border-color 0.2s; border-radius: 2px;
    }
    .newpt-card:hover { background: rgba(255,255,255,0.1); border-color: rgba(184,150,90,0.5); }
    .newpt-office { font-size: 0.78rem; font-weight: 400; letter-spacing: 0.06em; color: rgba(255,255,255,0.65); }
    .newpt-phone { font-family: "EB Garamond", serif; font-size: 1.1rem; color: var(--gold-light); }

    /* ── RESPONSIVE ── */
    @media (max-width: 1024px) {
      .section-inner { padding: 5rem 3rem; }
      nav { padding: 0 2rem; }
    }
    @media (max-width: 820px) {
      .nav-links { display: none; }
      .hamburger { display: flex; }
      nav { padding: 0 1.5rem; }
      .hero { grid-template-columns: 1fr; min-height: auto; }
      .hero-left { padding: 3rem 2rem 2.5rem; order: 2; }
      .hero-right { padding: 2.5rem 2rem 0; order: 1; justify-content: center; align-items: center; }
      .photo-wrap { max-width: 280px; }
      .section-inner { padding: 4rem 1.75rem; }
      .about-grid { grid-template-columns: 1fr; gap: 2.5rem; }
      .edu-grid, .edu-grid--3, .edu-grid--2 { grid-template-columns: 1fr; }
      .proc-panels-row { grid-template-columns: 1fr; }
      .offices-wrap { grid-template-columns: 1fr; }
      .reviews-grid { grid-template-columns: 1fr; }
      .location-extras { grid-template-columns: 1fr; }
      .newpt-inner { grid-template-columns: 1fr; gap: 2.5rem; }
      .reviews-footer { flex-direction: column; align-items: flex-start; }
      .footer-inner { flex-direction: column; text-align: center; }
      .footer-phones { text-align: center; }
      .footer-copy { text-align: center; }
      footer { padding: 2.5rem 1.75rem; }
    }
    @media (max-width: 480px) {
      .hero-name { font-size: 2rem; white-space: normal; }
      .photo-wrap { max-width: 240px; }
      .hero-actions { flex-direction: column; }
      .btn-navy, .btn-outline { text-align: center; justify-content: center; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav id="topnav">
    <a class="nav-brand" href="#">
      <div class="nav-monogram">AR</div>
      <div>
        <div class="nav-name">Allison Rice, MD</div>
        <div class="nav-cred">Bariatric &amp; General Surgery</div>
      </div>
    </a>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#procedures">Procedures</a></li>
      <li><a href="#location">Locations</a></li>
      <li><a href="#education">Education</a></li>
      <li><a href="#reviews">Reviews</a></li>
      <li><a href="#newpatients" class="nav-cta">New Patients</a></li>
    </ul>
    <div class="hamburger" id="hamburger" aria-label="Open menu">
      <span></span><span></span><span></span>
    </div>
  </nav>

  <div class="mobile-menu" id="mobileMenu">
    <a href="#about" onclick="closeMenu()">About</a>
    <a href="#procedures" onclick="closeMenu()">Procedures</a>
    <a href="#location" onclick="closeMenu()">Locations</a>
    <a href="#education" onclick="closeMenu()">Education</a>
    <a href="#reviews" onclick="closeMenu()">Reviews</a>
    <a href="#newpatients" onclick="closeMenu()">New Patients</a>
  </div>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-left">
      <div class="hero-eyebrow">Board-Certified Surgeon &mdash; Palm Beach County, FL</div>
      <h1 class="hero-name">Allison Rice, MD</h1>
      <div class="hero-specialty">Bariatric &amp; General Surgery</div>
      <div class="hero-rule"></div>
      <p class="hero-desc">Providing compassionate, expert surgical care to patients across Palm Beach County. Specializing in bariatric and minimally invasive surgery with a commitment to lasting results and patient-centered outcomes.</p>
      <div class="hero-actions">
        <a href="#location" class="btn-navy">Find a Location</a>
        <a href="#about" class="btn-outline">Meet Dr. Rice</a>
      </div>
      <div class="hero-rating">
        <div class="stars">&#9733;&#9733;&#9733;&#9733;&#9733;</div>
        <strong>5.0</strong>
        <span>Patient Rating</span>
      </div>
    </div>

    <div class="hero-right">
      <div class="photo-wrap">
        <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAYEBAUEBAYFBQUGBgYHCQ4JCQgICRINDQoOFRIWFhUSFBQXGiEcFxgfGRQUHScdHyIjJSUlFhwpLCgkKyEkJST/2wBDAQYGBgkICREJCREkGBQYJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCT/wAARCAPUArwDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD6pooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooZgoJJAA7ms+bWrZJZIVdDKgztLYJosBoUhYL1IFcbqvjSa0guLhGtxHCC20khiB6Vxfij4jR2UEccshaeWNZEcMRtzzjqQRg4zQ9NylFvY9f+3QfwvuHTK8j86r/21bHcVkRgvUhhivnjUfiZe6rM7QLFbKRtbacFh9eMY9vxrDvNZvZ9pe6uZuflIxj8z/hUucTVUH1PpafxZZQkj7TZ5GeDMufyzVGbx/p0OCbywwT0E2T+gNfN9xq2oC1EaX0+08OpkO0emQMCsO5nYsXNw4LcNtGR+VL2iKVBdz6nPxHsgpKRxzkDOIpck/mKjk+KOjQsFu5GtWJxiRGIH1IBAr5N+03UbFra62sCTlWKsalXxbr4CwvqVztA43Sdvx4pe1XYfsEfYWneN9CvyFj1O13EZ2mQZrcjnilUNHIrg91Oa+IZ9f1maJZZp3miAxuYAiprD4geINIn8yw1ae3BADKhJX8VOaPaxE8P5n23kUV8qaR+0B4kt50XUJ/PQDlkUIx/DGDXoXhz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" alt="Dr. Allison Rice, MD" />
        <div class="photo-credential">
          <div>
            <span class="cred-name">Dr. Allison Rice, MD</span>
            <span class="cred-spec">Bariatric &amp; General Surgery</span>
          </div>
          <span class="cred-badge">Board Certified</span>
        </div>
      </div>
    </div>
  </div>

  <!-- ABOUT -->
  <section id="about">
    <div class="section-inner">
      <div class="about-grid">
        <div class="about-body reveal">
          <div class="label">About</div>
          <h2 class="heading">A surgeon who<br><em>puts patients first</em></h2>
          <div class="rule"></div>
          <p>Dr. Allison Rice is a board-certified general surgeon with specialized fellowship training in bariatric and minimally invasive surgery. She practices across Palm Beach County, Florida, serving patients at three convenient locations in Atlantis and Loxahatchee.</p>
          <blockquote class="about-quote">"Dedicated to helping patients achieve their health goals through compassionate, comprehensive surgical care."</blockquote>
          <p>Affiliated with HCA Florida JFK Hospital and HCA Florida Palms West Hospital, Dr. Rice brings expertise in both traditional and advanced laparoscopic techniques, tailoring every approach to the individual patient. She is currently welcoming new patients and offers telehealth consultations.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- PROCEDURES — full-width, two panels side by side -->
  <section id="procedures">
    <div class="section-inner">
      <div class="reveal">
        <div class="label">Procedures &amp; Conditions Treated</div>
        <h2 class="heading">Comprehensive surgical<br><em>expertise</em></h2>
        <div class="rule"></div>
      </div>
      <div class="proc-panels-row reveal" style="transition-delay:0.1s">

        <!-- General Surgery panel -->
        <div class="proc-panel">
          <div class="proc-sub-header" id="gsHeader" onclick="toggleSub('gs')" role="button" aria-expanded="true" aria-controls="gsList">
            <span class="proc-sub-title">General Surgery</span>
            <button class="proc-toggle-btn open" id="gsToggleBtn" aria-label="Toggle General Surgery">
              <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><polyline points="18 15 12 9 6 15"/></svg>
              <span id="gsBtnLabel">Collapse</span>
            </button>
          </div>
          <div class="proc-scroll-fade" id="gsFade">
            <div class="proc-list-wrap" id="gsList">
              <ul class="proc-list">
                <li><span class="proc-dot"></span>Bowel Obstruction Treatment</li>
                <li><span class="proc-dot"></span>Gallbladder &amp; Biliary Tract Disease</li>
                <li><span class="proc-dot"></span>Gastroesophageal Reflux Disease (GERD)</li>
                <li><span class="proc-dot"></span>Gastrointestinal Surgery</li>
                <li><span class="proc-dot"></span>General Surgery</li>
                <li><span class="proc-dot"></span>Hernia</li>
                <li><span class="proc-dot"></span>Hernia Repair &mdash; Hiatal / GERD</li>
                <li><span class="proc-dot"></span>Inflammatory Bowel Disease</li>
                <li><span class="proc-dot"></span>Inguinal Hernia Repair</li>
                <li><span class="proc-dot"></span>Laparoscopy</li>
                <li><span class="proc-dot"></span>Remove Bowel Adhesions</li>
                <li><span class="proc-dot"></span>Robotic Surgery</li>
                <li><span class="proc-dot"></span>Thyroid Disorders</li>
                <li><span class="proc-dot"></span>Thyroid Surgery</li>
                <li><span class="proc-dot"></span>Ventral Hernia Repair</li>
              </ul>
            </div>
          </div>
          <div class="proc-count">15 procedures</div>
        </div>

        <!-- Bariatric / Weight Loss panel -->
        <div class="proc-panel">
          <div class="proc-sub-header proc-sub-header--alt" id="bwHeader" onclick="toggleSub('bw')" role="button" aria-expanded="true" aria-controls="bwList">
            <span class="proc-sub-title">Bariatric &amp; Weight Loss</span>
            <button class="proc-toggle-btn open" id="bwToggleBtn" aria-label="Toggle Bariatric">
              <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><polyline points="18 15 12 9 6 15"/></svg>
              <span id="bwBtnLabel">Collapse</span>
            </button>
          </div>
          <div class="proc-scroll-fade" id="bwFade">
            <div class="proc-list-wrap" id="bwList">
              <ul class="proc-list">
                <li><span class="proc-dot"></span>Bariatric Surgery</li>
                <li><span class="proc-dot"></span>Duodenal Switch Procedure</li>
                <li><span class="proc-dot"></span>Lap Band Surgery</li>
                <li><span class="proc-dot"></span>Medical Nutrition Assessment</li>
                <li><span class="proc-dot"></span>Medical Weight Loss</li>
                <li><span class="proc-dot"></span>Metabolic Diseases</li>
                <li><span class="proc-dot"></span>Nutritional &amp; Metabolic Disorders</li>
                <li><span class="proc-dot"></span>Obesity</li>
                <li><span class="proc-dot"></span>Revision Surgery</li>
                <li><span class="proc-dot"></span>Roux-en-Y Gastric Bypass</li>
                <li><span class="proc-dot"></span>Sleeve Gastrectomy</li>
                <li><span class="proc-dot"></span>Weight Loss Surgery</li>
              </ul>
            </div>
          </div>
          <div class="proc-count">12 procedures</div>
        </div>

      </div>
    </div>
  </section>


  <!-- LOCATIONS -->
  <section id="location">
    <div class="section-inner">
      <div class="reveal">
        <div class="label">Office Locations</div>
        <h2 class="heading">Three offices across<br><em>Palm Beach County</em></h2>
        <div class="rule"></div>
      </div>
      <div class="offices-wrap">
        <div class="office reveal" style="transition-delay:0.05s">
          <div class="office-head">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
            <span class="office-head-label">JFK Weight Management Center</span>
          </div>
          <div class="office-body">
            <div class="office-addr">5503 S Congress Ave, Suite 103<br>Atlantis, FL 33462</div>
            <a href="tel:5615482274" class="office-tel">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 9.81a19.79 19.79 0 01-3.07-8.68A2 2 0 012 .82h3a2 2 0 012 1.72c.127.96.361 1.903.7 2.81a2 2 0 01-.45 2.11L6.09 8.91a16 16 0 006 6l1.27-1.27a2 2 0 012.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0122 16.92z"/></svg>
              (561) 548-2274
            </a>
          </div>
          <div class="office-foot">
            <a href="https://maps.google.com/?q=5503+S+Congress+Ave+Suite+103+Atlantis+FL+33462" target="_blank" class="dir-link">
              <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
              Get Directions
            </a>
          </div>
        </div>
        <div class="office reveal" style="transition-delay:0.15s">
          <div class="office-head">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
            <span class="office-head-label">Palms West Weight Management Center</span>
          </div>
          <div class="office-body">
            <div class="office-addr">12977 Southern Blvd, Suite 101<br>Loxahatchee, FL 33470</div>
            <a href="tel:5618991113" class="office-tel">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 9.81a19.79 19.79 0 01-3.07-8.68A2 2 0 012 .82h3a2 2 0 012 1.72c.127.96.361 1.903.7 2.81a2 2 0 01-.45 2.11L6.09 8.91a16 16 0 006 6l1.27-1.27a2 2 0 012.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0122 16.92z"/></svg>
              (561) 899-1113
            </a>
          </div>
          <div class="office-foot">
            <a href="https://maps.google.com/?q=12977+Southern+Blvd+Suite+101+Loxahatchee+FL+33470" target="_blank" class="dir-link">
              <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
              Get Directions
            </a>
          </div>
        </div>
        <div class="office reveal" style="transition-delay:0.25s">
          <div class="office-head">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
            <span class="office-head-label">General Surgery Office</span>
          </div>
          <div class="office-body">
            <div class="office-addr">12955 Palms West Drive, Suite 201<br>Loxahatchee, FL 33470</div>
            <a href="tel:5613835200" class="office-tel">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 9.81a19.79 19.79 0 01-3.07-8.68A2 2 0 012 .82h3a2 2 0 012 1.72c.127.96.361 1.903.7 2.81a2 2 0 01-.45 2.11L6.09 8.91a16 16 0 006 6l1.27-1.27a2 2 0 012.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0122 16.92z"/></svg>
              (561) 383-5200
            </a>
          </div>
          <div class="office-foot">
            <a href="https://maps.google.com/?q=12955+Palms+West+Drive+Suite+201+Loxahatchee+FL+33470" target="_blank" class="dir-link">
              <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
              Get Directions
            </a>
          </div>
        </div>
      </div>
      <div class="location-extras reveal">
        <div class="extra">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M20 7H4a2 2 0 00-2 2v6a2 2 0 002 2h16a2 2 0 002-2V9a2 2 0 00-2-2z"/><path d="M16 21V5a2 2 0 00-2-2h-4a2 2 0 00-2 2v16"/></svg>
          <div>
            <strong>Insurance Accepted</strong>
            <p>Accepts most major plans including Highmark BCBS, Horizon BCBS, UnitedHealthCare, and others.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- EDUCATION -->
  <section id="education">
    <div class="section-inner">
      <div class="reveal">
        <div class="label">Education &amp; Training</div>
        <h2 class="heading">Rigorous training.<br><em>Refined expertise.</em></h2>
        <div class="rule"></div>
      </div>

      <!-- Academic Training group -->
      <div class="edu-group-label reveal">Academic Training</div>
      <div class="edu-grid edu-grid--3 reveal">
        <div class="edu-card">
          <svg class="edu-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M22 10v6M2 10l10-5 10 5-10 5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>
          <span class="edu-tag">Medical Degree</span>
          <div class="edu-name">Medical University of South Carolina</div>
          <div class="edu-detail">College of Medicine &middot; Charleston, SC</div>
        </div>
        <div class="edu-card">
          <svg class="edu-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="2" y="7" width="20" height="14" rx="2"/><path d="M16 7V5a2 2 0 00-2-2h-4a2 2 0 00-2 2v2"/><line x1="12" y1="12" x2="12" y2="16"/><line x1="10" y1="14" x2="14" y2="14"/></svg>
          <span class="edu-tag">Residency</span>
          <div class="edu-name">University of Miami / HCA Florida JFK</div>
          <div class="edu-detail">General Surgery Residency &middot; Palm Beach, FL</div>
        </div>
        <div class="edu-card">
          <svg class="edu-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><path d="M12 8v4l3 3"/></svg>
          <span class="edu-tag">Fellowship</span>
          <div class="edu-name">Bariatric &amp; Minimally Invasive Surgery</div>
          <div class="edu-detail">Hackensack University Medical Center<br>Advanced subspecialty training in weight loss &amp; laparoscopic techniques</div>
        </div>
      </div>

      <!-- Credentials group -->
      <div class="edu-group-label reveal" style="margin-top:2rem">Credentials &amp; Affiliations</div>
      <div class="edu-grid edu-grid--2 reveal">
        <div class="edu-card">
          <svg class="edu-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M9 11l3 3L22 4"/><path d="M21 12v7a2 2 0 01-2 2H5a2 2 0 01-2-2V5a2 2 0 012-2h11"/></svg>
          <span class="edu-tag">Board Certification</span>
          <div class="edu-name">American Board of Surgery</div>
          <div class="edu-detail">Board Certified in General Surgery</div>
        </div>
        <div class="edu-card">
          <svg class="edu-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M19 21l-7-5-7 5V5a2 2 0 012-2h10a2 2 0 012 2z"/></svg>
          <span class="edu-tag">Hospital Affiliations</span>
          <div class="edu-name">HCA Florida Health System</div>
          <div class="edu-detail">HCA Florida JFK Hospital &middot; Atlantis<br>HCA Florida Palms West &middot; Loxahatchee</div>
        </div>
      </div>
    </div>
  </section>

  <!-- NEW PATIENTS -->
  <section id="newpatients">
    <div class="section-inner newpt-inner">
      <div class="newpt-text reveal">
        <div class="label">Accepting New Patients</div>
        <h2 class="heading">Ready to start<br><em>your journey?</em></h2>
        <div class="rule"></div>
        <p style="font-size:0.95rem;line-height:1.88;color:var(--text-mid);max-width:480px;">Dr. Rice welcomes new patients across Palm Beach County. Most major insurance plans are accepted, including Highmark BCBS, Horizon BCBS, UnitedHealthCare, and others. Call any of our three locations to schedule a consultation.</p>
      </div>
      <div class="newpt-cards reveal" style="transition-delay:0.15s">
        <a href="tel:5615482274" class="newpt-card">
          <span class="newpt-office">JFK Weight Management Center</span>
          <span class="newpt-phone">(561) 548-2274</span>
        </a>
        <a href="tel:5618991113" class="newpt-card">
          <span class="newpt-office">Palms West Weight Management Center</span>
          <span class="newpt-phone">(561) 899-1113</span>
        </a>
        <a href="tel:5613835200" class="newpt-card">
          <span class="newpt-office">General Surgery Office</span>
          <span class="newpt-phone">(561) 383-5200</span>
        </a>
      </div>
    </div>
  </section>

  <!-- REVIEWS -->
  <section id="reviews">
    <div class="section-inner">
      <div class="reveal">
        <div class="label">Patient Reviews</div>
        <h2 class="heading">Trusted by<br><em>her patients</em></h2>
        <div class="rule"></div>
      </div>
      <div class="reviews-grid">
        <div class="review reveal" style="transition-delay:0.05s">
          <div class="review-mark">&ldquo;</div>
          <div class="r-stars">
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
          </div>
          <p class="r-text">"Dr. Rice was very kind and helped me realize the potential of these life-saving changes. Excellent surgeon with an uplifting bedside manner. Her team works great together."</p>
          <span class="r-author">&mdash; Verified Patient</span>
        </div>
        <div class="review reveal" style="transition-delay:0.15s">
          <div class="review-mark">&ldquo;</div>
          <div class="r-stars">
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
          </div>
          <p class="r-text">"My son needed emergency surgery and Dr. Rice performed a complicated procedure beautifully. Having worked in hospitals my whole life, she is a very competent and committed surgeon."</p>
          <span class="r-author">&mdash; Verified Patient</span>
        </div>
        <div class="review reveal" style="transition-delay:0.25s">
          <div class="review-mark">&ldquo;</div>
          <div class="r-stars">
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
          </div>
          <p class="r-text">"Dr. Rice was there for me through my procedure and throughout the healing process. She explains conditions well, is trustworthy, and her staff is genuinely friendly and supportive."</p>
          <span class="r-author">&mdash; Verified Patient</span>
        </div>
      </div>
      <div class="reviews-footer reveal">
        <div class="rating-summary">
          <span class="rating-big">5.0</span>
          <div class="rating-detail">
            <div class="r-stars">
              <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
              <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
              <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
              <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
              <svg class="r-star" viewBox="0 0 24 24" fill="currentColor"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
            </div>
            <span>Average patient rating</span>
          </div>
        </div>
        <a href="https://share.google/rAK79luUJm8Zeciav" target="_blank" class="btn-navy">See All Google Reviews &rarr;</a>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-inner">
      <div>
        <span class="footer-name">Allison Rice, MD</span>
        <span class="footer-sub">Bariatric &amp; General Surgery &middot; Palm Beach County, FL</span>
      </div>
      <div class="footer-phones">
        <a href="tel:5615482274"><span>JFK Weight Mgmt</span>(561) 548-2274</a>
        <a href="tel:5618991113"><span>Palms West Weight Mgmt</span>(561) 899-1113</a>
        <a href="tel:5613835200"><span>General Surgery</span>(561) 383-5200</a>
      </div>
      <div class="footer-copy">&copy; 2025 Allison Rice, MD<br>All rights reserved.</div>
    </div>
  </footer>

  <script>
    // Scroll reveal
    const revEls = document.querySelectorAll(".reveal");
    const revObs = new IntersectionObserver(entries => {
      entries.forEach(e => { if (e.isIntersecting) e.target.classList.add("vis"); });
    }, { threshold: 0.08 });
    revEls.forEach(el => revObs.observe(el));

    // Nav shadow
    window.addEventListener("scroll", () => {
      document.getElementById("topnav").style.boxShadow =
        window.scrollY > 20 ? "0 2px 20px rgba(30,58,82,0.08)" : "none";
    });

    // Hamburger
    const hb = document.getElementById("hamburger");
    const mm = document.getElementById("mobileMenu");
    hb.addEventListener("click", () => mm.classList.toggle("open"));
    function closeMenu() { mm.classList.remove("open"); }
    document.addEventListener("click", e => {
      if (!hb.contains(e.target) && !mm.contains(e.target)) mm.classList.remove("open");
    });

    // Procedure sub-section toggle
    function toggleSub(id) {
      const list = document.getElementById(id + 'List');
      const fade = document.getElementById(id + 'Fade');
      const btn  = document.getElementById(id + 'ToggleBtn');
      const lbl  = document.getElementById(id + 'BtnLabel');
      const hdr  = document.getElementById(id + 'Header');
      const isOpen = !list.classList.contains('collapsed');
      if (isOpen) {
        list.classList.add('collapsed');
        fade.classList.add('collapsed');
        btn.classList.remove('open');
        lbl.textContent = 'Expand';
        hdr.setAttribute('aria-expanded', 'false');
      } else {
        list.classList.remove('collapsed');
        fade.classList.remove('collapsed');
        btn.classList.add('open');
        lbl.textContent = 'Collapse';
        hdr.setAttribute('aria-expanded', 'true');
      }
    }
  </script>
</body>
</html>
