<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Gnanadarshi — Illuminate Your Learning</title>
  <link rel="preconnect" href="https://fonts.googleapis.com"/>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --ink: #0d0d0d;
      --cream: #f5f0e8;
      --gold: #c9a84c;
      --gold-light: #e8d49e;
      --terracotta: #b85c38;
      --sage: #4a6741;
      --mist: #d8e4e2;
      --shadow: rgba(13,13,13,0.12);
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--cream);
      color: var(--ink);
      font-family: 'DM Sans', sans-serif;
      font-weight: 300;
      overflow-x: hidden;
    }

    /* ── Noise texture overlay ── */
    body::before {
      content: '';
      position: fixed; inset: 0; z-index: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      opacity: 0.5;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1.4rem 4rem;
      background: rgba(245,240,232,0.88);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(201,168,76,0.25);
    }

    .nav-logo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.7rem;
      font-weight: 600;
      letter-spacing: 0.02em;
      color: var(--ink);
      text-decoration: none;
    }

    .nav-logo span { color: var(--gold); }

    .nav-links {
      display: flex; gap: 2.5rem; list-style: none;
    }

    .nav-links a {
      font-size: 0.82rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--ink);
      text-decoration: none;
      opacity: 0.7;
      transition: opacity 0.2s, color 0.2s;
    }

    .nav-links a:hover { opacity: 1; color: var(--gold); }

    .nav-cta {
      background: var(--ink);
      color: var(--cream) !important;
      opacity: 1 !important;
      padding: 0.55rem 1.4rem;
      border-radius: 2px;
      transition: background 0.2s !important;
    }

    .nav-cta:hover { background: var(--gold) !important; color: var(--ink) !important; }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      align-items: center;
      padding: 8rem 4rem 4rem;
      position: relative;
      overflow: hidden;
    }

    .hero-bg-circle {
      position: absolute;
      width: 600px; height: 600px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(201,168,76,0.18) 0%, transparent 70%);
      right: -100px; top: 50%;
      transform: translateY(-50%);
      animation: pulse 6s ease-in-out infinite;
    }

    @keyframes pulse {
      0%, 100% { transform: translateY(-50%) scale(1); opacity: 0.8; }
      50% { transform: translateY(-50%) scale(1.06); opacity: 1; }
    }

    .hero-content { z-index: 1; }

    .hero-eyebrow {
      font-size: 0.75rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 1.5rem;
      display: flex; align-items: center; gap: 0.8rem;
    }

    .hero-eyebrow::before {
      content: '';
      display: inline-block;
      width: 32px; height: 1px;
      background: var(--gold);
    }

    .hero-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(3.2rem, 6vw, 5.5rem);
      font-weight: 300;
      line-height: 1.08;
      margin-bottom: 1.8rem;
      color: var(--ink);
    }

    .hero-title em {
      font-style: italic;
      color: var(--terracotta);
    }

    .hero-sub {
      font-size: 1rem;
      line-height: 1.75;
      color: var(--ink);
      opacity: 0.65;
      max-width: 420px;
      margin-bottom: 2.8rem;
    }

    .hero-actions { display: flex; gap: 1.2rem; align-items: center; }

    .btn-primary {
      background: var(--ink);
      color: var(--cream);
      padding: 0.9rem 2.2rem;
      font-family: 'DM Sans', sans-serif;
      font-size: 0.85rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      border: none; cursor: pointer;
      text-decoration: none;
      transition: background 0.25s, transform 0.2s;
      display: inline-block;
    }

    .btn-primary:hover { background: var(--gold); color: var(--ink); transform: translateY(-2px); }

    .btn-ghost {
      color: var(--ink);
      font-size: 0.85rem;
      letter-spacing: 0.06em;
      text-decoration: none;
      display: flex; align-items: center; gap: 0.5rem;
      opacity: 0.65;
      transition: opacity 0.2s;
    }

    .btn-ghost:hover { opacity: 1; }
    .btn-ghost::after { content: '→'; font-size: 1rem; }

    .hero-visual {
      position: relative; z-index: 1;
      display: flex; justify-content: center; align-items: center;
    }

    .hero-card-stack {
      position: relative; width: 340px; height: 420px;
    }

    .hcard {
      position: absolute;
      background: white;
      border-radius: 4px;
      padding: 2rem;
      box-shadow: 0 12px 40px var(--shadow);
      transition: transform 0.3s;
    }

    .hcard:nth-child(1) {
      width: 280px; top: 0; right: 0;
      background: var(--ink); color: var(--cream);
      transform: rotate(3deg);
    }

    .hcard:nth-child(2) {
      width: 260px; top: 100px; left: 0;
      background: var(--gold-light);
      transform: rotate(-2deg);
    }

    .hcard:nth-child(3) {
      width: 270px; bottom: 0; right: 20px;
      background: var(--mist);
      transform: rotate(1deg);
    }

    .hero-card-stack:hover .hcard:nth-child(1) { transform: rotate(5deg) translateY(-8px); }
    .hero-card-stack:hover .hcard:nth-child(2) { transform: rotate(-4deg) translateY(4px); }
    .hero-card-stack:hover .hcard:nth-child(3) { transform: rotate(2deg) translateX(8px); }

    .hcard-label {
      font-size: 0.65rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      opacity: 0.6;
      margin-bottom: 0.8rem;
    }

    .hcard-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.3rem;
      font-weight: 600;
      line-height: 1.3;
    }

    .hcard-meta {
      font-size: 0.75rem;
      margin-top: 1rem;
      opacity: 0.5;
    }

    .hcard-dot {
      width: 8px; height: 8px;
      background: var(--gold);
      border-radius: 50%;
      margin-bottom: 1rem;
    }

    /* ── STATS BAR ── */
    .stats-bar {
      background: var(--ink);
      color: var(--cream);
      padding: 2.5rem 4rem;
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 2rem;
      position: relative; z-index: 1;
    }

    .stat { text-align: center; }

    .stat-num {
      font-family: 'Cormorant Garamond', serif;
      font-size: 3rem;
      font-weight: 300;
      color: var(--gold);
      line-height: 1;
    }

    .stat-label {
      font-size: 0.75rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      opacity: 0.5;
      margin-top: 0.4rem;
    }

    /* ── SECTION WRAPPER ── */
    section { position: relative; z-index: 1; }

    /* ── COURSES ── */
    .courses {
      padding: 7rem 4rem;
    }

    .section-header {
      display: flex; justify-content: space-between; align-items: flex-end;
      margin-bottom: 4rem;
    }

    .section-tag {
      font-size: 0.7rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
