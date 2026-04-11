# index.html-
Nada-art
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nada Art — فن الطبيعة والعيون</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=Jost:wght@200;300;400&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #f9f4ee;
    --cream-dark: #ede5d8;
    --cream-mid: #f2ebe0;
    --lavender: #9b89b4;
    --lavender-light: #c4b5d8;
    --lavender-deep: #7a6496;
    --lavender-pale: #e8e0f0;
    --text-dark: #3a2f45;
    --text-mid: #6b5f7a;
    --text-soft: #a096ad;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background-color: var(--cream);
    color: var(--text-dark);
    font-family: 'Jost', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
  }

  /* ── NOISE TEXTURE OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 999;
    opacity: 0.4;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.4rem 3rem;
    background: rgba(249,244,238,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(155,137,180,0.15);
  }

  .nav-logo {
    display: flex;
    align-items: center;
    gap: 0.7rem;
    text-decoration: none;
  }

  .logo-mark {
    width: 38px; height: 38px;
    position: relative;
  }

  .logo-mark svg { width: 100%; height: 100%; }

  .logo-text {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.6rem;
    font-weight: 400;
    color: var(--lavender-deep);
    letter-spacing: 0.04em;
  }

  .logo-text span {
    font-style: italic;
    font-weight: 300;
    color: var(--text-soft);
    font-size: 0.85rem;
    display: block;
    letter-spacing: 0.15em;
    margin-top: -4px;
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }

  .nav-links a {
    font-size: 0.78rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--text-mid);
    text-decoration: none;
    transition: color 0.3s;
  }

  .nav-links a:hover { color: var(--lavender-deep); }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
    padding-top: 80px;
  }

  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 6rem 4rem 6rem 6rem;
    position: relative;
  }

  .hero-tagline {
    font-size: 0.72rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--lavender);
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 0.8rem;
  }

  .hero-tagline::before {
    content: '';
    display: inline-block;
    width: 30px;
    height: 1px;
    background: var(--lavender-light);
  }

  .hero-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(3.5rem, 6vw, 5.5rem);
    font-weight: 300;
    line-height: 1.05;
    color: var(--text-dark);
    margin-bottom: 1.5rem;
  }

  .hero-title em {
    font-style: italic;
    color: var(--lavender-deep);
  }

  .hero-desc {
    font-size: 0.92rem;
    color: var(--text-mid);
    line-height: 1.9;
    max-width: 380px;
    margin-bottom: 3rem;
    font-weight: 200;
  }

  .hero-cta {
    display: flex;
    gap: 1.2rem;
    flex-wrap: wrap;
  }

  .btn-primary {
    background: var(--lavender-deep);
    color: var(--cream);
    padding: 0.9rem 2.2rem;
    font-size: 0.75rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    border: none;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.4s;
    font-family: 'Jost', sans-serif;
  }

  .btn-primary:hover {
    background: var(--lavender);
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(122,100,150,0.25);
  }

  .btn-secondary {
    background: transparent;
    color: var(--lavender-deep);
    padding: 0.9rem 2.2rem;
    font-size: 0.75rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    border: 1px solid var(--lavender-light);
    cursor: pointer;
    text-decoration: none;
    transition: all 0.4s;
    font-family: 'Jost', sans-serif;
  }

  .btn-secondary:hover {
    border-color: var(--lavender-deep);
    background: var(--lavender-pale);
  }

  .hero-right {
    position: relative;
    overflow: hidden;
    background: var(--lavender-pale);
  }

  .hero-right::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(249,244,238,0.3) 0%, transparent 60%);
  }

  /* Big decorative lavender illustration in hero */
  .hero-illustration {
    position: absolute;
    inset: 0;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .hero-illustration svg {
    width: 75%;
    height: 75%;
    opacity: 0.55;
  }

  /* Floating elements */
  .float-el {
    position: absolute;
    border-radius: 50%;
    background: radial-gradient(circle, var(--lavender-light) 0%, transparent 70%);
    animation: float 8s ease-in-out infinite;
  }

  .float-el:nth-child(1) { width: 200px; height: 200px; top: 10%; right: 10%; opacity: 0.4; animation-delay: 0s; }
  .float-el:nth-child(2) { width: 120px; height: 120px; bottom: 20%; left: 15%; opacity: 0.3; animation-delay: 3s; }

  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-20px); }
  }

  /* Scroll indicator */
  .scroll-hint {
    position: absolute;
    bottom: 2rem;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    color: var(--text-soft);
    text-transform: uppercase;
    animation: fadeInUp 1s ease 1s both;
  }

‏  .scroll-line {
‏    width: 1px;
‏    height: 40px;
‏    background: linear-gradient(to bottom, var(--lavender-light), transparent);
‏    animation: scrollPulse 2s ease-in-out infinite;
  }

‏  @keyframes scrollPulse {
‏    0%, 100% { opacity: 0.4; transform: scaleY(1); }
‏    50% { opacity: 1; transform: scaleY(1.2); }
  }

‏  /* ── SECTION SHARED ── */
‏  section { padding: 7rem 6rem; }

‏  .section-label {
‏    font-size: 0.68rem;
‏    letter-spacing: 0.3em;
‏    text-transform: uppercase;
‏    color: var(--lavender);
‏    margin-bottom: 0.8rem;
‏    display: flex;
‏    align-items: center;
‏    gap: 0.7rem;
  }

‏  .section-label::after {
‏    content: '';
‏    flex: 1;
‏    max-width: 40px;
‏    height: 1px;
‏    background: var(--lavender-light);
  }

‏  .section-title {
‏    font-family: 'Cormorant Garamond', serif;
‏    font-size: clamp(2rem, 4vw, 3.2rem);
‏    font-weight: 300;
‏    line-height: 1.2;
‏    color: var(--text-dark);
‏    margin-bottom: 1rem;
  }

‏  .section-title em { font-style: italic; color: var(--lavender-deep); }

