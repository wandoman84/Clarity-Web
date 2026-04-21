<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Clarity — Site Wireframes</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;800&family=Figtree:wght@300;400;500;600&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --cream: #faf7f2;
    --warm: #f0ebe0;
    --ink: #1a1612;
    --ink2: #3d3530;
    --muted: #9b8f85;
    --accent: #c8693a;
    --accent2: #2d6a4f;
    --light-border: rgba(26,22,18,0.1);
    --font-display: 'Playfair Display', serif;
    --font-body: 'Figtree', sans-serif;
    --radius: 12px;
  }

  body {
    font-family: var(--font-body);
    background: #e8e3db;
    color: var(--ink);
    line-height: 1.6;
  }

  /* PAGE NAV */
  .page-switcher {
    position: fixed; top: 0; left: 0; right: 0; z-index: 1000;
    background: var(--ink); display: flex; align-items: center;
    padding: 0.6rem 1.5rem; gap: 0.5rem; overflow-x: auto;
    scrollbar-width: none;
  }
  .page-switcher::-webkit-scrollbar { display: none; }
  .page-switcher span {
    color: rgba(255,255,255,0.5); font-size: 0.72rem; font-weight: 600;
    letter-spacing: 0.08em; text-transform: uppercase; margin-right: 0.5rem; white-space: nowrap;
  }
  .page-btn {
    background: rgba(255,255,255,0.08); border: 1px solid rgba(255,255,255,0.15);
    color: rgba(255,255,255,0.7); padding: 0.35rem 0.9rem; border-radius: 99px;
    font-family: var(--font-body); font-size: 0.78rem; cursor: pointer;
    white-space: nowrap; transition: all 0.15s;
  }
  .page-btn:hover { background: rgba(255,255,255,0.15); color: white; }
  .page-btn.active { background: var(--accent); border-color: var(--accent); color: white; }

  /* SCREEN WRAPPER */
  .screen { display: none; padding-top: 48px; min-height: 100vh; }
  .screen.active { display: block; }

  /* ═══════════════════════════════════════════
     HOMEPAGE
  ═══════════════════════════════════════════ */
  .hp-nav {
    background: var(--cream); border-bottom: 1px solid var(--light-border);
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.1rem 3rem;
    position: sticky; top: 48px; z-index: 50;
  }
  .hp-logo { font-family: var(--font-display); font-size: 1.4rem; font-weight: 800; color: var(--ink); }
  .hp-logo sup { font-size: 0.5em; color: var(--accent); vertical-align: super; }
  .hp-nav-links { display: flex; gap: 2rem; }
  .hp-nav-links a {
    color: var(--ink2); font-size: 0.88rem; text-decoration: none; font-weight: 500;
    transition: color 0.15s;
  }
  .hp-nav-links a:hover { color: var(--accent); }
  .hp-nav-ctas { display: flex; gap: 0.75rem; align-items: center; }
  .btn-sm {
    padding: 0.5rem 1.2rem; border-radius: 8px; font-family: var(--font-body);
    font-size: 0.85rem; font-weight: 600; cursor: pointer; border: none; transition: all 0.15s;
  }
  .btn-ghost-sm { background: transparent; border: 1px solid var(--light-border); color: var(--ink2); }
  .btn-ghost-sm:hover { border-color: var(--accent); color: var(--accent); }
  .btn-accent { background: var(--accent); color: white; }
  .btn-accent:hover { background: #b5572e; }

  .hp-hero {
    background: var(--cream);
    padding: 6rem 3rem 5rem;
    display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center;
  }
  .hp-hero-eyebrow {
    display: inline-flex; align-items: center; gap: 0.5rem;
    font-size: 0.75rem; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase;
    color: var(--accent); margin-bottom: 1.5rem;
  }
  .hp-hero-eyebrow::before { content: ''; display: block; width: 24px; height: 2px; background: var(--accent); }
  .hp-hero h1 {
    font-family: var(--font-display); font-size: clamp(2.6rem, 4vw, 3.8rem);
    font-weight: 800; line-height: 1.1; letter-spacing: -0.02em; margin-bottom: 1.5rem;
  }
  .hp-hero h1 em { font-style: italic; color: var(--accent); }
  .hp-hero p { color: var(--ink2); max-width: 440px; margin-bottom: 2.5rem; font-size: 1.05rem; line-height: 1.75; }
  .hp-hero-ctas { display: flex; gap: 1rem; align-items: center; }
  .btn-lg {
    padding: 0.9rem 2rem; border-radius: 10px; font-family: var(--font-body);
    font-size: 0.95rem; font-weight: 600; cursor: pointer; border: none; transition: all 0.2s;
  }
  .btn-accent-lg { background: var(--accent); color: white; }
  .btn-accent-lg:hover { background: #b5572e; transform: translateY(-1px); }
  .btn-outline-lg { background: transparent; border: 1.5px solid var(--light-border); color: var(--ink2); }
  .btn-outline-lg:hover { border-color: var(--ink); }
  .hp-trust { display: flex; gap: 1.5rem; margin-top: 2.5rem; }
  .hp-trust-item { font-size: 0.8rem; color: var(--muted); display: flex; align-items: center; gap: 0.4rem; }
  .hp-trust-item::before { content: '✓'; color: var(--accent2); font-weight: 700; }

  .hp-hero-visual {
    background: white; border-radius: 20px; padding: 1.75rem;
    box-shadow: 0 20px 60px rgba(26,22,18,0.12); position: relative;
  }
  .hp-visual-label {
    font-size: 0.7rem; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase;
    color: var(--muted); margin-bottom: 1rem;
  }
  .hp-visual-plans { display: flex; flex-direction: column; gap: 0.75rem; }
  .hp-visual-plan {
    display: flex; align-items: center; gap: 1rem; padding: 1rem; border-radius: 10px;
    border: 1.5px solid var(--light-border); transition: all 0.15s;
  }
  .hp-visual-plan.top { border-color: var(--accent); background: rgba(200,105,58,0.04); }
  .hp-visual-plan-icon { font-size: 1.4rem; }
  .hp-visual-plan-info { flex: 1; }
  .hp-visual-plan-name { font-weight: 600; font-size: 0.88rem; margin-bottom: 0.2rem; }
  .hp-visual-plan-type { font-size: 0.73rem; color: var(--muted); }
  .hp-visual-plan-score {
    font-family: var(--font-display); font-size: 1.3rem; font-weight: 700;
  }
  .hp-visual-plan-score.high { color: var(--accent2); }
  .hp-visual-plan-score.mid { color: var(--accent); }
  .hp-visual-plan-score.low { color: var(--muted); }
  .hp-visual-badge {
    position: absolute; top: -14px; right: 24px;
    background: var(--accent2); color: white; font-size: 0.7rem; font-weight: 700;
    padding: 0.3rem 0.9rem; border-radius: 99px; letter-spacing: 0.06em;
  }

  .hp-how { background: var(--warm); padding: 6rem 3rem; text-align: center; }
  .section-eyebrow {
    font-size: 0.72rem; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase;
    color: var(--accent); margin-bottom: 1rem;
  }
  .section-title {
    font-family: var(--font-display); font-size: clamp(1.8rem, 3vw, 2.6rem);
    font-weight: 800; margin-bottom: 1rem; line-height: 1.2;
  }
  .section-sub { color: var(--ink2); max-width: 520px; margin: 0 auto 3.5rem; font-size: 1rem; }
  .how-steps { display: grid; grid-template-columns: repeat(3, 1fr); gap: 2rem; max-width: 900px; margin: 0 auto; }
  .how-step { text-align: left; }
  .how-step-num {
    font-family: var(--font-display); font-size: 3rem; font-weight: 800;
    color: rgba(200,105,58,0.2); line-height: 1; margin-bottom: 1rem;
  }
  .how-step-title { font-weight: 700; font-size: 1rem; margin-bottom: 0.5rem; }
  .how-step-desc { color: var(--ink2); font-size: 0.88rem; line-height: 1.7; }

  .hp-features { background: var(--cream); padding: 6rem 3rem; }
  .features-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; max-width: 960px; margin: 0 auto; }
  .feature-card {
    background: white; border-radius: var(--radius); padding: 1.75rem;
    border: 1px solid var(--light-border);
  }
  .feature-icon { font-size: 1.75rem; margin-bottom: 1rem; }
  .feature-title { font-weight: 700; margin-bottom: 0.5rem; }
  .feature-desc { font-size: 0.85rem; color: var(--ink2); line-height: 1.7; }

  .hp-social { background: var(--ink); padding: 6rem 3rem; text-align: center; }
  .hp-social .section-title { color: white; }
  .hp-social .section-sub { color: rgba(255,255,255,0.5); }
  .testimonials { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; max-width: 960px; margin: 0 auto; }
  .testimonial {
    background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.1);
    border-radius: var(--radius); padding: 1.75rem; text-align: left;
  }
  .testimonial-quote { color: rgba(255,255,255,0.8); font-size: 0.9rem; line-height: 1.7; margin-bottom: 1.25rem; font-style: italic; }
  .testimonial-author { color: rgba(255,255,255,0.5); font-size: 0.8rem; font-weight: 600; }
  .testimonial-role { color: rgba(255,255,255,0.3); font-size: 0.75rem; }

  .hp-cta { background: var(--accent); padding: 5rem 3rem; text-align: center; }
  .hp-cta h2 { font-family: var(--font-display); font-size: 2.5rem; font-weight: 800; color: white; margin-bottom: 1rem; }
  .hp-cta p { color: rgba(255,255,255,0.8); max-width: 480px; margin: 0 auto 2rem; }
  .btn-white { background: white; color: var(--accent); }

  .hp-footer {
    background: var(--ink); padding: 2.5rem 3rem;
    display: flex; justify-content: space-between; align-items: center;
    border-top: 1px solid rgba(255,255,255,0.08);
  }
  .hp-footer-logo { font-family: var(--font-display); color: white; font-size: 1.1rem; }
  .hp-footer-links { display: flex; gap: 1.5rem; }
  .hp-footer-links a { color: rgba(255,255,255,0.4); font-size: 0.8rem; text-decoration: none; }
  .hp-footer-copy { color: rgba(255,255,255,0.3); font-size: 0.78rem; }

  /* ═══════════════════════════════════════════
     AUTH — SIGN UP / LOG IN
  ═══════════════════════════════════════════ */
  .auth-screen {
    background: var(--cream); min-height: calc(100vh - 48px);
    display: grid; grid-template-columns: 1fr 1fr;
  }
  .auth-left {
    background: var(--ink); padding: 4rem;
    display: flex; flex-direction: column; justify-content: space-between;
  }
  .auth-left-logo { font-family: var(--font-display); color: white; font-size: 1.4rem; }
  .auth-left-body { flex: 1; display: flex; flex-direction: column; justify-content: center; }
  .auth-left h2 {
    font-family: var(--font-display); font-size: 2.2rem; font-weight: 800; color: white;
    line-height: 1.2; margin-bottom: 1.25rem;
  }
  .auth-left h2 em { font-style: italic; color: var(--accent); }
  .auth-left p { color: rgba(255,255,255,0.55); line-height: 1.7; max-width: 380px; margin-bottom: 2.5rem; }
  .auth-left-bullets { display: flex; flex-direction: column; gap: 1rem; }
  .auth-bullet { display: flex; align-items: center; gap: 0.75rem; }
  .auth-bullet-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--accent); flex-shrink: 0; }
  .auth-bullet-text { color: rgba(255,255,255,0.7); font-size: 0.88rem; }
  .auth-left-footer { color: rgba(255,255,255,0.25); font-size: 0.75rem; }

  .auth-right {
    padding: 4rem; display: flex; flex-direction: column;
    justify-content: center; align-items: center;
  }
  .auth-form-wrap { width: 100%; max-width: 400px; }
  .auth-tabs { display: flex; gap: 0; margin-bottom: 2.5rem; border-bottom: 2px solid var(--light-border); }
  .auth-tab {
    padding: 0.75rem 1.5rem; font-weight: 600; font-size: 0.9rem; cursor: pointer;
    border-bottom: 2px solid transparent; margin-bottom: -2px; color: var(--muted);
    transition: all 0.15s;
  }
  .auth-tab.active { color: var(--ink); border-bottom-color: var(--accent); }
  .auth-form-title { font-family: var(--font-display); font-size: 1.6rem; font-weight: 700; margin-bottom: 0.4rem; }
  .auth-form-sub { color: var(--muted); font-size: 0.88rem; margin-bottom: 2rem; }
  .form-field { margin-bottom: 1.1rem; }
  .form-label { font-size: 0.78rem; font-weight: 600; color: var(--ink2); margin-bottom: 0.4rem; display: block; letter-spacing: 0.04em; }
  .form-input {
    width: 100%; padding: 0.75rem 1rem; border: 1.5px solid var(--light-border);
    border-radius: 8px; font-family: var(--font-body); font-size: 0.9rem;
    background: white; color: var(--ink); outline: none; transition: border-color 0.15s;
  }
  .form-input:focus { border-color: var(--accent); }
  .form-input::placeholder { color: #c4b8af; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 0.75rem; }
  .btn-full {
    width: 100%; padding: 0.9rem; border-radius: 10px; font-family: var(--font-body);
    font-size: 0.95rem; font-weight: 600; cursor: pointer; border: none; margin-top: 0.5rem;
  }
  .auth-divider { text-align: center; color: var(--muted); font-size: 0.8rem; margin: 1.25rem 0; position: relative; }
  .auth-divider::before, .auth-divider::after {
    content: ''; position: absolute; top: 50%; width: calc(50% - 1.5rem);
    height: 1px; background: var(--light-border);
  }
  .auth-divider::before { left: 0; }
  .auth-divider::after { right: 0; }
  .btn-social {
    width: 100%; padding: 0.75rem; border-radius: 8px; background: white;
    border: 1.5px solid var(--light-border); font-family: var(--font-body);
    font-size: 0.88rem; font-weight: 500; cursor: pointer; display: flex;
    align-items: center; justify-content: center; gap: 0.5rem; color: var(--ink2);
  }
  .auth-footer-note { text-align: center; font-size: 0.8rem; color: var(--muted); margin-top: 1.5rem; }
  .auth-footer-note a { color: var(--accent); text-decoration: none; font-weight: 600; }
  .role-picker { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0.6rem; margin-bottom: 1.25rem; }
  .role-btn {
    padding: 0.75rem 0.5rem; border-radius: 8px; border: 1.5px solid var(--light-border);
    background: white; cursor: pointer; text-align: center; transition: all 0.15s;
  }
  .role-btn.selected { border-color: var(--accent); background: rgba(200,105,58,0.05); }
  .role-btn-icon { font-size: 1.25rem; margin-bottom: 0.3rem; }
  .role-btn-label { font-size: 0.72rem; font-weight: 600; color: var(--ink2); }

  /* ═══════════════════════════════════════════
     ONBOARDING
  ═══════════════════════════════════════════ */
  .onboard-screen { background: var(--cream); min-height: calc(100vh - 48px); }
  .onboard-top {
    background: white; border-bottom: 1px solid var(--light-border);
    padding: 1.1rem 3rem; display: flex; align-items: center; justify-content: space-between;
    position: sticky; top: 48px; z-index: 50;
  }
  .onboard-logo { font-family: var(--font-display); font-size: 1.2rem; font-weight: 800; }
  .onboard-progress { display: flex; align-items: center; gap: 0.5rem; }
  .prog-step {
    display: flex; align-items: center; gap: 0.4rem;
    font-size: 0.78rem; font-weight: 600; color: var(--muted);
  }
  .prog-step.done { color: var(--accent2); }
  .prog-step.active { color: var(--accent); }
  .prog-dot {
    width: 24px; height: 24px; border-radius: 50%; border: 2px solid currentColor;
    display: flex; align-items: center; justify-content: center; font-size: 0.65rem; font-weight: 700;
  }
  .prog-step.done .prog-dot { background: var(--accent2); border-color: var(--accent2); color: white; }
  .prog-step.active .prog-dot { background: var(--accent); border-color: var(--accent); color: white; }
  .prog-line { width: 40px; height: 2px; background: var(--light-border); }
  .prog-line.done { background: var(--accent2); }
  .onboard-skip { font-size: 0.8rem; color: var(--muted); cursor: pointer; }

  .onboard-body { max-width: 680px; margin: 0 auto; padding: 4rem 2rem; }
  .onboard-step-label { font-size: 0.72rem; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase; color: var(--accent); margin-bottom: 0.75rem; }
  .onboard-title { font-family: var(--font-display); font-size: 2rem; font-weight: 800; margin-bottom: 0.6rem; line-height: 1.2; }
  .onboard-sub { color: var(--ink2); margin-bottom: 2.5rem; font-size: 0.95rem; }

  .source-cards { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-bottom: 2rem; }
  .source-card {
    background: white; border: 2px solid var(--light-border); border-radius: var(--radius);
    padding: 1.75rem; cursor: pointer; transition: all 0.15s;
  }
  .source-card:hover { border-color: rgba(200,105,58,0.4); }
  .source-card.selected { border-color: var(--accent); background: rgba(200,105,58,0.04); }
  .source-card-icon { font-size: 2rem; margin-bottom: 1rem; }
  .source-card-title { font-weight: 700; margin-bottom: 0.4rem; }
  .source-card-desc { font-size: 0.82rem; color: var(--muted); line-height: 1.6; }

  .upload-box {
    background: white; border: 2px dashed var(--light-border); border-radius: var(--radius);
    padding: 3rem; text-align: center; cursor: pointer; transition: all 0.15s; margin-bottom: 1.5rem;
  }
  .upload-box:hover { border-color: var(--accent); }
  .upload-box-icon { font-size: 2.5rem; margin-bottom: 1rem; }
  .upload-box-title { font-weight: 600; margin-bottom: 0.3rem; }
  .upload-box-sub { font-size: 0.82rem; color: var(--muted); }

  .onboard-form { background: white; border-radius: var(--radius); padding: 1.75rem; margin-bottom: 1.5rem; }
  .onboard-form-title { font-weight: 700; margin-bottom: 1.25rem; font-size: 0.95rem; }
  .form-grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 0.9rem; }
  .chip-group { display: flex; flex-wrap: wrap; gap: 0.5rem; margin-top: 0.5rem; }
  .chip {
    padding: 0.35rem 0.8rem; border-radius: 99px; font-size: 0.78rem; font-weight: 500;
    border: 1.5px solid var(--light-border); cursor: pointer; transition: all 0.15s; background: white;
    color: var(--ink2);
  }
  .chip.selected { background: rgba(200,105,58,0.08); border-color: var(--accent); color: var(--accent); }
  .onboard-actions { display: flex; justify-content: space-between; align-items: center; }
  .btn-back { background: transparent; border: 1.5px solid var(--light-border); color: var(--muted); }

  /* ═══════════════════════════════════════════
     DASHBOARD
  ═══════════════════════════════════════════ */
  .dash-layout { display: grid; grid-template-columns: 220px 1fr; min-height: calc(100vh - 48px); }

  .dash-sidebar {
    background: var(--ink); padding: 2rem 1.25rem;
    display: flex; flex-direction: column; gap: 0.25rem;
    position: sticky; top: 48px; height: calc(100vh - 48px); overflow-y: auto;
  }
  .dash-logo { font-family: var(--font-display); color: white; font-size: 1.2rem; margin-bottom: 2rem; padding: 0 0.75rem; }
  .dash-section-label {
    font-size: 0.65rem; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase;
    color: rgba(255,255,255,0.25); padding: 0.75rem 0.75rem 0.4rem; margin-top: 0.5rem;
  }
  .dash-nav-item {
    display: flex; align-items: center; gap: 0.75rem; padding: 0.65rem 0.75rem;
    border-radius: 8px; cursor: pointer; color: rgba(255,255,255,0.5); font-size: 0.85rem;
    font-weight: 500; transition: all 0.15s;
  }
  .dash-nav-item:hover { background: rgba(255,255,255,0.06); color: rgba(255,255,255,0.8); }
  .dash-nav-item.active { background: rgba(200,105,58,0.15); color: white; }
  .dash-nav-item.active .dash-nav-icon { color: var(--accent); }
  .dash-nav-icon { font-size: 1rem; width: 18px; text-align: center; }
  .dash-sidebar-footer { margin-top: auto; }
  .dash-user {
    display: flex; align-items: center; gap: 0.75rem; padding: 0.75rem;
    border-radius: 8px; border: 1px solid rgba(255,255,255,0.08);
  }
  .dash-avatar {
    width: 32px; height: 32px; border-radius: 50%; background: var(--accent);
    display: flex; align-items: center; justify-content: center; font-size: 0.8rem;
    font-weight: 700; color: white; flex-shrink: 0;
  }
  .dash-user-name { font-size: 0.82rem; color: rgba(255,255,255,0.7); font-weight: 500; }
  .dash-user-role { font-size: 0.7rem; color: rgba(255,255,255,0.3); }

  .dash-main { background: var(--cream); padding: 2.5rem; overflow-y: auto; }
  .dash-header { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 2rem; }
  .dash-greeting { font-family: var(--font-display); font-size: 1.6rem; font-weight: 800; margin-bottom: 0.3rem; }
  .dash-date { color: var(--muted); font-size: 0.85rem; }
  .dash-header-actions { display: flex; gap: 0.75rem; }

  .dash-stat-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.25rem; margin-bottom: 2rem; }
  .dash-stat {
    background: white; border-radius: var(--radius); padding: 1.5rem;
    border: 1px solid var(--light-border);
  }
  .dash-stat-label { font-size: 0.75rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.06em; margin-bottom: 0.5rem; font-weight: 600; }
  .dash-stat-val { font-family: var(--font-display); font-size: 2rem; font-weight: 800; line-height: 1; margin-bottom: 0.4rem; }
  .dash-stat-val.green { color: var(--accent2); }
  .dash-stat-val.orange { color: var(--accent); }
  .dash-stat-change { font-size: 0.78rem; color: var(--muted); }
  .dash-stat-change.up { color: var(--accent2); }

  .dash-two-col { display: grid; grid-template-columns: 1fr 360px; gap: 1.25rem; margin-bottom: 1.25rem; }

  .dash-card { background: white; border-radius: var(--radius); padding: 1.5rem; border: 1px solid var(--light-border); }
  .dash-card-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 1.25rem; }
  .dash-card-title { font-weight: 700; font-size: 0.95rem; }
  .dash-card-action { font-size: 0.78rem; color: var(--accent); cursor: pointer; font-weight: 600; }

  .plan-row {
    display: flex; align-items: center; gap: 1rem; padding: 1rem 0;
    border-bottom: 1px solid var(--light-border);
  }
  .plan-row:last-child { border-bottom: none; }
  .plan-row-icon { font-size: 1.5rem; }
  .plan-row-info { flex: 1; }
  .plan-row-name { font-weight: 600; font-size: 0.9rem; margin-bottom: 0.15rem; }
  .plan-row-type { font-size: 0.75rem; color: var(--muted); }
  .plan-row-score-wrap { text-align: right; }
  .plan-row-score { font-family: var(--font-display); font-size: 1.2rem; font-weight: 800; }
  .plan-row-score.high { color: var(--accent2); }
  .plan-row-score.mid { color: var(--accent); }
  .plan-row-score.low { color: var(--muted); }
  .plan-row-label { font-size: 0.68rem; color: var(--muted); }
  .plan-row-bar { height: 4px; border-radius: 99px; background: var(--warm); margin-top: 0.4rem; overflow: hidden; }
  .plan-row-fill { height: 100%; border-radius: 99px; background: var(--accent2); }

  .alert-list { display: flex; flex-direction: column; gap: 0.75rem; }
  .alert-item {
    display: flex; gap: 0.75rem; padding: 0.85rem; border-radius: 8px;
    background: var(--warm); border: 1px solid var(--light-border);
  }
  .alert-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; margin-top: 4px; }
  .alert-dot.orange { background: var(--accent); }
  .alert-dot.green { background: var(--accent2); }
  .alert-dot.red { background: #d95858; }
  .alert-text { font-size: 0.82rem; line-height: 1.5; color: var(--ink2); }
  .alert-text strong { color: var(--ink); }

  .claims-mini { display: flex; flex-direction: column; gap: 0.6rem; }
  .claim-row {
    display: flex; justify-content: space-between; align-items: center;
    font-size: 0.83rem; padding: 0.6rem 0; border-bottom: 1px solid var(--light-border);
  }
  .claim-row:last-child { border-bottom: none; }
  .claim-name { color: var(--ink2); }
  .claim-amount { font-weight: 700; }
  .claim-date { color: var(--muted); font-size: 0.75rem; }

  /* ANNOTATIONS */
  .annotation {
    display: inline-block; background: #fff9c4; border: 1px solid #f0d84e;
    border-radius: 4px; padding: 0.2rem 0.5rem; font-size: 0.7rem; font-weight: 600;
    color: #7a6a00; margin-left: 0.5rem; vertical-align: middle;
  }

  @media (max-width: 768px) {
    .hp-hero, .auth-screen, .dash-layout, .dash-two-col { grid-template-columns: 1fr; }
    .auth-left { display: none; }
    .dash-sidebar { display: none; }
    .how-steps, .features-grid, .testimonials, .hp-stat-row { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- PAGE SWITCHER -->
<div class="page-switcher">
  <span>Pages:</span>
  <button class="page-btn active" onclick="show('homepage')">🏠 Homepage</button>
  <button class="page-btn" onclick="show('auth')">🔐 Sign Up / Log In</button>
  <button class="page-btn" onclick="show('onboard')">🚀 Onboarding</button>
  <button class="page-btn" onclick="show('dashboard')">📊 Dashboard</button>
</div>

<!-- ═══════════════════════ HOMEPAGE ═══════════════════════ -->
<div id="homepage" class="screen active">

  <!-- NAV -->
  <nav class="hp-nav">
    <div class="hp-logo">Clarity<sup>✦</sup></div>
    <div class="hp-nav-links">
      <a href="#">How it works</a>
      <a href="#">Features</a>
      <a href="#">Pricing</a>
      <a href="#">For Brokers</a>
    </div>
    <div class="hp-nav-ctas">
      <button class="btn-sm btn-ghost-sm">Log In</button>
      <button class="btn-sm btn-accent">Get Started Free</button>
    </div>
  </nav>

  <!-- HERO -->
  <section class="hp-hero">
    <div>
      <div class="hp-hero-eyebrow">AI-Powered Benefits Matching</div>
      <h1>Find the plan that fits your <em>actual</em> health story</h1>
      <p>Upload your claims, connect your employer benefits or the government marketplace — and get a ranked, personalized recommendation in under 2 minutes.</p>
      <div class="hp-hero-ctas">
        <button class="btn-lg btn-accent-lg">Get My Recommendations →</button>
        <button class="btn-lg btn-outline-lg">See how it works</button>
      </div>
      <div class="hp-trust">
        <div class="hp-trust-item">No account required to start</div>
        <div class="hp-trust-item">HIPAA-compliant</div>
        <div class="hp-trust-item">Free for individuals</div>
      </div>
    </div>
    <div class="hp-hero-visual">
      <div class="hp-visual-badge">Your Results</div>
      <div class="hp-visual-label">Ranked by match score</div>
      <div class="hp-visual-plans">
        <div class="hp-visual-plan top">
          <div class="hp-visual-plan-icon">🏥</div>
          <div class="hp-visual-plan-info">
            <div class="hp-visual-plan-name">Blue Shield PPO Gold</div>
            <div class="hp-visual-plan-type">PPO · $420/mo · Best for your conditions</div>
          </div>
          <div class="hp-visual-plan-score high">94%</div>
        </div>
        <div class="hp-visual-plan">
          <div class="hp-visual-plan-icon">💎</div>
          <div class="hp-visual-plan-info">
            <div class="hp-visual-plan-name">Kaiser HMO Silver</div>
            <div class="hp-visual-plan-type">HMO · $290/mo · Integrated care</div>
          </div>
          <div class="hp-visual-plan-score mid">71%</div>
        </div>
        <div class="hp-visual-plan">
          <div class="hp-visual-plan-icon">⚕️</div>
          <div class="hp-visual-plan-info">
            <div class="hp-visual-plan-name">Cigna HDHP + HSA</div>
            <div class="hp-visual-plan-type">HDHP · $195/mo · Low utilizer pick</div>
          </div>
          <div class="hp-visual-plan-score low">48%</div>
        </div>
      </div>
    </div>
  </section>

  <!-- HOW IT WORKS -->
  <section class="hp-how">
    <div class="section-eyebrow">How it works</div>
    <h2 class="section-title">From claims to clarity in 3 steps</h2>
    <p class="section-sub">No jargon. No confusion. Just a clear answer matched to how you actually use healthcare.</p>
    <div class="how-steps">
      <div class="how-step">
        <div class="how-step-num">01</div>
        <div class="how-step-title">Connect your data</div>
        <div class="how-step-desc">Upload an EOB or claims CSV from your insurer, or enter your totals manually. We only use this to match you — never sell it.</div>
      </div>
      <div class="how-step">
        <div class="how-step-num">02</div>
        <div class="how-step-title">Tell us your priorities</div>
        <div class="how-step-desc">Flag conditions, family size, budget, and network preference. Takes 60 seconds.</div>
      </div>
      <div class="how-step">
        <div class="how-step-num">03</div>
        <div class="how-step-title">Get ranked recommendations</div>
        <div class="how-step-desc">We score every available plan against your profile and rank them by actual fit — with plain-English explanations for each.</div>
      </div>
    </div>
  </section>

  <!-- FEATURES -->
  <section class="hp-features">
    <div style="text-align:center; margin-bottom:3rem;">
      <div class="section-eyebrow">Features</div>
      <h2 class="section-title">Everything you need to choose with confidence</h2>
    </div>
    <div class="features-grid">
      <div class="feature-card">
        <div class="feature-icon">📊</div>
        <div class="feature-title">Claims-Based Matching</div>
        <div class="feature-desc">We use your actual claims history — not averages — to predict what your costs would be under each plan.</div>
      </div>
      <div class="feature-card">
        <div class="feature-icon">🏛️</div>
        <div class="feature-title">Live Marketplace Data</div>
        <div class="feature-desc">Real-time plan data pulled directly from Healthcare.gov for your zip code and income bracket.</div>
      </div>
      <div class="feature-card">
        <div class="feature-icon">🏢</div>
        <div class="feature-title">Group Benefits Upload</div>
        <div class="feature-desc">Upload your employer's benefits summary (PDF or CSV) and we'll parse every plan detail automatically.</div>
      </div>
      <div class="feature-card">
        <div class="feature-icon">💊</div>
        <div class="feature-title">Drug & Condition Coverage</div>
        <div class="feature-desc">See exactly which plans cover your medications and flag gaps in coverage for chronic conditions.</div>
      </div>
      <div class="feature-card">
        <div class="feature-icon">📋</div>
        <div class="feature-title">Side-by-Side Comparison</div>
        <div class="feature-desc">Compare up to 3 plans at once with a clear breakdown of premiums, deductibles, OOP max, and network.</div>
      </div>
      <div class="feature-card">
        <div class="feature-icon">📤</div>
        <div class="feature-title">Shareable PDF Reports</div>
        <div class="feature-desc">Export your full recommendation report to share with a broker, HR team, or family member.</div>
      </div>
    </div>
  </section>

  <!-- TESTIMONIALS -->
  <section class="hp-social">
    <div class="section-eyebrow" style="color:rgba(255,255,255,0.4)">What people are saying</div>
    <h2 class="section-title">Real people. Real decisions.</h2>
    <p class="section-sub">Used by individuals, HR teams, and insurance brokers.</p>
    <div class="testimonials">
      <div class="testimonial">
        <div class="testimonial-quote">"I had no idea my current plan was so mismatched for my diabetes management. Clarity showed me I was leaving $3,400 a year on the table."</div>
        <div class="testimonial-author">Sarah M.</div>
        <div class="testimonial-role">Individual · California</div>
      </div>
      <div class="testimonial">
        <div class="testimonial-quote">"We use Clarity during open enrollment for our 200-person team. It cuts down the HR support tickets by half. Employees actually understand their choices now."</div>
        <div class="testimonial-author">Derek T.</div>
        <div class="testimonial-role">HR Director · Mid-size Tech Co.</div>
      </div>
      <div class="testimonial">
        <div class="testimonial-quote">"As a broker, the claims-matching logic is a genuine differentiator. My clients trust the recommendations because they're tied to their actual data."</div>
        <div class="testimonial-author">Lisa R.</div>
        <div class="testimonial-role">Independent Benefits Broker</div>
      </div>
    </div>
  </section>

  <!-- CTA -->
  <section class="hp-cta">
    <h2>Start for free. No credit card needed.</h2>
    <p>See your top plan matches in under 2 minutes. Your data stays yours.</p>
    <button class="btn-lg btn-white">Get My Recommendations →</button>
  </section>

  <!-- FOOTER -->
  <footer class="hp-footer">
    <div class="hp-footer-logo">Clarity</div>
    <div class="hp-footer-links">
      <a href="#">Privacy Policy</a>
      <a href="#">Terms of Service</a>
      <a href="#">HIPAA Notice</a>
      <a href="#">Contact</a>
    </div>
    <div class="hp-footer-copy">© 2026 Clarity Health, Inc.</div>
  </footer>
</div>


<!-- ═══════════════════════ AUTH ═══════════════════════ -->
<div id="auth" class="screen">
  <div class="auth-screen">
    <!-- LEFT PANEL -->
    <div class="auth-left">
      <div class="auth-left-logo">Clarity</div>
      <div class="auth-left-body">
        <h2>The smarter way to pick a <em>health plan</em></h2>
        <p>Join thousands of individuals, HR teams, and brokers who use Clarity to match plans to real health data — not guesswork.</p>
        <div class="auth-left-bullets">
          <div class="auth-bullet"><div class="auth-bullet-dot"></div><div class="auth-bullet-text">Claims-based matching — not averages</div></div>
          <div class="auth-bullet"><div class="auth-bullet-dot"></div><div class="auth-bullet-text">Live data from Healthcare.gov + group plans</div></div>
          <div class="auth-bullet"><div class="auth-bullet-dot"></div><div class="auth-bullet-text">HIPAA-compliant. Your data stays yours.</div></div>
          <div class="auth-bullet"><div class="auth-bullet-dot"></div><div class="auth-bullet-text">Free for individuals. Team plans available.</div></div>
        </div>
      </div>
      <div class="auth-left-footer">© 2026 Clarity Health · Privacy · Terms</div>
    </div>

    <!-- RIGHT PANEL — SIGN UP -->
    <div class="auth-right">
      <div class="auth-form-wrap">
        <div class="auth-tabs">
          <div class="auth-tab active">Create account</div>
          <div class="auth-tab">Log in</div>
        </div>

        <div class="auth-form-title">Get started free</div>
        <div class="auth-form-sub">No credit card required · Free for individuals</div>

        <div style="margin-bottom:1.25rem;">
          <div class="form-label" style="margin-bottom:0.6rem;">I am a… <span class="annotation">Personalizes your experience</span></div>
          <div class="role-picker">
            <div class="role-btn selected">
              <div class="role-btn-icon">👤</div>
              <div class="role-btn-label">Individual</div>
            </div>
            <div class="role-btn">
              <div class="role-btn-icon">🏢</div>
              <div class="role-btn-label">HR / Employer</div>
            </div>
            <div class="role-btn">
              <div class="role-btn-icon">📋</div>
              <div class="role-btn-label">Broker</div>
            </div>
          </div>
        </div>

        <div class="form-row">
          <div class="form-field">
            <label class="form-label">First Name</label>
            <input class="form-input" placeholder="Jane" />
          </div>
          <div class="form-field">
            <label class="form-label">Last Name</label>
            <input class="form-input" placeholder="Smith" />
          </div>
        </div>
        <div class="form-field">
          <label class="form-label">Work Email</label>
          <input class="form-input" type="email" placeholder="jane@company.com" />
        </div>
        <div class="form-field">
          <label class="form-label">Password</label>
          <input class="form-input" type="password" placeholder="8+ characters" />
        </div>

        <button class="btn-full btn-accent" style="margin-top:0.75rem;">Create my account →</button>

        <div class="auth-divider">or continue with</div>
        <button class="btn-social">🔵 Continue with Google</button>

        <div class="auth-footer-note">
          Already have an account? <a href="#">Log in</a>
        </div>
        <div class="auth-footer-note" style="margin-top:0.5rem; font-size:0.72rem;">
          By signing up you agree to our <a href="#">Terms</a> and <a href="#">Privacy Policy</a>
        </div>
      </div>
    </div>
  </div>
</div>


<!-- ═══════════════════════ ONBOARDING ═══════════════════════ -->
<div id="onboard" class="screen">
  <div class="onboard-screen">
    <div class="onboard-top">
      <div class="onboard-logo">Clarity</div>
      <div class="onboard-progress">
        <div class="prog-step done"><div class="prog-dot">✓</div><span>Account</span></div>
        <div class="prog-line done"></div>
        <div class="prog-step active"><div class="prog-dot">2</div><span>Data Source</span></div>
        <div class="prog-line"></div>
        <div class="prog-step"><div class="prog-dot">3</div><span>Your Profile</span></div>
        <div class="prog-line"></div>
        <div class="prog-step"><div class="prog-dot">4</div><span>Results</span></div>
      </div>
      <div class="onboard-skip">Skip for now</div>
    </div>

    <div class="onboard-body">
      <div class="onboard-step-label">Step 2 of 4</div>
      <div class="onboard-title">Where are your plan options coming from?</div>
      <div class="onboard-sub">Pick a source and we'll pull in the available plans for you to compare.</div>

      <div class="source-cards">
        <div class="source-card selected">
          <div class="source-card-icon">🏢</div>
          <div class="source-card-title">Upload Group Benefits</div>
          <div class="source-card-desc">Your employer offers a benefits package. Upload the summary document and we'll parse every plan detail.</div>
        </div>
        <div class="source-card">
          <div class="source-card-icon">🏛️</div>
          <div class="source-card-title">Government Marketplace</div>
          <div class="source-card-desc">Shop ACA marketplace plans for your zip code. We pull live data from Healthcare.gov — free and real-time.</div>
        </div>
      </div>

      <div class="upload-box">
        <div class="upload-box-icon">📎</div>
        <div class="upload-box-title">Drop your benefits summary here</div>
        <div class="upload-box-sub">PDF, CSV, or Excel · Max 20MB · or <span style="color:var(--accent);font-weight:600;cursor:pointer">browse files</span></div>
      </div>

      <div class="onboard-form">
        <div class="onboard-form-title">Or enter plan details manually <span class="annotation">Optional</span></div>
        <div class="form-grid-2">
          <div class="form-field">
            <label class="form-label">Employer Name</label>
            <input class="form-input" placeholder="Acme Corp" />
          </div>
          <div class="form-field">
            <label class="form-label">Benefits Effective Date</label>
            <input class="form-input" type="date" />
          </div>
          <div class="form-field">
            <label class="form-label">Number of Plans Offered</label>
            <input class="form-input" placeholder="e.g. 3" />
          </div>
          <div class="form-field">
            <label class="form-label">Plan Year</label>
            <input class="form-input" placeholder="2025 / 2026" />
          </div>
        </div>
      </div>

      <div class="onboard-form">
        <div class="onboard-form-title">Tell us about your health profile</div>
        <div class="form-grid-2">
          <div class="form-field">
            <label class="form-label">Your Age</label>
            <input class="form-input" placeholder="e.g. 38" />
          </div>
          <div class="form-field">
            <label class="form-label">Family Size</label>
            <select class="form-input">
              <option>Just me</option>
              <option>Me + Partner</option>
              <option>Family of 3</option>
              <option>Family of 4+</option>
            </select>
          </div>
          <div class="form-field">
            <label class="form-label">Est. Annual Claims ($)</label>
            <input class="form-input" placeholder="e.g. 14,000" />
          </div>
          <div class="form-field">
            <label class="form-label">Monthly Premium Budget</label>
            <input class="form-input" placeholder="e.g. $400" />
          </div>
        </div>
        <div style="margin-top:1.25rem;">
          <label class="form-label">Conditions / Coverage Priorities</label>
          <div class="chip-group">
            <div class="chip selected">Diabetes</div>
            <div class="chip">Heart Disease</div>
            <div class="chip selected">Mental Health</div>
            <div class="chip">Maternity</div>
            <div class="chip">Cancer</div>
            <div class="chip">Ortho / Spine</div>
            <div class="chip">Asthma / COPD</div>
            <div class="chip">Substance Use</div>
            <div class="chip">Rare Disease</div>
          </div>
        </div>
      </div>

      <div class="onboard-actions">
        <button class="btn-sm btn-back btn-ghost-sm">← Back</button>
        <button class="btn-sm btn-accent">Analyze My Plans →</button>
      </div>
    </div>
  </div>
</div>


<!-- ═══════════════════════ DASHBOARD ═══════════════════════ -->
<div id="dashboard" class="screen">
  <div class="dash-layout">

    <!-- SIDEBAR -->
    <aside class="dash-sidebar">
      <div class="dash-logo">Clarity</div>

      <div class="dash-section-label">Main</div>
      <div class="dash-nav-item active"><div class="dash-nav-icon">🏠</div> Dashboard</div>
      <div class="dash-nav-item"><div class="dash-nav-icon">📋</div> My Plans</div>
      <div class="dash-nav-item"><div class="dash-nav-icon">⚖️</div> Compare Plans</div>

      <div class="dash-section-label">My Data</div>
      <div class="dash-nav-item"><div class="dash-nav-icon">📄</div> Claims & Profile</div>
      <div class="dash-nav-item"><div class="dash-nav-icon">📎</div> Uploaded Files</div>

      <div class="dash-section-label">Account</div>
      <div class="dash-nav-item"><div class="dash-nav-icon">⚙️</div> Settings</div>
      <div class="dash-nav-item"><div class="dash-nav-icon">💳</div> Billing</div>
      <div class="dash-nav-item"><div class="dash-nav-icon">❓</div> Help</div>

      <div class="dash-sidebar-footer">
        <div class="dash-user">
          <div class="dash-avatar">JM</div>
          <div>
            <div class="dash-user-name">Jane M.</div>
            <div class="dash-user-role">Individual Plan</div>
          </div>
        </div>
      </div>
    </aside>

    <!-- MAIN CONTENT -->
    <main class="dash-main">
      <div class="dash-header">
        <div>
          <div class="dash-greeting">Good morning, Jane 👋</div>
          <div class="dash-date">Open Enrollment closes in 14 days · Mon, Apr 20 2026</div>
        </div>
        <div class="dash-header-actions">
          <button class="btn-sm btn-ghost-sm">📤 Export Report</button>
          <button class="btn-sm btn-accent">+ Update Profile</button>
        </div>
      </div>

      <!-- STAT ROW -->
      <div class="dash-stat-row">
        <div class="dash-stat">
          <div class="dash-stat-label">Top Match Score</div>
          <div class="dash-stat-val green">94%</div>
          <div class="dash-stat-change up">↑ Blue Shield PPO Gold</div>
        </div>
        <div class="dash-stat">
          <div class="dash-stat-label">Est. Monthly Savings</div>
          <div class="dash-stat-val orange">$127</div>
          <div class="dash-stat-change">vs. your current plan</div>
        </div>
        <div class="dash-stat">
          <div class="dash-stat-label">Plans Analyzed</div>
          <div class="dash-stat-val">5</div>
          <div class="dash-stat-change">2 marketplace · 3 group</div>
        </div>
      </div>

      <!-- TWO COL -->
      <div class="dash-two-col">

        <!-- PLAN RECS -->
        <div class="dash-card">
          <div class="dash-card-header">
            <div class="dash-card-title">Your Ranked Plans</div>
            <div class="dash-card-action">View all →</div>
          </div>
          <div class="plan-row">
            <div class="plan-row-icon">🏥</div>
            <div class="plan-row-info">
              <div class="plan-row-name">Blue Shield PPO Gold <span class="annotation">Best Match</span></div>
              <div class="plan-row-type">PPO · $420/mo · Deductible $1,500</div>
              <div class="plan-row-bar"><div class="plan-row-fill" style="width:94%"></div></div>
            </div>
            <div class="plan-row-score-wrap">
              <div class="plan-row-score high">94%</div>
              <div class="plan-row-label">match</div>
            </div>
          </div>
          <div class="plan-row">
            <div class="plan-row-icon">🌿</div>
            <div class="plan-row-info">
              <div class="plan-row-name">Kaiser HMO Permanente</div>
              <div class="plan-row-type">HMO · $340/mo · Deductible $1,800</div>
              <div class="plan-row-bar"><div class="plan-row-fill" style="width:78%; background:var(--accent)"></div></div>
            </div>
            <div class="plan-row-score-wrap">
              <div class="plan-row-score mid">78%</div>
              <div class="plan-row-label">match</div>
            </div>
          </div>
          <div class="plan-row">
            <div class="plan-row-icon">💎</div>
            <div class="plan-row-info">
              <div class="plan-row-name">Aetna HMO Silver</div>
              <div class="plan-row-type">HMO · $290/mo · Deductible $2,500</div>
              <div class="plan-row-bar"><div class="plan-row-fill" style="width:62%; background:var(--accent)"></div></div>
            </div>
            <div class="plan-row-score-wrap">
              <div class="plan-row-score mid">62%</div>
              <div class="plan-row-label">match</div>
            </div>
          </div>
          <div class="plan-row">
            <div class="plan-row-icon">⚕️</div>
            <div class="plan-row-info">
              <div class="plan-row-name">Cigna HDHP + HSA</div>
              <div class="plan-row-type">HDHP · $195/mo · Deductible $4,000</div>
              <div class="plan-row-bar"><div class="plan-row-fill" style="width:41%; background:var(--muted)"></div></div>
            </div>
            <div class="plan-row-score-wrap">
              <div class="plan-row-score low">41%</div>
              <div class="plan-row-label">match</div>
            </div>
          </div>
        </div>

        <!-- RIGHT COL -->
        <div style="display:flex; flex-direction:column; gap:1.25rem;">
          <!-- ALERTS -->
          <div class="dash-card">
            <div class="dash-card-header">
              <div class="dash-card-title">Alerts</div>
              <div class="dash-card-action">Dismiss all</div>
            </div>
            <div class="alert-list">
              <div class="alert-item">
                <div class="alert-dot orange"></div>
                <div class="alert-text"><strong>Open enrollment closes in 14 days.</strong> Your top match could save you $127/mo.</div>
              </div>
              <div class="alert-item">
                <div class="alert-dot green"></div>
                <div class="alert-text"><strong>New marketplace plans available</strong> for 2026 in your zip code. 3 new options added.</div>
              </div>
              <div class="alert-item">
                <div class="alert-dot red"></div>
                <div class="alert-text"><strong>Mental health coverage gap</strong> detected in your current plan. Your top match fixes this.</div>
              </div>
            </div>
          </div>

          <!-- RECENT CLAIMS -->
          <div class="dash-card">
            <div class="dash-card-header">
              <div class="dash-card-title">Recent Claims</div>
              <div class="dash-card-action">View all →</div>
            </div>
            <div class="claims-mini">
              <div class="claim-row">
                <div>
                  <div class="claim-name">Specialist Visit — Endocrinology</div>
                  <div class="claim-date">Apr 12, 2026</div>
                </div>
                <div class="claim-amount">$840</div>
              </div>
              <div class="claim-row">
                <div>
                  <div class="claim-name">Lab Work — Metabolic Panel</div>
                  <div class="claim-date">Apr 3, 2026</div>
                </div>
                <div class="claim-amount">$310</div>
              </div>
              <div class="claim-row">
                <div>
                  <div class="claim-name">Rx — Metformin (90-day)</div>
                  <div class="claim-date">Mar 28, 2026</div>
                </div>
                <div class="claim-amount">$95</div>
              </div>
              <div class="claim-row">
                <div>
                  <div class="claim-name">Mental Health — Therapy Session</div>
                  <div class="claim-date">Mar 22, 2026</div>
                </div>
                <div class="claim-amount">$175</div>
              </div>
            </div>
          </div>
        </div>
      </div>

    </main>
  </div>
</div>

<script>
  function show(id) {
    document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
    document.querySelectorAll('.page-btn').forEach(b => b.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    event.target.classList.add('active');
    window.scrollTo(0, 0);
  }
</script>
</body>
</html>
