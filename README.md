<!DOCTYPE html>
<html lang="kn">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>\u0c9c\u0ccd\u0c9e\u0cbe\u0ca8\u0ca6\u0cb0\u0ccd\u0cb6\u0cbf - Gnanadarshi</title>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Kannada:wght@300;400;600;700;900&family=Noto+Serif+Kannada:wght@400;700;900&display=swap" rel="stylesheet" />
  <style>
    :root {
      --saffron: #FF6B1A;
      --deep-blue: #0A1628;
      --gold: #F5C842;
      --cream: #FDF6E3;
      --teal: #0D7377;
      --light-teal: #14A085;
      --text-dark: #1A1A2E;
      --text-mid: #3A3A5C;
      --card-bg: #FFFFFF;
      --section-bg: #F4F7FB;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Noto Sans Kannada', sans-serif;
      background: var(--cream);
      color: var(--text-dark);
      overflow-x: hidden;
    }

    /* \u2500\u2500 NAV \u2500\u2500 */
    nav {
      position: fixed; top: 0; width: 100%; z-index: 1000;
      background: rgba(10, 22, 40, 0.97);
      backdrop-filter: blur(12px);
      border-bottom: 2px solid var(--saffron);
      padding: 0 1.5rem;
    }
    .nav-inner {
      max-width: 1200px; margin: auto;
      display: flex; align-items: center; justify-content: space-between;
      height: 64px;
    }
    .logo {
      display: flex; align-items: center; gap: 10px; text-decoration: none;
    }
    .logo-icon {
      width: 42px; height: 42px;
      background: linear-gradient(135deg, var(--saffron), var(--gold));
      border-radius: 10px;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.4rem; font-weight: 900;
      color: white; font-family: 'Noto Serif Kannada', serif;
      box-shadow: 0 0 14px rgba(255, 107, 26, 0.5);
    }
    .logo-text { color: #fff; font-size: 1.2rem; font-weight: 700; line-height: 1.2; }
    .logo-sub { color: var(--gold); font-size: 0.65rem; font-weight: 400; letter-spacing: 1px; }

    .nav-links { display: flex; gap: 0.2rem; list-style: none; }
    .nav-links a {
      color: #ccc; text-decoration: none;
      padding: 0.45rem 0.85rem; border-radius: 6px;
      font-size: 0.88rem; font-weight: 600;
      transition: all 0.2s;
    }
    .nav-links a:hover, .nav-links a.active {
      color: #fff; background: rgba(255, 107, 26, 0.2);
      color: var(--saffron);
    }

    .hamburger {
      display: none; flex-direction: column; gap: 5px;
      cursor: pointer; background: none; border: none; padding: 4px;
    }
    .hamburger span {
      width: 24px; height: 2px; background: #fff;
      border-radius: 2px; transition: 0.3s;
    }

    .mobile-menu {
      display: none;
      flex-direction: column;
      background: rgba(10, 22, 40, 0.98);
      padding: 1rem 1.5rem 1.5rem;
      border-top: 1px solid rgba(255,255,255,0.08);
    }
    .mobile-menu a {
      color: #ccc; text-decoration: none;
      padding: 0.75rem 0; font-size: 1rem; font-weight: 600;
      border-bottom: 1px solid rgba(255,255,255,0.08);
      transition: color 0.2s;
    }
    .mobile-menu a:hover { color: var(--saffron); }
    .mobile-menu.open { display: flex; }

    /* \u2500\u2500 HERO \u2500\u2500 */
    #home {
      min-height: 100vh;
      background: linear-gradient(160deg, var(--deep-blue) 0%, #0e2240 50%, #0d3d3f 100%);
      display: flex; align-items: center;
      padding: 100px 1.5rem 60px;
      position: relative; overflow: hidden;
    }
    #home::before {
      content: '';
      position: absolute; inset: 0;
      background: radial-gradient(ellipse 60% 60% at 80% 50%, rgba(255,107,26,0.1) 0%, transparent 70%),
                  radial-gradient(ellipse 50% 50% at 20% 80%, rgba(13,115,119,0.15) 0%, transparent 70%);
    }
    .hero-dots {
      position: absolute; inset: 0; pointer-events: none;
      background-image: radial-gradient(rgba(255,255,255,0.06) 1px, transparent 1px);
      background-size: 32px 32px;
    }
    .hero-inner {
      position: relative; z-index: 2;
      max-width: 1200px; margin: auto; width: 100%;
      display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center;
    }
    .hero-badge {
      display: inline-flex; align-items: center; gap: 8px;
      background: rgba(245, 200, 66, 0.15);
      border: 1px solid rgba(245, 200, 66, 0.4);
      color: var(--gold); padding: 0.4rem 1rem;
      border-radius: 50px; font-size: 0.8rem; font-weight: 600;
      margin-bottom: 1.2rem; letter-spacing: 0.5px;
    }
    .hero-title {
      font-family: 'Noto Serif Kannada', serif;
      font-size: clamp(2.2rem, 5vw, 3.8rem);
      font-weight: 900; color: #fff; line-height: 1.15;
      margin-bottom: 1rem;
    }
    .hero-title .highlight {
      background: linear-gradient(90deg, var(--saffron), var(--gold));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    }
    .hero-desc {
      color: rgba(255,255,255,0.72); font-size: 1.05rem;
      line-height: 1.8; margin-bottom: 2rem;
    }
    .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; }
    .btn-primary {
      background: linear-gradient(135deg, var(--saffron), #e05a0a);
      color: #fff; padding: 0.85rem 1.8rem;
      border-radius: 10px; font-weight: 700; font-size: 0.95rem;
      text-decoration: none; border: none; cursor: pointer;
      box-shadow: 0 4px 20px rgba(255,107,26,0.4);
      transition: transform 0.2s, box-shadow 0.2s;
      font-family: 'Noto Sans Kannada', sans-serif;
    }
    .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 6px 28px rgba(255,107,26,0.55); }
    .btn-outline {
      background: transparent;
      color: #fff; padding: 0.85rem 1.8rem;
      border-radius: 10px; font-weight: 700; font-size: 0.95rem;
      text-decoration: none; border: 2px solid rgba(255,255,255,0.3);
      transition: all 0.2s; font-family: 'Noto Sans Kannada', sans-serif;
      cursor: pointer;
    }
    .btn-outline:hover { border-color: var(--gold); color: var(--gold); }

    .hero-stats {
      display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem;
    }
    .stat-card {
      background: rgba(255,255,255,0.07);
      border: 1px solid rgba(255,255,255,0.12);
      border-radius: 14px; padding: 1.5rem;
      text-align: center;
      backdrop-filter: blur(8px);
      transition: transform 0.3s, background 0.3s;
    }
    .stat-card:hover { transform: translateY(-4px); background: rgba(255,255,255,0.11); }
    .stat-num {
      font-size: 2.2rem; font-weight: 900;
      background: linear-gradient(90deg, var(--saffron), var(--gold));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      line-height: 1;
    }
    .stat-label { color: rgba(255,255,255,0.6); font-size: 0.82rem; margin-top: 0.4rem; }

    /* \u2500\u2500 SECTIONS COMMON \u2500\u2500 */
    section { padding: 80px 1.5rem; }
    .section-inner { max-width: 1200px; margin: auto; }
    .section-tag {
      display: inline-flex; align-items: center; gap: 6px;
      color: var(--saffron); font-size: 0.8rem; font-weight: 700;
      letter-spacing: 1.5px; text-transform: uppercase;
      margin-bottom: 0.6rem;
    }
    .section-tag::before { content: ''; width: 24px; height: 2px; background: var(--saffron); }
    .section-title {
      font-family: 'Noto Serif Kannada', serif;
      font-size: clamp(1.6rem, 3vw, 2.4rem);
      font-weight: 800; color: var(--text-dark);
      margin-bottom: 0.8rem;
    }
    .section-desc { color: var(--text-mid); font-size: 1rem; max-width: 600px; line-height: 1.7; }

    /* \u2500\u2500 CURRENT AFFAIRS \u2500\u2500 */
    #current-affairs { background: var(--section-bg); }
    .affairs-grid {
      display: grid; grid-template-columns: repeat