‏  /* ── ABOUT / INTRO ── */
‏  .about {
‏    background: var(--cream-mid);
‏    display: grid;
‏    grid-template-columns: 1fr 1.4fr;
‏    gap: 6rem;
‏    align-items: center;
  }

‏  .about-visual {
‏    position: relative;
‏    height: 420px;
  }

‏  .about-frame {
‏    position: absolute;
‏    width: 280px;
‏    height: 360px;
‏    border: 1px solid var(--lavender-light);
‏    top: 20px; left: 20px;
  }

‏  .about-frame-2 {
‏    position: absolute;
‏    width: 280px;
‏    height: 360px;
‏    background: var(--lavender-pale);
‏    top: 0; left: 0;
‏    display: flex;
‏    align-items: center;
‏    justify-content: center;
  }

‏  .about-frame-2 svg { width: 80%; height: 80%; opacity: 0.5; }

‏  .about-badge {
‏    position: absolute;
‏    bottom: 0; right: 0;
‏    background: var(--lavender-deep);
‏    color: var(--cream);
‏    width: 110px;
‏    height: 110px;
‏    border-radius: 50%;
‏    display: flex;
‏    flex-direction: column;
‏    align-items: center;
‏    justify-content: center;
‏    text-align: center;
‏    font-size: 0.65rem;
‏    letter-spacing: 0.1em;
‏    line-height: 1.4;
  }

‏  .about-badge strong {
‏    font-family: 'Cormorant Garamond', serif;
‏    font-size: 1.6rem;
‏    font-weight: 300;
‏    display: block;
  }

‏  .about-text p {
‏    font-size: 0.95rem;
‏    color: var(--text-mid);
‏    line-height: 2;
‏    margin-bottom: 1.2rem;
‏    font-weight: 200;
  }

‏  /* ── GALLERY ── */
‏  .gallery { background: var(--cream); }

‏  .gallery-header {
‏    display: flex;
‏    align-items: flex-end;
‏    justify-content: space-between;
‏    margin-bottom: 3.5rem;
  }

‏  .gallery-grid {
‏    display: grid;
‏    grid-template-columns: 1.3fr 1fr 1fr;
‏    grid-template-rows: 280px 280px;
‏    gap: 1rem;
  }

‏  .gallery-item {
‏    background: var(--lavender-pale);
‏    position: relative;
‏    overflow: hidden;
‏    cursor: pointer;
  }

‏  .gallery-item:first-child {
‏    grid-row: 1 / 3;
  }

‏  .gallery-item-inner {
‏    position: absolute;
‏    inset: 0;
‏    display: flex;
‏    align-items: center;
‏    justify-content: center;
‏    transition: transform 0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  }

‏  .gallery-item:hover .gallery-item-inner { transform: scale(1.04); }

‏  .gallery-item-inner svg { width: 60%; height: 60%; opacity: 0.4; }

‏  .gallery-overlay {
‏    position: absolute;
‏    inset: 0;
‏    background: linear-gradient(to top, rgba(122,100,150,0.6) 0%, transparent 60%);
‏    opacity: 0;
‏    transition: opacity 0.4s;
‏    display: flex;
‏    align-items: flex-end;
‏    padding: 1.5rem;
‏    color: var(--cream);
‏    font-size: 0.8rem;
‏    letter-spacing: 0.1em;
  }

‏  .gallery-item:hover .gallery-overlay { opacity: 1; }

‏  .gallery-label {
‏    position: absolute;
‏    top: 1rem; right: 1rem;
‏    font-size: 0.6rem;
‏    letter-spacing: 0.2em;
‏    text-transform: uppercase;
‏    color: var(--lavender);
‏    background: rgba(249,244,238,0.9);
‏    padding: 0.3rem 0.7rem;
  }

