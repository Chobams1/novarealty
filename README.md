<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>NovaNest Realty — Luxury Living in Abuja</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  :root {
    --gold: #C9A84C;
    --gold-light: #E8C97A;
    --dark: #0D0D0D;
    --dark2: #161616;
    --dark3: #1F1F1F;
    --text: #E8E2D9;
    --muted: #7A7570;
    --white: #FAF8F5;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--dark);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
  }

  /* ─── NOISE OVERLAY ─── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1000;
    opacity: 0.4;
  }

  /* ─── NAV ─── */
  nav {
    position: fixed; top: 0; width: 100%; z-index: 100;
    padding: 24px 60px;
    display: flex; justify-content: space-between; align-items: center;
    background: linear-gradient(to bottom, rgba(13,13,13,0.95), transparent);
    backdrop-filter: blur(1px);
  }
  .logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 22px;
    letter-spacing: 0.12em;
    color: var(--gold);
    text-transform: uppercase;
  }
  .logo span { color: var(--text); font-weight: 300; font-style: italic; }
  nav a {
    color: var(--muted); text-decoration: none; font-size: 13px;
    letter-spacing: 0.08em; text-transform: uppercase;
    transition: color 0.3s;
  }
  nav a:hover { color: var(--gold); }

  /* ─── HERO ─── */
  .hero {
    position: relative; min-height: 100vh;
    display: flex; align-items: center;
    padding: 120px 60px 60px;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 70% 50%, rgba(201,168,76,0.07) 0%, transparent 60%),
      radial-gradient(ellipse 50% 80% at 20% 80%, rgba(201,168,76,0.04) 0%, transparent 50%),
      linear-gradient(135deg, #0D0D0D 0%, #161410 50%, #0D0D0D 100%);
  }
  .hero-grid {
    position: absolute; inset: 0;
    background-image: linear-gradient(rgba(201,168,76,0.04) 1px, transparent 1px),
                      linear-gradient(90deg, rgba(201,168,76,0.04) 1px, transparent 1px);
    background-size: 80px 80px;
    mask-image: radial-gradient(ellipse 70% 70% at 70% 40%, black, transparent);
  }

  .hero-content {
    position: relative; z-index: 2;
    max-width: 700px;
  }

  .eyebrow {
    display: inline-flex; align-items: center; gap: 12px;
    font-size: 11px; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--gold); margin-bottom: 28px;
    animation: fadeUp 0.8s ease both;
  }
  .eyebrow::before {
    content: ''; width: 40px; height: 1px; background: var(--gold);
  }

  h1 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(52px, 7vw, 90px);
    font-weight: 300;
    line-height: 0.95;
    letter-spacing: -0.02em;
    color: var(--white);
    margin-bottom: 8px;
    animation: fadeUp 0.8s 0.1s ease both;
  }
  h1 em {
    font-style: italic; color: var(--gold); display: block;
  }

  .hero-sub {
    font-size: 15px; color: var(--muted); line-height: 1.7;
    max-width: 420px; margin: 28px 0 48px;
    animation: fadeUp 0.8s 0.2s ease both;
  }

  .hero-stats {
    display: flex; gap: 48px;
    animation: fadeUp 0.8s 0.3s ease both;
    margin-bottom: 60px;
  }
  .stat-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 38px; font-weight: 300; color: var(--white);
  }
  .stat-num span { color: var(--gold); }
  .stat-label { font-size: 11px; color: var(--muted); letter-spacing: 0.1em; text-transform: uppercase; margin-top: 4px; }

  /* ─── FORM CARD ─── */
  .form-wrapper {
    position: absolute; right: 60px; top: 50%; transform: translateY(-50%);
    width: 420px; z-index: 10;
    animation: fadeLeft 0.9s 0.3s ease both;
  }

  .form-card {
    background: var(--dark2);
    border: 1px solid rgba(201,168,76,0.15);
    border-radius: 2px;
    padding: 44px 40px 40px;
    position: relative;
    box-shadow: 0 40px 80px rgba(0,0,0,0.6), inset 0 1px 0 rgba(201,168,76,0.1);
  }
  .form-card::before {
    content: ''; position: absolute;
    top: 0; left: 40px; right: 40px; height: 1px;
    background: linear-gradient(to right, transparent, var(--gold), transparent);
  }

  .form-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 28px; font-weight: 400;
    color: var(--white); margin-bottom: 6px;
  }
  .form-desc { font-size: 13px; color: var(--muted); margin-bottom: 32px; line-height: 1.6; }

  .field { margin-bottom: 18px; }
  .field label {
    display: block; font-size: 10px; letter-spacing: 0.15em;
    text-transform: uppercase; color: var(--gold);
    margin-bottom: 8px;
  }
  .field input, .field select {
    width: 100%;
    background: var(--dark3);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 2px;
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-size: 14px;
    padding: 13px 16px;
    outline: none;
    transition: border-color 0.3s, box-shadow 0.3s;
    -webkit-appearance: none;
  }
  .field select { cursor: pointer; }
  .field select option { background: var(--dark3); }
  .field input:focus, .field select:focus {
    border-color: rgba(201,168,76,0.5);
    box-shadow: 0 0 0 3px rgba(201,168,76,0.06);
  }
  .field input::placeholder { color: rgba(122,117,112,0.6); }

  .field-row { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }

  .submit-btn {
    width: 100%; margin-top: 8px;
    background: var(--gold);
    border: none; border-radius: 2px;
    color: var(--dark);
    font-family: 'DM Sans', sans-serif;
    font-size: 13px; font-weight: 500;
    letter-spacing: 0.12em; text-transform: uppercase;
    padding: 16px;
    cursor: pointer;
    position: relative; overflow: hidden;
    transition: background 0.3s, transform 0.2s;
  }
  .submit-btn:hover { background: var(--gold-light); transform: translateY(-1px); }
  .submit-btn:active { transform: translateY(0); }
  .submit-btn::after {
    content: ''; position: absolute;
    inset: 0; background: white; opacity: 0;
    transition: opacity 0.3s;
  }
  .submit-btn:hover::after { opacity: 0.05; }

  .submit-btn .btn-text { position: relative; z-index: 1; }
  .submit-btn .btn-arrow {
    position: relative; z-index: 1;
    display: inline-block; margin-left: 10px;
    transition: transform 0.3s;
  }
  .submit-btn:hover .btn-arrow { transform: translateX(4px); }

  .form-note { font-size: 11px; color: var(--muted); text-align: center; margin-top: 16px; }

  /* ─── SUCCESS STATE ─── */
  .success-state {
    display: none; text-align: center; padding: 20px 0;
  }
  .success-icon {
    width: 56px; height: 56px; border-radius: 50%;
    background: rgba(201,168,76,0.1);
    border: 1px solid rgba(201,168,76,0.3);
    display: flex; align-items: center; justify-content: center;
    margin: 0 auto 20px;
    font-size: 22px;
  }
  .success-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 26px; color: var(--white); margin-bottom: 10px;
  }
  .success-msg { font-size: 13px; color: var(--muted); line-height: 1.7; }

  /* ─── LISTINGS STRIP ─── */
  .listings {
    padding: 100px 60px;
    position: relative;
  }
  .section-label {
    font-size: 10px; letter-spacing: 0.25em;
    text-transform: uppercase; color: var(--gold);
    display: flex; align-items: center; gap: 12px;
    margin-bottom: 20px;
  }
  .section-label::after { content: ''; flex: 1; height: 1px; background: rgba(201,168,76,0.15); max-width: 60px; }

  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(36px, 4vw, 56px); font-weight: 300;
    color: var(--white); margin-bottom: 60px;
    max-width: 500px;
  }

  .cards {
    display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px;
  }

  .property-card {
    background: var(--dark2);
    border: 1px solid rgba(255,255,255,0.05);
    border-radius: 2px;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.4s;
    cursor: pointer;
  }
  .property-card:hover { border-color: rgba(201,168,76,0.3); transform: translateY(-4px); }

  .card-img {
    height: 220px;
    position: relative;
    overflow: hidden;
  }
  .card-img-bg {
    position: absolute; inset: 0;
    transition: transform 0.6s ease;
  }
  .property-card:hover .card-img-bg { transform: scale(1.04); }

  /* Simulated property images with gradients */
  .img-1 { background: linear-gradient(135deg, #1a1208 0%, #2d1f0a 40%, #1a1208 100%); }
  .img-2 { background: linear-gradient(135deg, #08121a 0%, #0a1f2d 40%, #08121a 100%); }
  .img-3 { background: linear-gradient(135deg, #0a1208 0%, #0f2d0a 40%, #0a1208 100%); }

  .card-img-overlay {
    position: absolute; inset: 0;
    background: linear-gradient(to top, rgba(0,0,0,0.7) 0%, transparent 60%);
  }
  .card-badge {
    position: absolute; top: 16px; left: 16px;
    background: var(--gold); color: var(--dark);
    font-size: 10px; font-weight: 500; letter-spacing: 0.1em;
    text-transform: uppercase; padding: 5px 10px; border-radius: 1px;
  }
  .card-price {
    position: absolute; bottom: 16px; left: 16px;
    font-family: 'Cormorant Garamond', serif;
    font-size: 22px; color: white; font-weight: 300;
  }

  .card-body { padding: 22px 24px; }
  .card-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 20px; color: var(--white); margin-bottom: 6px;
  }
  .card-loc { font-size: 12px; color: var(--muted); letter-spacing: 0.05em; margin-bottom: 16px; }
  .card-specs {
    display: flex; gap: 20px;
    border-top: 1px solid rgba(255,255,255,0.05);
    padding-top: 16px;
  }
  .spec { font-size: 11px; color: var(--muted); }
  .spec strong { display: block; font-size: 14px; font-weight: 400; color: var(--text); margin-bottom: 2px; }

  /* ─── FOOTER ─── */
  footer {
    padding: 40px 60px;
    border-top: 1px solid rgba(255,255,255,0.05);
    display: flex; justify-content: space-between; align-items: center;
  }
  footer p { font-size: 12px; color: var(--muted); }

  /* ─── ANIMATIONS ─── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeLeft {
    from { opacity: 0; transform: translate(40px, -50%); }
    to   { opacity: 1; transform: translate(0, -50%); }
  }

  /* ─── LOADING SPINNER ─── */
  .spinner {
    display: none; width: 18px; height: 18px;
    border: 2px solid rgba(13,13,13,0.3);
    border-top-color: var(--dark);
    border-radius: 50%;
    animation: spin 0.7s linear infinite;
    margin: 0 auto;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  @media (max-width: 1100px) {
    .form-wrapper { position: static; transform: none; width: 100%; max-width: 460px; margin: 40px auto 0; }
    .hero { flex-direction: column; align-items: flex-start; padding-bottom: 80px; }
    @keyframes fadeLeft {
      from { opacity: 0; transform: translateY(30px); }
      to   { opacity: 1; transform: none; }
    }
    .cards { grid-template-columns: 1fr 1fr; }
  }
  @media (max-width: 700px) {
    nav { padding: 20px 24px; }
    .hero, .listings { padding-left: 24px; padding-right: 24px; }
    .cards { grid-template-columns: 1fr; }
    .hero-stats { gap: 28px; }
    footer { flex-direction: column; gap: 12px; text-align: center; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">Nova<span>Nest</span> Realty</div>
  <a href="#listings">View Properties</a>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>

  <div class="hero-content">
    <div class="eyebrow">Luxury Real Estate · Abuja, Nigeria</div>
    <h1>Where Prestige<em>Meets Home</em></h1>
    <p class="hero-sub">
      Discover Abuja's most exclusive residential addresses. 
      From Maitama penthouses to Asokoro estates — 
      NovaNest curates living experiences beyond the ordinary.
    </p>
    <div class="hero-stats">
      <div>
        <div class="stat-num">320<span>+</span></div>
        <div class="stat-label">Properties Sold</div>
      </div>
      <div>
        <div class="stat-num">₦<span>180B</span></div>
        <div class="stat-label">Portfolio Value</div>
      </div>
      <div>
        <div class="stat-num">12<span>yr</span></div>
        <div class="stat-label">In The Market</div>
      </div>
    </div>
  </div>

  <!-- LEAD FORM -->
  <div class="form-wrapper">
    <div class="form-card">
      <div class="form-content">
        <div class="form-title">Find Your Property</div>
        <p class="form-desc">Our consultants will reach out within 2 hours with curated listings matching your needs.</p>

        <form id="leadForm">
          <div class="field-row">
            <div class="field">
              <label>First Name</label>
              <input type="text" id="firstName" placeholder="Chidi" required />
            </div>
            <div class="field">
              <label>Last Name</label>
              <input type="text" id="lastName" placeholder="Okafor" required />
            </div>
          </div>
          <div class="field">
            <label>Email Address</label>
            <input type="email" id="email" placeholder="you@example.com" required />
          </div>
          <div class="field">
            <label>Phone Number</label>
            <input type="tel" id="phone" placeholder="+234 800 000 0000" required />
          </div>
          <div class="field-row">
            <div class="field">
              <label>I Want To</label>
              <select id="intent">
                <option value="buy">Buy</option>
                <option value="rent">Rent</option>
                <option value="invest">Invest</option>
                <option value="sell">Sell</option>
              </select>
            </div>
            <div class="field">
              <label>Budget Range</label>
              <select id="budget">
                <option value="50m-100m">₦50M – ₦100M</option>
                <option value="100m-250m">₦100M – ₦250M</option>
                <option value="250m-500m">₦250M – ₦500M</option>
                <option value="500m+">₦500M+</option>
              </select>
            </div>
          </div>
          <div class="field">
            <label>Preferred Location</label>
            <select id="location">
              <option value="maitama">Maitama</option>
              <option value="asokoro">Asokoro</option>
              <option value="wuse2">Wuse II</option>
              <option value="guzape">Guzape</option>
              <option value="katampe">Katampe</option>
              <option value="any">Open to All</option>
            </select>
          </div>

          <button type="submit" class="submit-btn" id="submitBtn">
            <div class="spinner" id="spinner"></div>
            <span id="btnLabel"><span class="btn-text">Request Consultation</span><span class="btn-arrow">→</span></span>
          </button>
          <p class="form-note">🔒 Your data is private. No spam, ever.</p>
        </form>
      </div>

      <!-- SUCCESS -->
      <div class="success-state" id="successState">
        <div class="success-icon">✦</div>
        <div class="success-title">You're on our list.</div>
        <p class="success-msg">Thank you! A NovaNest consultant will contact you within 2 hours with properties tailored to your brief.</p>
      </div>
    </div>
  </div>
</section>

<!-- FEATURED LISTINGS -->
<section class="listings" id="listings">
  <div class="section-label">Featured Properties</div>
  <div class="section-title">Handpicked for the Discerning Buyer</div>
  <div class="cards">
    <div class="property-card">
      <div class="card-img">
        <div class="card-img-bg" style="background-image: url('maitama-house.jpg')"></div>
        <div class="card-img-overlay"></div>
        <div class="card-badge">For Sale</div>
        <div class="card-price">₦285,000,000</div>
      </div>
      <div class="card-body">
        <div class="card-name">The Crescent Manor</div>
        <div class="card-loc">📍 Maitama, Abuja</div>
        <div class="card-specs">
          <div class="spec"><strong>5</strong>Bedrooms</div>
          <div class="spec"><strong>6</strong>Bathrooms</div>
          <div class="spec"><strong>680㎡</strong>Floor Area</div>
        </div>
      </div>
    </div>
    <div class="property-card">
      <div class="card-img">
        <div class="card-img-bg" style="background-image: url('maitwusea-house.jpg'); background-size: cover; background-position: center;"></div>
        <div class="card-img-overlay"></div>
        <div class="card-badge">New Listing</div>
        <div class="card-price">₦160,000,000</div>
      </div>
      <div class="card-body">
        <div class="card-name">Skyline Penthouse 12A</div>
        <div class="card-loc">📍 Wuse II, Abuja</div>
        <div class="card-specs">
          <div class="spec"><strong>3</strong>Bedrooms</div>
          <div class="spec"><strong>4</strong>Bathrooms</div>
          <div class="spec"><strong>310㎡</strong>Floor Area</div>
        </div>
      </div>
    </div>
    <div class="property-card">
      <div class="card-img">
        <div class="card-img-bg" style="background-image: url('maya-house.jpg'); background-size: cover; background-position: center;"></div>
        <div class="card-img-overlay"></div>
        <div class="card-badge">For Rent</div>
        <div class="card-price">₦12,000,000/yr</div>
      </div>
      <div class="card-body">
        <div class="card-name">Asokoro Garden Villa</div>
        <div class="card-loc">📍 Asokoro, Abuja</div>
        <div class="card-specs">
          <div class="spec"><strong>4</strong>Bedrooms</div>
          <div class="spec"><strong>5</strong>Bathrooms</div>
          <div class="spec"><strong>490㎡</strong>Floor Area</div>
        </div>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="logo" style="font-size:16px">Nova<span>Nest</span> Realty</div>
  <p>© 2026 NovaNest Realty Ltd. · Abuja, Nigeria · RC 1234567</p>
  <p style="font-size:11px">hello@novanest.ng · +234 912 000 0000</p>
</footer>

<script>
  // ─── CONFIG: Replace with your n8n webhook URL ───
  const N8N_WEBHOOK_URL = "https://6h2o8omc.rcld.app/webhook/novanest-lead";

  document.getElementById("leadForm").addEventListener("submit", async function(e) {
    e.preventDefault();

    const btn = document.getElementById("submitBtn");
    const spinner = document.getElementById("spinner");
    const btnLabel = document.getElementById("btnLabel");

    // Show loading
    spinner.style.display = "block";
    btnLabel.style.display = "none";
    btn.disabled = true;

    const payload = {
      firstName: document.getElementById("firstName").value,
      lastName:  document.getElementById("lastName").value,
      email:     document.getElementById("email").value,
      phone:     document.getElementById("phone").value,
      intent:    document.getElementById("intent").value,
      budget:    document.getElementById("budget").value,
      location:  document.getElementById("location").value,
      source:    "landing-page",
      timestamp: new Date().toISOString()
    };

    try {
      await fetch(N8N_WEBHOOK_URL, {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(payload),
        mode: "no-cors" // allows cross-origin to n8n
      });
    } catch (err) {
      console.warn("Webhook call failed (may still have gone through):", err);
    }

    // Always show success after attempting (no-cors means no response body)
    document.querySelector(".form-content").style.display = "none";
    document.getElementById("successState").style.display = "block";
  });
</script>
</body>
</html>