‏  /* different bg for variety */
‏  .gallery-item:nth-child(2) { background: #e8e0f0; }
‏  .gallery-item:nth-child(3) { background: #ede5d8; }
‏  .gallery-item:nth-child(4) { background: #dfd8ec; }
‏  .gallery-item:nth-child(5) { background: #f0ece3; }

‏  /* ── SERVICES ── */
‏  .services {
‏    background: var(--lavender-deep);
‏    color: var(--cream);
‏    padding: 7rem 6rem;
  }

‏  .services .section-label { color: var(--lavender-light); }
‏  .services .section-title { color: var(--cream); }
‏  .services .section-title em { color: var(--lavender-light); }

‏  .services-grid {
‏    display: grid;
‏    grid-template-columns: repeat(3, 1fr);
‏    gap: 2rem;
‏    margin-top: 4rem;
  }

‏  .service-card {
‏    border: 1px solid rgba(196,181,216,0.25);
‏    padding: 2.5rem;
‏    transition: all 0.4s;
‏    position: relative;
‏    overflow: hidden;
  }

‏  .service-card::before {
‏    content: '';
‏    position: absolute;
‏    inset: 0;
‏    background: rgba(249,244,238,0.05);
‏    transform: scaleX(0);
‏    transform-origin: left;
‏    transition: transform 0.4s;
  }

‏  .service-card:hover::before { transform: scaleX(1); }
‏  .service-card:hover { border-color: rgba(196,181,216,0.5); }

‏  .service-icon {
‏    width: 50px;
‏    height: 50px;
‏    margin-bottom: 1.5rem;
‏    opacity: 0.8;
  }

‏  .service-card h3 {
‏    font-family: 'Cormorant Garamond', serif;
‏    font-size: 1.4rem;
‏    font-weight: 300;
‏    margin-bottom: 0.8rem;
‏    color: var(--cream);
  }

‏  .service-card p {
‏    font-size: 0.85rem;
‏    line-height: 1.9;
‏    color: rgba(249,244,238,0.65);
‏    font-weight: 200;
  }

‏  .service-num {
‏    position: absolute;
‏    top: 1.5rem; left: 1.5rem;
‏    font-family: 'Cormorant Garamond', serif;
‏    font-size: 4rem;
‏    font-weight: 300;
‏    color: rgba(196,181,216,0.1);
‏    line-height: 1;
‏    pointer-events: none;
  }

‏  /* ── PROCESS ── */
‏  .process {
‏    background: var(--cream-mid);
‏    display: grid;
‏    grid-template-columns: 1fr 1fr;
‏    gap: 6rem;
‏    align-items: center;
  }

‏  .process-steps { margin-top: 3rem; }

‏  .step {
‏    display: flex;
‏    gap: 1.5rem;
‏    margin-bottom: 2.5rem;
‏    padding-bottom: 2.5rem;
‏    border-bottom: 1px solid var(--cream-dark);
  }

‏  .step:last-child { border-bottom: none; }

‏  .step-num {
‏    font-family: 'Cormorant Garamond', serif;
‏    font-size: 2.5rem;
‏    font-weight: 300;
‏    color: var(--lavender-light);
‏    line-height: 1;
‏    min-width: 50px;
  }

‏  .step-content h4 {
‏    font-family: 'Cormorant Garamond', serif;
‏    font-size: 1.2rem;
‏    font-weight: 400;
‏    color: var(--text-dark);
‏    margin-bottom: 0.4rem;
  }

‏  .step-content p {
‏    font-size: 0.85rem;
‏    color: var(--text-soft);
‏    line-height: 1.8;
‏    font-weight: 200;
  }

‏ .process-visual {
‏    position: relative;
‏    height: 500px;
‏    display: flex;
‏    align-items: center;
‏    justify-content: center;
  }

‏  /* Layered circles */
‏  .circle-layer {
‏    position: absolute;
‏    border-radius: 50%;
‏    border: 1px solid var(--lavender-light);
  }

‏  .circle-layer:nth-child(1) { width: 380px; height: 380px; opacity: 0.3; animation: spin 30s linear infinite; }
‏  .circle-layer:nth-child(2) { width: 280px; height: 280px; opacity: 0.25; animation: spin 20s linear infinite reverse; }
‏  .circle-layer:nth-child(3) { width: 180px; height: 180px; background: var(--lavender-pale); border: none; display: flex; align-items: center; justify-content: center; }

‏  .circle-layer:nth-child(3) svg { width: 80px; height: 80px; opacity: 0.7; }

‏  @keyframes spin {
‏    from { transform: rotate(0deg); }
‏    to { transform: rotate(360deg); }
  }

‏  /* ── TESTIMONIALS ── */
‏  .testimonials { background: var(--cream); text-align: center; }

‏  .testimonials .section-label { justify-content: center; }
‏  .testimonials .section-label::after { display: none; }
‏  .testimonials .section-label::before {
‏    content: '';
‏    flex: 1;
‏    max-width: 40px;
‏    height: 1px;
‏    background: var(--lavender-light);
  }

‏  .testimonial-grid {
‏    display: grid;
‏    grid-template-columns: repeat(3, 1fr);
‏    gap: 2rem;
‏    margin-top: 4rem;
‏    text-align: right;
  }

‏  .testimonial-card {
‏    background: var(--cream-mid);
‏    padding: 2.5rem;
‏    border-top: 2px solid var(--lavender-light);
  }

‏  .quote-mark {
‏    font-family: 'Cormorant Garamond', serif;
‏    font-size: 4rem;
‏    color: var(--lavender-light);
‏    line-height: 0.5;
‏    margin-bottom: 1rem;
‏    display: block;
  }

‏  .testimonial-card p {
‏    font-size: 0.9rem;
‏    color: var(--text-mid);
‏    line-height: 1.9;
‏    margin-bottom: 1.5rem;
‏    font-style: italic;
‏    font-family: 'Cormorant Garamond', serif;
‏    font-size: 1.05rem;
‏    font-weight: 300;
  }

‏  .testimonial-author {
‏    font-size: 0.7rem;
‏    letter-spacing: 0.15em;
‏    text-transform: uppercase;
‏    color: var(--text-soft);
  }

‏  /* ── CONTACT ── */
‏  .contact {
‏    background: var(--cream-mid);
‏    display: grid;
‏    grid-template-columns: 1fr 1fr;
‏    gap: 6rem;
‏    align-items: start;
  }

‏  .contact-info { padding-top: 1rem; }

‏  .contact-info p {
‏    font-size: 0.9rem;
‏    color: var(--text-mid);
‏    line-height: 2;
‏    margin-bottom: 2rem;
‏    font-weight: 200;
  }

‏  .contact-links { display: flex; flex-direction: column; gap: 0.8rem; }

‏  .contact-link {
‏    display: flex;
‏    align-items: center;
‏    gap: 1rem;
‏    font-size: 0.8rem;
‏    color: var(--text-mid);
‏    text-decoration: none;
‏    transition: color 0.3s;
‏    letter-spacing: 0.05em;
  }

‏  .contact-link:hover { color: var(--lavender-deep); }

‏  .contact-link-dot {
‏    width: 6px; height: 6px;
‏    border-radius: 50%;
‏    background: var(--lavender-light);
‏    flex-shrink: 0;
  }

‏  .contact-form { display: flex; flex-direction: column; gap: 1.2rem; }

‏  .form-group { display: flex; flex-direction: column; gap: 0.5rem; }

‏  .form-group label {
‏    font-size: 0.68rem;
‏    letter-spacing: 0.2em;
‏    text-transform: uppercase;
‏    color: var(--text-soft);
  }

‏  .form-group input,
‏  .form-group textarea,
‏  .form-group select {
‏    background: var(--cream);
‏    border: 1px solid var(--cream-dark);
‏    padding: 0.9rem 1.1rem;
‏    font-family: 'Jost', sans-serif;
‏    font-size: 0.88rem;
‏    color: var(--text-dark);
‏    outline: none;
‏    transition: border-color 0.3s;
‏    font-weight: 200;
‏    direction: rtl;
  }

‏  .form-group input:focus,
‏  .form-group textarea:focus,
‏  .form-group select:focus {
‏    border-color: var(--lavender-light);
  }

‏  .form-group textarea { resize: vertical; min-height: 120px; }

‏  /* ── FOOTER ── */
‏  footer {
‏    background: var(--text-dark);
‏    color: var(--cream);
‏    padding: 4rem 6rem;
‏    display: flex;
‏    align-items: center;
‏    justify-content: space-between;
‏    flex-wrap: wrap;
‏    gap: 2rem;
  }

‏  .footer-logo {
‏    font-family: 'Cormorant Garamond', serif;
‏    font-size: 1.8rem;
‏    font-weight: 300;
‏    color: var(--lavender-light);
‏    letter-spacing: 0.05em;
  }

‏  .footer-logo span {
‏    display: block;
‏    font-size: 0.65rem;
‏    letter-spacing: 0.25em;
‏    text-transform: uppercase;
‏    color: var(--text-soft);
‏    margin-top: -2px;
‏    font-family: 'Jost', sans-serif;
  }

‏  .footer-links {
‏    display: flex;
‏    gap: 2rem;
‏    list-style: none;
  }

‏  .footer-links a {
‏    font-size: 0.75rem;
‏    letter-spacing: 0.12em;
‏    color: rgba(249,244,238,0.5);
‏    text-decoration: none;
‏    transition: color 0.3s;
  }

‏  .footer-links a:hover { color: var(--lavender-light); }

‏  .footer-copy {
‏    font-size: 0.7rem;
‏    color: rgba(249,244,238,0.3);
‏    letter-spacing: 0.1em;
  }

‏  /* ── FADE IN ANIMATIONS ── */
‏  @keyframes fadeInUp {
‏    from { opacity: 0; transform: translateY(30px); }
‏    to { opacity: 1; transform: translateY(0); }
  }

‏  .fade-in { animation: fadeInUp 0.9s ease both; }
‏  .delay-1 { animation-delay: 0.2s; }
‏  .delay-2 { animation-delay: 0.4s; }
‏  .delay-3 { animation-delay: 0.6s; }
‏  .delay-4 { animation-delay: 0.8s; }

‏  /* ── DIVIDER ── */
‏  .divider {
‏    text-align: center;
‏    padding: 2rem;
‏    background: var(--cream);
  }

‏  .divider svg { height: 30px; opacity: 0.3; }

‏  /* Lavender decorative strip */
‏  .strip {
‏    height: 3px;
‏    background: linear-gradient(to right, transparent, var(--lavender-light), var(--lavender), var(--lavender-light), transparent);
  }

‏  /* ── RESPONSIVE ── */
‏  @media (max-width: 900px) {
‏    nav { padding: 1rem 1.5rem; }
‏    .nav-links { gap: 1.5rem; }
‏    .hero { grid-template-columns: 1fr; min-height: auto; }
‏    .hero-right { height: 300px; }
‏    .hero-left { padding: 4rem 2rem 3rem; }
‏    section { padding: 4rem 2rem; }
‏    .about, .process, .contact { grid-template-columns: 1fr; gap: 3rem; }
‏    .services { padding: 4rem 2rem; }
‏    .services-grid { grid-template-columns: 1fr; }
‏    .gallery-grid { grid-template-columns: 1fr 1fr; grid-template-rows: auto; }
‏    .gallery-item:first-child { grid-row: auto; }
‏    .testimonial-grid { grid-template-columns: 1fr; }
‏    footer { flex-direction: column; padding: 3rem 2rem; }
‏    .footer-links { flex-wrap: wrap; gap: 1rem; }
  }
‏</style>
‏</head>
‏<body>

‏<!-- NAV -->
‏<nav>
‏  <a href="#" class="nav-logo">
‏    <div class="logo-mark">
‏      <svg viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
‏        <!-- Stylized N with lavender sprig -->
‏        <path d="M10 48V12L30 38V12" stroke="#7a6496" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
‏        <path d="M30 38V12H50V48" stroke="#7a6496" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
‏        <!-- tiny lavender sprig top right -->
‏        <line x1="46" y1="8" x2="46" y2="2" stroke="#c4b5d8" stroke-width="1"/>
‏        <ellipse cx="44" cy="3" rx="1.5" ry="2.5" fill="#c4b5d8" opacity="0.7" transform="rotate(-15 44 3)"/>
‏        <ellipse cx="46" cy="1.5" rx="1.5" ry="2.5" fill="#9b89b4" opacity="0.7"/>
‏        <ellipse cx="48" cy="3" rx="1.5" ry="2.5" fill="#c4b5d8" opacity="0.7" transform="rotate(15 48 3)"/>
‏      </svg>
‏    </div>
‏    <div class="logo-text">
‏      Nada
‏      <span>Art Studio</span>
‏    </div>
‏  </a>
‏  <ul class="nav-links">
‏    <li><a href="#gallery">أعمالي</a></li>
‏    <li><a href="#services">خدماتي</a></li>
‏    <li><a href="#about">عني</a></li>
‏    <li><a href="#contact">تواصلي</a></li>
‏  </ul>
‏</nav>

‏<!-- HERO -->
‏<section class="hero">
‏  <div class="hero-left">
‏    <div class="hero-tagline fade-in">فن — طبيعة — عيون</div>
‏    <h1 class="hero-title fade-in delay-1">
‏      Where <em>Nature</em><br>meets <em>Art</em>
‏    </h1>
‏    <p class="hero-desc fade-in delay-2">
      لوحات بالرصاص تنبض بالحياة — من أناقة الزهور البرية إلى عمق العيون الإنسانية. كل رسمة قصة تُحكى بنعومة وإتقان.
‏    </p>
‏    <div class="hero-cta fade-in delay-3">
‏      <a href="#gallery" class="btn-primary">استعرضي أعمالي</a>
‏      <a href="#contact" class="btn-secondary">طلب رسمة</a>
‏    </div>
‏  </div>
‏  <div class="hero-right">
‏    <div class="float-el"></div>
‏    <div class="float-el"></div>
‏    <div class="hero-illustration">
‏      <!-- Large decorative lavender botanical -->
‏      <svg viewBox="0 0 300 400" fill="none" xmlns="http://www.w3.org/2000/svg">
‏        <!-- Main stem -->
‏        <path d="M150 380 C148 320 145 260 150 180 C152 140 155 100 150 60" stroke="#7a6496" stroke-width="1.5" stroke-linecap="round"/>
‏        <!-- Side stems -->
‏        <path d="M150 280 C130 265 110 250 90 245" stroke="#9b89b4" stroke-width="1" stroke-linecap="round"/>
‏        <path d="M150 260 C170 245 190 230 210 225" stroke="#9b89b4" stroke-width="1" stroke-linecap="round"/>
‏        <path d="M150 220 C135 205 118 195 100 190" stroke="#9b89b4" stroke-width="1" stroke-linecap="round"/>
‏        <path d="M150 200 C165 185 182 175 200 170" stroke="#9b89b4" stroke-width="1" stroke-linecap="round"/>
‏        <!-- Lavender buds left -->
‏        <ellipse cx="90" cy="240" rx="5" ry="8" fill="#9b89b4" opacity="0.6"/>
‏        <ellipse cx="80" cy="235" rx="4" ry="7" fill="#c4b5d8" opacity="0.5" transform="rotate(-10 80 235)"/>
‏        <ellipse cx="98" cy="233" rx="4" ry="7" fill="#7a6496" opacity="0.5" transform="rotate(10 98 233)"/>
‏        <!-- Lavender buds right -->
‏        <ellipse cx="210" cy="220" rx="5" ry="8" fill="#9b89b4" opacity="0.6"/>
‏        <ellipse cx="200" cy="215" rx="4" ry="7" fill="#c4b5d8" opacity="0.5" transform="rotate(-10 200 215)"/>
‏        <ellipse cx="218" cy="213" rx="4" ry="7" fill="#7a6496" opacity="0.5" transform="rotate(10 218 213)"/>
‏        <!-- More buds up the stem -->
‏        <ellipse cx="98" cy="185" rx="4" ry="7" fill="#c4b5d8" opacity="0.5"/>
‏        <ellipse cx="200" cy="165" rx="4" ry="7" fill="#9b89b4" opacity="0.5"/>
‏        <!-- Top flower cluster -->
‏        <ellipse cx="150" cy="58" rx="6" ry="10" fill="#7a6496" opacity="0.7"/>
‏        <ellipse cx="140" cy="52" rx="5" ry="9" fill="#9b89b4" opacity="0.6" transform="rotate(-15 140 52)"/>
‏        <ellipse cx="160" cy="52" rx="5" ry="9" fill="#c4b5d8" opacity="0.6" transform="rotate(15 160 52)"/>
‏        <ellipse cx="148" cy="40" rx="4" ry="7" fill="#7a6496" opacity="0.5"/>
‏        <!-- Leaves -->
‏        <path d="M150 300 C140 310 120 308 115 295 C130 290 145 292 150 300Z" fill="#9b89b4" opacity="0.25"/>
‏        <path d="M150 320 C162 328 178 322 178 308 C165 305 152 310 150 320Z" fill="#9b89b4" opacity="0.25"/>
‏        <path d="M150 160 C138 168 122 162 120 148 C134 146 147 150 150 160Z" fill="#9b89b4" opacity="0.2"/>
‏      </svg>
‏    </div>
‏  </div>
‏  <div class="scroll-hint">
‏    <div class="scroll-line"></div>
‏    <span>scroll</span>
‏  </div>
‏</section>

‏<div class="strip"></div>

‏<!-- ABOUT -->
‏<section class="about" id="about">
‏  <div class="about-visual">
‏    <div class="about-frame-2">
‏      <!-- Pencil sketch flower SVG placeholder -->
‏      <svg viewBox="0 0 200 260" fill="none" xmlns="http://www.w3.org/2000/svg">
‏        <path d="M100 240 C100 200 98 160 100 120 C102 80 105 50 100 20" stroke="#9b89b4" stroke-width="1" stroke-linecap="round"/>
‏        <path d="M100 180 C80 165 60 160 50 145 C70 140 90 148 100 180Z" fill="none" stroke="#c4b5d8" stroke-width="0.8"/>
‏        <path d="M100 160 C120 145 140 140 148 125 C130 122 112 130 100 160Z" fill="none" stroke="#c4b5d8" stroke-width="0.8"/>
‏        <circle cx="100" cy="100" r="35" fill="none" stroke="#9b89b4" stroke-width="0.8" stroke-dasharray="3,3"/>
‏        <path d="M75 90 C80 70 95 60 110 65 C118 75 118 90 110 100 C100 112 80 110 75 90Z" fill="none" stroke="#7a6496" stroke-width="1"/>
‏        <path d="M100 65 C100 50 105 38 100 30 C95 38 98 50 100 65Z" fill="none" stroke="#9b89b4" stroke-width="0.8"/>
‏        <path d="M75 90 C60 85 50 75 48 68 C56 65 68 72 75 90Z" fill="none" stroke="#9b89b4" stroke-width="0.8"/>
‏        <path d="M110 100 C122 105 132 100 136 93 C126 88 116 92 110 100Z" fill="none" stroke="#9b89b4" stroke-width="0.8"/>
‏      </svg>
‏    </div>
‏    <div class="about-frame"></div>
‏    <div class="about-badge">
‏      <strong>ندى</strong>
      فنانة رسم
‏    </div>
‏  </div>
‏  <div class="about-text">
‏    <div class="section-label">عني</div>
‏    <h2 class="section-title">رسمٌ يُلمسُ<br>القلوب <em>قبل العيون</em></h2>
‏    <p>أنا ندى، فنانة شغوفة بعالم الرصاص والتفاصيل الدقيقة. أرسم بحب الطبيعة وجمالها — من بتلات اللافندر الناعمة إلى تفاصيل عيون تحكي قصصًا بلا كلمات.</p>
‏    <p>كل قلم أمسكه يحمل رؤية، وكل ورقة تتحول إلى عالم خاص. أؤمن أن الفن ليس مجرد صورة — بل هو تجربة ولحظة تبقى في الذاكرة إلى الأبد.</p>
‏    <a href="#contact" class="btn-secondary" style="margin-top:1rem; display:inline-block;">اطلبي رسمتك</a>
‏  </div>
‏</section>

‏<!-- GALLERY -->
‏<section class="gallery" id="gallery">
‏  <div class="gallery-header">
‏    <div>
‏      <div class="section-label">معرضي</div>
‏      <h2 class="section-title">لمسة <em>القلم</em></h2>
‏    </div>
‏    <a href="#contact" class="btn-secondary" style="margin-bottom:0.5rem;">طلب رسمة مخصصة</a>
‏  </div>
‏  <div class="gallery-grid">
‏    <div class="gallery-item">
‏      <div class="gallery-item-inner">
‏        <svg viewBox="0 0 200 300" fill="none" xmlns="http://www.w3.org/2000/svg">
‏          <path d="M100 280C100 240 95 200 100 160C105 120 110 80 100 40" stroke="#7a6496" stroke-width="1.5" stroke-linecap="round"/>
‏          <path d="M100 200C80 185 60 185 50 170C70 165 88 172 100 200Z" fill="none" stroke="#9b89b4" stroke-width="1"/>
‏          <path d="M100 180C120 165 140 162 150 147C130 143 112 152 100 180Z" fill="none" stroke="#9b89b4" stroke-width="1"/>
‏          <circle cx="100" cy="110" r="40" fill="none" stroke="#c4b5d8" stroke-width="1"/>
‏          <path d="M70 100C75 75 95 62 115 70C128 82 125 102 115 114C100 130 70 125 70 100Z" fill="none" stroke="#7a6496" stroke-width="1.2"/>
‏        </svg>
‏      </div>
‏      <div class="gallery-label">زهور</div>
‏      <div class="gallery-overlay">Botanical Studies — رسم زهور</div>
‏    </div>
‏    <div class="gallery-item">
‏      <div class="gallery-item-inner">
‏        <svg viewBox="0 0 180 180" fill="none" xmlns="http://www.w3.org/2000/svg">
‏          <!-- Eye sketch -->
‏          <path d="M20 90 C50 55 130 55 160 90 C130 125 50 125 20 90Z" fill="none" stroke="#7a6496" stroke-width="1.5"/>
‏          <circle cx="90" cy="90" r="22" fill="none" stroke="#9b89b4" stroke-width="1.2"/>
‏          <circle cx="90" cy="90" r="14" fill="#c4b5d8" opacity="0.4"/>
‏          <circle cx="83" cy="84" r="4" fill="#7a6496" opacity="0.6"/>
‏          <!-- lashes top -->
‏          <line x1="60" y1="65" x2="55" y2="52" stroke="#7a6496" stroke-width="0.8"/>
‏          <line x1="75" y1="58" x2="72" y2="44" stroke="#7a6496" stroke-width="0.8"/>
‏          <line x1="90" y1="56" x2="90" y2="41" stroke="#7a6496" stroke-width="0.8"/>
‏          <line x1="105" y1="58" x2="108" y2="44" stroke="#7a6496" stroke-width="0.8"/>
‏          <line x1="120" y1="65" x2="125" y2="52" stroke="#7a6496" stroke-width="0.8"/>
‏          <!-- brow -->
‏          <path d="M50 45 C70 35 110 35 135 45" stroke="#9b89b4" stroke-width="2" stroke-linecap="round"/>
‏        </svg>
‏      </div>
‏      <div class="gallery-label">عيون</div>
‏      <div class="gallery-overlay">Eye Portrait — رسم عيون</div>
‏    </div>
‏    <div class="gallery-item">
‏      <div class="gallery-item-inner">
‏        <svg viewBox="0 0 180 180" fill="none" xmlns="http://www.w3.org/2000/svg">
‏          <!-- Lavender sprig -->
‏          <line x1="90" y1="170" x2="90" y2="30" stroke="#9b89b4" stroke-width="1.5" stroke-linecap="round"/>
‏          <ellipse cx="90" cy="85" rx="6" ry="10" fill="#9b89b4" opacity="0.6"/>
‏          <ellipse cx="80" cy="78" rx="5" ry="9" fill="#c4b5d8" opacity="0.5" transform="rotate(-15 80 78)"/>
‏          <ellipse cx="100" cy="78" rx="5" ry="9" fill="#7a6496" opacity="0.5" transform="rotate(15 100 78)"/>
‏          <ellipse cx="82" cy="66" rx="5" ry="9" fill="#c4b5d8" opacity="0.5" transform="rotate(-10 82 66)"/>
‏          <ellipse cx="98" cy="66" rx="5" ry="9" fill="#9b89b4" opacity="0.5" transform="rotate(10 98 66)"/>
‏          <ellipse cx="90" cy="55" rx="5" ry="9" fill="#7a6496" opacity="0.6"/>
‏          <ellipse cx="85" cy="44" rx="4" ry="7" fill="#c4b5d8" opacity="0.5" transform="rotate(-5 85 44)"/>
‏          <ellipse cx="95" cy="44" rx="4" ry="7" fill="#9b89b4" opacity="0.5" transform="rotate(5 95 44)"/>
‏          <ellipse cx="90" cy="34" rx="4" ry="7" fill="#7a6496" opacity="0.6"/>
‏          <!-- leaves -->
‏          <path d="M90 130 C78 140 62 136 60 124 C74 120 87 126 90 130Z" fill="none" stroke="#9b89b4" stroke-width="0.8"/>
‏          <path d="M90 140 C102 150 118 144 118 132 C105 129 92 135 90 140Z" fill="none" stroke="#9b89b4" stroke-width="0.8"/>
‏        </svg>
‏      </div>
‏      <div class="gallery-label">لافندر</div>
‏      <div class="gallery-overlay">Lavender Study — لافندر</div>
‏    </div>
‏    <div class="gallery-item">
‏      <div class="gallery-item-inner">
‏        <svg viewBox="0 0 180 180" fill="none" xmlns="http://www.w3.org/2000/svg">
‏          <!-- Lily sketch -->
‏          <path d="M90 160 L90 100" stroke="#9b89b4" stroke-width="1.5" stroke-linecap="round"/>
‏          <path d="M90 100 C70 85 55 70 60 55 C70 65 80 80 90 100Z" fill="none" stroke="#7a6496" stroke-width="1"/>
‏          <path d="M90 100 C110 85 125 70 120 55 C110 65 100 80 90 100Z" fill="none" stroke="#7a6496" stroke-width="1"/>
‏          <path d="M90 100 C90 75 85 55 90 40 C95 55 90 75 90 100Z" fill="none" stroke="#7a6496" stroke-width="1"/>
‏          <path d="M90 100 C75 90 60 95 52 85 C65 80 78 88 90 100Z" fill="none" stroke="#c4b5d8" stroke-width="1"/>
‏          <path d="M90 100 C105 90 120 95 128 85 C115 80 102 88 90 100Z" fill="none" stroke="#c4b5d8" stroke-width="1"/>
‏          <circle cx="90" cy="102" r="6" fill="#9b89b4" opacity="0.4"/>
‏        </svg>
‏      </div>
‏      <div class="gallery-label">زنبق</div>
‏      <div class="gallery-overlay">Lily Portrait — زنبق</div>
‏    </div>
‏    <div class="gallery-item">
‏      <div class="gallery-item-inner">
‏        <svg viewBox="0 0 180 180" fill="none" xmlns="http://www.w3.org/2000/svg">
‏          <!-- crying eye -->
‏          <path d="M25 80 C55 50 125 50 155 80 C125 110 55 110 25 80Z" fill="none" stroke="#9b89b4" stroke-width="1.5"/>
‏          <circle cx="90" cy="80" r="18" fill="none" stroke="#7a6496" stroke-width="1"/>
‏          <circle cx="90" cy="80" r="11" fill="#c4b5d8" opacity="0.3"/>
‏          <!-- tear -->
‏          <path d="M90 112 C88 120 86 130 90 140 C94 130 92 120 90 112Z" fill="#c4b5d8" opacity="0.5"/>
‏        </svg>
‏      </div>
‏      <div class="gallery-label">عيون دموع</div>
‏      <div class="gallery-overlay">Tearful Eye — دموع</div>
‏    </div>
‏  </div>
‏</section>

‏<!-- SERVICES -->
‏<section class="services" id="services">
‏  <div class="section-label">خدماتي</div>
‏  <h2 class="section-title">ما أقدمه <em>لكِ</em></h2>
‏  <div class="services-grid">
‏    <div class="service-card">
‏      <div class="service-num">01</div>
‏      <div class="service-icon">
‏        <svg viewBox="0 0 50 50" fill="none">
‏          <path d="M25 45 C25 35 23 25 25 15 C27 5 30 2 25 0" stroke="#c4b5d8" stroke-width="1.5" stroke-linecap="round"/>
‏          <path d="M25 30 C18 25 12 25 10 18 C17 16 23 20 25 30Z" fill="none" stroke="#c4b5d8" stroke-width="1"/>
‏          <path d="M25 22 C32 17 38 17 40 10 C33 8 27 12 25 22Z" fill="none" stroke="#c4b5d8" stroke-width="1"/>
‏          <circle cx="25" cy="10" r="6" fill="none" stroke="#c4b5d8" stroke-width="1"/>
‏        </svg>
‏      </div>
‏      <h3>رسم الزهور والطبيعة</h3>
‏      <p>رسومات بالرصاص لأجمل الزهور البرية والنباتات — اللافندر، الزنبق، الورد وغيرها بأسلوب نابض بالحياة.</p>
‏    </div>
‏    <div class="service-card">
‏      <div class="service-num">02</div>
‏      <div class="service-icon">
‏        <svg viewBox="0 0 50 50" fill="none">
‏          <path d="M8 25 C18 15 32 15 42 25 C32 35 18 35 8 25Z" fill="none" stroke="#c4b5d8" stroke-width="1.5"/>
‏          <circle cx="25" cy="25" r="8" fill="none" stroke="#c4b5d8" stroke-width="1"/>
‏          <circle cx="22" cy="22" r="3" fill="#c4b5d8" opacity="0.5"/>
‏        </svg>
‏      </div>
‏      <h3>رسم بورتريه العيون</h3>
‏      <p>عيون تتكلم بصمت — رسومات واقعية تحاكي عمق العين الإنسانية بكل تفاصيلها ولمعانها.</p>
‏    </div>
‏    <div class="service-card">
‏      <div class="service-num">03</div>
‏      <div class="service-icon">
‏        <svg viewBox="0 0 50 50" fill="none">
‏          <rect x="8" y="10" width="34" height="30" rx="2" stroke="#c4b5d8" stroke-width="1.5"/>
‏          <path d="M15 18 L35 18" stroke="#c4b5d8" stroke-width="1" stroke-linecap="round"/>
‏          <path d="M15 24 L28 24" stroke="#c4b5d8" stroke-width="1" stroke-linecap="round"/>
‏          <path d="M15 30 L32 30" stroke="#c4b5d8" stroke-width="1" stroke-linecap="round"/>
‏        </svg>
‏      </div>
‏      <h3>رسومات مخصصة بالطلب</h3>
‏      <p>اطلبي رسمة بأسلوبي المميز — هدية لشخص عزيز، ذكرى جميلة، أو لوحة تزين منزلك.</p>
‏    </div>
‏  </div>
‏</section>

‏<!-- PROCESS -->
‏<section class="process" style="background: var(--cream-mid); padding: 7rem 6rem;">
‏  <div>
‏    <div class="section-label">كيف نعمل</div>
‏    <h2 class="section-title">رحلة <em>رسمتك</em><br>من الفكرة للواقع</h2>
‏    <div class="process-steps">
‏      <div class="step">
‏        <div class="step-num">01</div>
‏        <div class="step-content">
‏          <h4>التواصل والاختيار</h4>
‏          <p>تتواصلين معي وتختارين نوع الرسمة — زهور، عيون، أو تصميم مخصص.</p>
‏        </div>
‏      </div>
‏      <div class="step">
‏        <div class="step-num">02</div>
‏        <div class="step-content">
‏          <h4>الرسم والإبداع</h4>
‏          <p>أبدأ العمل على رسمتك بكل حب وتفانٍ، مع إرسال تحديثات أثناء العمل.</p>
‏        </div>
‏      </div>
‏      <div class="step">
‏        <div class="step-num">03</div>
‏        <div class="step-content">
‏          <h4>التسليم والرضا</h4>
‏          <p>تستلمين رسمتك بجودة عالية — رقميًا أو طباعةً بحسب طلبك.</p>
‏        </div>
‏      </div>
‏    </div>
‏  </div>
‏  <div class="process-visual">
‏    <div class="circle-layer"></div>
‏    <div class="circle-layer"></div>
‏    <div class="circle-layer">
‏      <svg viewBox="0 0 80 80" fill="none">
‏        <path d="M40 70 L40 40" stroke="#9b89b4" stroke-width="1.5" stroke-linecap="round"/>
‏        <path d="M40 40 C30 32 22 30 20 22 C28 20 36 26 40 40Z" fill="none" stroke="#9b89b4" stroke-width="1"/>
‏        <path d="M40 40 C50 32 58 30 60 22 C52 20 44 26 40 40Z" fill="none" stroke="#9b89b4" stroke-width="1"/>
‏        <ellipse cx="40" cy="18" rx="8" ry="12" fill="none" stroke="#7a6496" stroke-width="1"/>
‏      </svg>
‏    </div>
‏  </div>
‏</section>

   
‏<!-- CONTACT -->
‏<section class="contact" id="contact">
‏  <div class="contact-info">
‏    <div class="section-label">تواصلي معي</div>
‏    <h2 class="section-title">لنرسم<br><em>قصتك</em> معًا</h2>
‏    <p>هل لديكِ فكرة رسمة في ذهنك؟ أو تريدين هدية مميزة لشخص تحبينه؟ أنا هنا. تواصلي معي وسنخلق شيئًا جميلًا.</p>
‏    <div class="contact-links">
‏      <a href="#" class="contact-link">
‏        <div class="contact-link-dot"></div>
‏        Instagram: @nada.art
‏      </a>
‏      <a href="#" class="contact-link">
‏        <div class="contact-link-dot"></div>
‏        WhatsApp: للطلبات والاستفسارات 0509885564
‏      </a>
‏      <a href="#" class="contact-link">
‏        <div class="contact-link-dot"></div>
‏        ndya26883@gmail.com
‏      </a>
‏    </div>
‏  </div>
‏  <div>
‏    <div class="contact-form">
‏      <div class="form-group">
‏        <label>الاسم</label>
‏        <input type="text" placeholder="اسمك الكريم...">
‏      </div>
‏      <div class="form-group">
‏        <label>البريد الإلكتروني</label>
‏        <input type="email" placeholder="بريدك الإلكتروني...">
‏      </div>
‏      <div class="form-group">
‏        <label>نوع الرسمة</label>
‏        <select>
‏          <option value="">اختاري نوع الرسمة...</option>
‏          <option>رسم زهور وطبيعة</option>
‏          <option>بورتريه عيون</option>
‏          <option>تصميم مخصص</option>
‏          <option>هدية شخصية</option>
‏        </select>
‏      </div>
‏      <div class="form-group">
‏        <label>رسالتك</label>
‏        <textarea placeholder="اكتبي فكرتك أو طلبك هنا..."></textarea>
‏      </div>
‏      <button class="btn-primary" style="width:100%; padding:1.1rem;">أرسلي طلبك ✦</button>
‏    </div>
‏  </div>
‏</section>

‏<!-- FOOTER -->
‏<footer>
‏  <div class="footer-logo">
‏    Nada Art
‏    <span>Studio — فن الطبيعة والعيون</span>
‏  </div>
‏  <ul class="footer-links">
‏    <li><a href="#gallery">أعمالي</a></li>
‏    <li><a href="#services">خدماتي</a></li>
‏    <li><a href="#about">عني</a></li>
‏    <li><a href="#contact">تواصلي</a></li>
‏  </ul>
‏  <div class="footer-copy">© 2025 Nada Art Studio · جميع الحقوق محفوظة</div>
‏</footer>

‏<script>
‏  // Smooth scroll
‏  document.querySelectorAll('a[href^="#"]').forEach(a => {
‏    a.addEventListener('click', e => {
‏      const id = a.getAttribute('href');
‏      if (id === '#') return;
‏      e.preventDefault();
‏      document.querySelector(id)?.scrollIntoView({ behavior: 'smooth' });
    });
  });

‏  // Fade in on scroll
‏  const observer = new IntersectionObserver(entries => {
‏    entries.forEach(entry => {
‏      if (entry.isIntersecting) {
‏        entry.target.style.opacity = '1';
‏        entry.target.style.transform = 'translateY(0)';
      }
    });
‏  }, { threshold: 0.1 });

‏  document.querySelectorAll('.service-card, .step, .testimonial-card, .gallery-item').forEach(el => {
‏    el.style.opacity = '0';
‏    el.style.transform = 'translateY(25px)';
‏    el.style.transition = 'opacity 0.7s ease, transform 0.7s ease';
‏    observer.observe(el);
  });
‏</script>
‏</body>
‏</html>
