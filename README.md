# forster-website
<!DOCTYPE html><html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>FORSTER – Precision Laboratory Solutions</title>
  <meta name="description" content="FORSTER – Premium laboratory equipment. Muffle Furnace, Hot Air Oven, Magnetic Stirrer and more.">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#ffffff;
      --text:#0a1f44;           /* Deep Blue */
      --muted:#5a6b8a;
      --accent:#e11d48;         /* Red Accent */
      --card:#f6f8fc;
      --shadow:0 10px 30px rgba(10,31,68,.12);
      --radius:18px;
      --radius-lg:26px;
      --maxw:1200px;
    }
    *{box-sizing:border-box}
    html,body{margin:0;padding:0;font-family:Montserrat,system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,Helvetica,Arial,sans-serif;background:var(--bg);color:var(--text)}
    a{color:inherit;text-decoration:none}
    img{display:block;max-width:100%;height:auto}
    .container{width:100%;max-width:var(--maxw);padding:0 20px;margin:0 auto}/* ===== Preloader (FORSTER logo) ===== */
#preloader{position:fixed;inset:0;background:#0a1f44;display:grid;place-items:center;z-index:9999;transition:opacity .6s ease, visibility .6s ease}
#preloader.hide{opacity:0;visibility:hidden}
.loader-wrap{display:flex;align-items:center;gap:18px;color:#fff}
.logo-box{width:64px;height:64px;border-radius:16px;position:relative;overflow:hidden;background:conic-gradient(from 90deg at 50% 50%, #173a74, #0a1f44, #173a74)}
.logo-box::after{content:"";position:absolute;inset:-40%;background:radial-gradient(circle at 30% 30%, rgba(255,255,255,.28), transparent 45%)}
.logo-ring{position:absolute;inset:8px;border:3px solid rgba(255,255,255,.55);border-top-color:transparent;border-radius:14px;animation:spin 1.4s linear infinite}
.loader-text{font-weight:800;letter-spacing:.12em;font-size:22px}
.brand-dot{color:var(--accent)}
@keyframes spin{to{transform:rotate(360deg)}}

/* ===== Header / Nav ===== */
header{position:sticky;top:0;z-index:50;background:rgba(255,255,255,.88);backdrop-filter:saturate(150%) blur(8px);border-bottom:1px solid #e9eef7}
.nav{display:flex;align-items:center;justify-content:space-between;gap:20px;height:72px}
.brand{display:flex;align-items:center;gap:12px;font-weight:800;font-size:22px}
.brand-mark{width:28px;height:28px;border-radius:8px;background:linear-gradient(135deg,#0f2c63,#163a72);position:relative}
.brand-mark::after{content:"";position:absolute;inset:3px;border-radius:6px;border:2px solid #e11d48}
nav ul{list-style:none;display:flex;gap:22px;margin:0;padding:0}
nav a{font-weight:600;color:var(--text);opacity:.85}
nav a:hover{opacity:1}

/* ===== Hero ===== */
.hero{position:relative;min-height:78vh;display:grid;place-items:center;overflow:hidden}
.hero::before{content:"";position:absolute;inset:-20%;background:radial-gradient(1200px 600px at 20% 20%, rgba(14,40,92,.18), transparent 50%), radial-gradient(1200px 600px at 80% 80%, rgba(225,29,72,.10), transparent 45%);animation:floatGrad 14s ease-in-out infinite alternate}
.hero::after{content:"";position:absolute;inset:-10%;background:url('https://images.unsplash.com/photo-1581091014534-8987c1d4eb0d?q=80&w=1600&auto=format&fit=crop') center/cover no-repeat;opacity:.12;transform:scale(1);animation:slowZoom 18s ease-in-out infinite alternate}
@keyframes slowZoom{from{transform:scale(1)}to{transform:scale(1.06)}}
@keyframes floatGrad{from{transform:translateY(-8px)}to{transform:translateY(8px)}}

.hero-inner{position:relative;z-index:1;text-align:center;padding:80px 16px}
.kicker{display:inline-block;background:var(--card);padding:8px 14px;border-radius:999px;font-weight:700;letter-spacing:.08em;color:var(--muted);box-shadow:var(--shadow)}
.title{font-size:clamp(32px,6vw,56px);line-height:1.06;margin:16px 0 12px;font-weight:800}
.subtitle{font-size:clamp(14px,2.6vw,18px);color:var(--muted);max-width:800px;margin:0 auto 26px}
.cta{display:inline-flex;gap:12px;align-items:center;background:var(--text);color:#fff;padding:14px 20px;border-radius:12px;font-weight:700;box-shadow:var(--shadow);transition:transform .2s ease, box-shadow .2s ease}
.cta:hover{transform:translateY(-2px);box-shadow:0 16px 40px rgba(10,31,68,.2)}

/* ===== Sections & Reveal Animations ===== */
section{padding:72px 0}
.reveal{opacity:0;transform:translateY(22px);transition:opacity .8s ease, transform .8s ease}
.reveal.show{opacity:1;transform:none}

/* ===== Intro ===== */
.intro{display:grid;grid-template-columns:1.1fr .9fr;gap:36px;align-items:center}
.intro .logo-tile{background:var(--card);border-radius:var(--radius-lg);padding:28px;display:grid;place-items:center;box-shadow:var(--shadow)}
.forster-logo{font-size:40px;font-weight:800;letter-spacing:.14em}
.forster-logo span{color:var(--accent)}
.intro p{color:var(--muted);margin:0}
@media(max-width:900px){.intro{grid-template-columns:1fr}.forster-logo{font-size:32px}}

/* ===== Products ===== */
.products-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:22px}
@media(max-width:980px){.products-grid{grid-template-columns:repeat(2,1fr)}}
@media(max-width:640px){.products-grid{grid-template-columns:1fr}}
.card{background:var(--card);border-radius:var(--radius);padding:18px;box-shadow:var(--shadow);display:flex;flex-direction:column;gap:14px;transition:transform .2s ease, box-shadow .2s ease;border:1px solid #e9eef7}
.card:hover{transform:translateY(-6px);box-shadow:0 18px 46px rgba(10,31,68,.16)}
.thumb{height:220px;border-radius:14px;background:linear-gradient(135deg, #e9eef7, #f7f9ff);display:grid;place-items:center;overflow:hidden}
.thumb svg{width:68%;height:auto}
.card h3{margin:6px 0 0;font-size:20px}
.specs{color:var(--muted);font-size:14px}
.actions{margin-top:auto;display:flex;justify-content:space-between;align-items:center}
.view{font-weight:700}
.pill{display:inline-flex;align-items:center;gap:8px;background:#fff;border:1px solid #e5eaf4;padding:8px 12px;border-radius:999px;font-weight:700}

/* ===== Why Choose ===== */
.why-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:18px}
@media(max-width:980px){.why-grid{grid-template-columns:repeat(2,1fr)}}
@media(max-width:640px){.why-grid{grid-template-columns:1fr}}
.why{background:var(--card);border:1px solid #e9eef7;border-radius:var(--radius);padding:20px;box-shadow:var(--shadow);display:flex;gap:14px}
.why-icon{width:48px;height:48px;border-radius:12px;display:grid;place-items:center;background:#fff;border:1px solid #e5eaf4}
.why h4{margin:0 0 6px}
.why p{margin:0;color:var(--muted)}

/* ===== Footer ===== */
footer{background:#071837;color:#c8d4ef;margin-top:30px}
.foot{display:grid;grid-template-columns:2fr 1fr 1fr;gap:24px;padding:36px 0}
@media(max-width:900px){.foot{grid-template-columns:1fr 1fr}}
@media(max-width:640px){.foot{grid-template-columns:1fr}}
.foot h5{margin:0 0 12px;color:#fff}
.foot a{color:#c8d4ef;opacity:.9}
.copyright{border-top:1px solid rgba(255,255,255,.08);padding:16px 0;text-align:center;font-size:14px;color:#9fb1d8}

  </style>
</head>
<body>
  <!-- Preloader -->
  <div id="preloader" aria-hidden="true">
    <div class="loader-wrap" role="status" aria-live="polite">
      <div class="logo-box"><div class="logo-ring"></div></div>
      <div class="loader-text">FORSTER<span class="brand-dot">•</span></div>
    </div>
  </div>  <!-- Header -->  <header>
    <div class="container nav">
      <div class="brand"><span class="brand-mark"></span> FORSTER</div>
      <nav>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="about.html">About Us</a></li>
          <li><a href="products.html">Products</a></li>
          <li><a href="brochures.html">Brochures</a></li>
          <li><a href="contact.html">Contact</a></li>
        </ul>
      </nav>
    </div>
  </header>  <!-- Hero -->  <section id="home" class="hero">
    <div class="hero-inner reveal">
      <span class="kicker">FORSTER</span>
      <h1 class="title">FORSTER – Precision Laboratory Solutions</h1>
      <p class="subtitle">Premium laboratory equipment engineered for reliability and performance. Explore our Muffle Furnaces, Hot Air Ovens, Magnetic Stirrers and more.</p>
      <a class="cta" href="products.html">Explore Products ▸</a>
    </div>
  </section>  <!-- Brand Intro -->  <section>
    <div class="container intro reveal">
      <div>
        <h2 style="margin:0 0 10px">Built for Accuracy. Designed to Last.</h2>
        <p>FORSTER delivers industrial‑grade lab equipment with meticulous attention to safety, durability and precision. From heating systems to stirring solutions, every product reflects our commitment to quality and service.</p>
      </div>
      <div class="logo-tile" aria-label="FORSTER Logo">
        <div class="forster-logo">FORSTER<span>•</span></div>
      </div>
    </div>
  </section>  <!-- Featured Products -->  <section>
    <div class="container">
      <div class="reveal" style="display:flex;align-items:baseline;justify-content:space-between;gap:16px;margin-bottom:14px">
        <h2 style="margin:0">Featured Products</h2>
        <a class="pill" href="products.html">View All Products ▸</a>
      </div>
      <div class="products-grid">
        <!-- Magnetic Stirrer -->
        <article class="card reveal">
          <div class="thumb" title="Magnetic Stirrer">
            <!-- simple SVG placeholder -->
            <svg viewBox="0 0 200 140" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Magnetic Stirrer">
              <rect x="10" y="90" width="180" height="30" rx="8" fill="#dbe4f5"/>
              <rect x="30" y="35" width="140" height="50" rx="6" fill="#c6d4ef"/>
              <circle cx="60" cy="105" r="6" fill="#a8b6d6"/>
              <circle cx="140" cy="105" r="6" fill="#a8b6d6"/>
            </svg>
          </div>
          <h3>Magnetic Stirrer (2 L)</h3>
          <p class="specs">Variable speed control · Hot plate option · Durable housing</p>
          <div class="actions">
            <a class="view" href="products.html#magnetic-stirrer">View Product</a>
            <span class="pill">Brochure</span>
          </div>
        </article>
        <!-- Hot Air Oven -->
        <article class="card reveal">
          <div class="thumb" title="Hot Air Oven">
            <svg viewBox="0 0 200 140" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Hot Air Oven">
              <rect x="20" y="20" width="160" height="100" rx="10" fill="#dbe4f5"/>
              <rect x="40" y="40" width="120" height="60" rx="6" fill="#c6d4ef"/>
              <circle cx="160" cy="90" r="6" fill="#a8b6d6"/>
            </svg>
          </div>
          <h3>Hot Air Oven</h3>
          <p class="specs">Uniform heating · Digital controls · Safety interlocks</p>
          <div class="actions">
            <a class="view" href="products.html#hot-air-oven">View Product</a>
            <span class="pill">Brochure</span>
          </div>
        </article>
        <!-- Muffle Furnace -->
        <article class="card reveal">
          <div class="thumb" title="Muffle Furnace">
            <svg viewBox="0 0 200 140" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Muffle Furnace">
              <rect x="15" y="25" width="170" height="90" rx="10" fill="#dbe4f5"/>
              <rect x="45" y="45" width="110" height="50" rx="8" fill="#c6d4ef"/>
              <rect x="30" y="95" width="140" height="10" rx="5" fill="#a8b6d6"/>
            </svg>
          </div>
          <h3>FORSTER Muffle Furnace</h3>
          <p class="specs">High‑temp insulation · Precise PID control · Rugged build</p>
          <div class="actions">
            <a class="view" href="products.html#muffle-furnace">View Product</a>
            <span class="pill">Brochure</span>
          </div>
        </article>
      </div>
    </div>
  </section>  <!-- Why Choose FORSTER -->  <section>
    <div class="container">
      <h2 class="reveal" style="margin:0 0 18px">Why Choose FORSTER?</h2>
      <div class="why-grid">
        <div class="why reveal">
          <div class="why-icon">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true"><path d="M12 2l3 7 7 .5-5.3 4.6L18.6 22 12 18.3 5.4 22l1.9-7.9L2 9.5 9 9l3-7z" stroke="#0a1f44" stroke-width="1.6"/></svg>
          </div>
          <div><h4>Premium Quality</h4><p>Industrial‑grade materials, built for rigorous daily use.</p></div>
        </div>
        <div class="why reveal">
          <div class="why-icon">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true"><path d="M3 12h18M12 3v18" stroke="#0a1f44" stroke-width="1.6"/></svg>
          </div>
          <div><h4>Precision Performance</h4><p>Stable controls and accurate results across applications.</p></div>
        </div>
        <div class="why reveal">
          <div class="why-icon">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true"><path d="M4 12a8 8 0 1016 0A8 8 0 004 12zm8-5v5l3 3" stroke="#0a1f44" stroke-width="1.6"/></svg>
          </div>
          <div><h4>Reliable Support</h4><p>Friendly assistance and service when you need it.</p></div>
        </div>
        <div class="why reveal">
          <div class="why-icon">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true"><path d="M5 12l5 5L19 7" stroke="#0a1f44" stroke-width="1.6"/></svg>
          </div>
          <div><h4>Safety First</h4><p>Thoughtful protections built into every product we ship.</p></div>
        </div>
      </div>
    </div>
  </section>  <!-- Footer -->  <footer>
    <div class="container foot">
      <div>
        <h5>FORSTER</h5>
        <p>Precision Laboratory Solutions. Built for accuracy, reliability and long service life.</p>
      </div>
      <div>
        <h5>Quick Links</h5>
        <p><a href="#home">Home</a></p>
        <p><a href="products.html">Products</a></p>
        <p><a href="brochures.html">Brochures</a></p>
      </div>
      <div>
        <h5>Contact</h5>
        <p>Email: bhagwatiscientific22@gmail.com</p>
        <p>Phone: +91-XXXXXXXXXX</p>
        <p><a href="https://wa.me/91XXXXXXXXXX" target="_blank" rel="noopener">WhatsApp Chat</a></p>
      </div>
    </div>
    <div class="copyright">© <span id="year"></span> FORSTER. All rights reserved.</div>
  </footer>  <script>
    // Preloader hide on window load
    window.addEventListener('load', () => {
      const p = document.getElementById('preloader');
      setTimeout(()=>p.classList.add('hide'), 350);
    });

    // IntersectionObserver reveal animations
    const io = new IntersectionObserver((entries)=>{
      entries.forEach(e=>{ if(e.isIntersecting){ e.target.classList.add('show'); io.unobserve(e.target); } });
    }, {threshold: .16});
    document.querySelectorAll('.reveal').forEach(el=>io.observe(el));

    // Current year in footer
    document.getElementById('year').textContent = new Date().getFullYear();
  </script></body>
</html>
<div class="thumb"><img src="assets/PRODUCT.jpg" alt="PRODUCT NAME"></div>
<!DOCTYPE html><html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>FORSTER Website</title>
  <link rel="stylesheet" href="styles.css">
  <style>
    .product-grid {display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:20px;}
    .product-card {background:#fff;border-radius:12px;box-shadow:0 4px 15px rgba(0,0,0,.1);overflow:hidden;transition:transform .3s;}
    .product-card:hover {transform:translateY(-5px);}
    .product-card img {width:100%;height:auto;}
    .product-card h3 {margin:15px;}
    .btn-download {display:inline-block;padding:10px 20px;background:#e11d48;color:#fff;border-radius:8px;text-decoration:none;transition:background .3s;}
    .btn-download:hover {background:#b50f36;}
    form {display:grid;gap:10px;max-width:500px;}
    input,textarea {padding:10px;border-radius:6px;border:1px solid #ccc;font-size:1rem;}
    button {padding:10px;background:#0a1f44;color:#fff;border:none;border-radius:6px;cursor:pointer;}
    button:hover {background:#16386f;}
    iframe {width:100%;height:300px;border:0;}
  </style>
</head>
<body>
<header>
  <nav class="container">
    <a href="index.html" class="logo">FORSTER</a>
    <ul>
      <li><a href="index.html">Home</a></li>
      <li><a href="about.html">About Us</a></li>
      <li><a href="products.html">Products</a></li>
      <li><a href="brochures.html">Brochures</a></li>
      <li><a href="contact.html">Contact</a></li>
    </ul>
  </nav>
</header><!-- Products Page --><section class="hero-sub container">
  <h1>Our Products</h1>
  <div class="product-grid">
    <div class="product-card"><img src="muffle.jpg" alt="Muffle Furnace"><h3>Muffle Furnace</h3></div>
    <div class="product-card"><img src="oven.jpg" alt="Hot Air Oven"><h3>Hot Air Oven</h3></div>
    <div class="product-card"><img src="stirrer.jpg" alt="Magnetic Stirrer"><h3>Magnetic Stirrer</h3></div>
  </div>
</section><!-- Brochures Page --><section class="hero-sub container">
  <h1>Brochures</h1>
  <a href="brochure-muffle.pdf" class="btn-download" download>Download Muffle Furnace Brochure</a><br><br>
  <a href="brochure-oven.pdf" class="btn-download" download>Download Hot Air Oven Brochure</a>
</section><!-- Contact Page --><section class="hero-sub container">
  <h1>Contact Us</h1>
  <form>
    <input type="text" placeholder="Your Name" required>
    <input type="email" placeholder="Your Email" required>
    <textarea rows="4" placeholder="Your Message" required></textarea>
    <button type="submit">Send Message</button>
  </form>
  <br>
  <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3672.2561947174436!2d72.5130891752056!3d23.01175827917454!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x395e84f9ac57f7b7%3A0x8bcaaed9ddecf703!2sBhagwati%20Scientific!5e0!3m2!1sen!2sin!4v1692025269096!5m2!1sen!2sin" allowfullscreen="" loading="lazy"></iframe>
</section><footer>
  <div class="container">
    <p>© 2025 FORSTER. All rights reserved.</p>
  </div>
</footer>
</body>
</html>
<!DOCTYPE html><html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>FORSTER Website</title>
  <link rel="stylesheet" href="styles.css">
  <style>
    .product-grid {display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:20px;}
    .product-card {background:#fff;border-radius:12px;box-shadow:0 4px 15px rgba(0,0,0,.1);overflow:hidden;transition:transform .3s;}
    .product-card:hover {transform:translateY(-5px);}
    .product-card img {width:100%;height:auto;}
    .product-card h3 {margin:15px;}
    .btn-download {display:inline-block;padding:10px 20px;background:#e11d48;color:#fff;border-radius:8px;text-decoration:none;transition:background .3s;}
    .btn-download:hover {background:#b50f36;}
    form {display:grid;gap:10px;max-width:500px;}
    input,textarea {padding:10px;border-radius:6px;border:1px solid #ccc;font-size:1rem;}
    button {padding:10px;background:#0a1f44;color:#fff;border:none;border-radius:6px;cursor:pointer;}
    button:hover {background:#16386f;}
    iframe {width:100%;height:300px;border:0;}
  </style>
</head>
<body>
<header>
  <nav class="container">
    <a href="index.html" class="logo">FORSTER</a>
    <ul>
      <li><a href="index.html">Home</a></li>
      <li><a href="about.html">About Us</a></li>
      <li><a href="products.html">Products</a></li>
      <li><a href="brochures.html">Brochures</a></li>
      <li><a href="contact.html">Contact</a></li>
    </ul>
  </nav>
</header><!-- Products Page --><section class="hero-sub container">
  <h1>Our Products</h1>
  <div class="product-grid">
    <div class="product-card"><img src="muffle.jpg" alt="Muffle Furnace"><h3>Muffle Furnace</h3></div>
    <div class="product-card"><img src="oven.jpg" alt="Hot Air Oven"><h3>Hot Air Oven</h3></div>
    <div class="product-card"><img src="stirrer.jpg" alt="Magnetic Stirrer"><h3>Magnetic Stirrer</h3></div>
  </div>
</section><!-- Brochures Page --><section class="hero-sub container">
  <h1>Brochures</h1>
  <a href="brochure-muffle.pdf" class="btn-download" download>Download Muffle Furnace Brochure</a><br><br>
  <a href="brochure-oven.pdf" class="btn-download" download>Download Hot Air Oven Brochure</a>
</section><!-- Contact Page --><section class="hero-sub container">
  <h1>Contact Us</h1>
  <form>
    <input type="text" placeholder="Your Name" required>
    <input type="email" placeholder="Your Email" required>
    <textarea rows="4" placeholder="Your Message" required></textarea>
    <button type="submit">Send Message</button>
  </form>
  <br>
  <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3672.2561947174436!2d72.5130891752056!3d23.01175827917454!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x395e84f9ac57f7b7%3A0x8bcaaed9ddecf703!2sBhagwati%20Scientific!5e0!3m2!1sen!2sin!4v1692025269096!5m2!1sen!2sin" allowfullscreen="" loading="lazy"></iframe>
</section><footer>
  <div class="container">
    <p>© 2025 FORSTER. All rights reserved.</p>
  </div>
</footer>
</body>
</html>
<!DOCTYPE html><html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>FORSTER Website</title>
  <link rel="stylesheet" href="styles.css">
  <style>
    .product-grid {display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:20px;}
    .product-card {background:#fff;border-radius:12px;box-shadow:0 4px 15px rgba(0,0,0,.1);overflow:hidden;transition:transform .3s;}
    .product-card:hover {transform:translateY(-5px);}
    .product-card img {width:100%;height:auto;}
    .product-card h3 {margin:15px;}
    .btn-download {display:inline-block;padding:10px 20px;background:#e11d48;color:#fff;border-radius:8px;text-decoration:none;transition:background .3s;}
    .btn-download:hover {background:#b50f36;}
    form {display:grid;gap:10px;max-width:500px;}
    input,textarea {padding:10px;border-radius:6px;border:1px solid #ccc;font-size:1rem;}
    button {padding:10px;background:#0a1f44;color:#fff;border:none;border-radius:6px;cursor:pointer;}
    button:hover {background:#16386f;}
    iframe {width:100%;height:300px;border:0;}
  </style>
</head>
<body>
<header>
  <nav class="container">
    <a href="index.html" class="logo">FORSTER</a>
    <ul>
      <li><a href="index.html">Home</a></li>
      <li><a href="about.html">About Us</a></li>
      <li><a href="products.html">Products</a></li>
      <li><a href="brochures.html">Brochures</a></li>
      <li><a href="contact.html">Contact</a></li>
    </ul>
  </nav>
</header><!-- Products Page --><section class="hero-sub container">
  <h1>Our Products</h1>
  <div class="product-grid">
    <div class="product-card"><img src="muffle.jpg" alt="Muffle Furnace"><h3>Muffle Furnace</h3></div>
    <div class="product-card"><img src="oven.jpg" alt="Hot Air Oven"><h3>Hot Air Oven</h3></div>
    <div class="product-card"><img src="stirrer.jpg" alt="Magnetic Stirrer"><h3>Magnetic Stirrer</h3></div>
  </div>
</section><!-- Brochures Page --><section class="hero-sub container">
  <h1>Brochures</h1>
  <a href="brochure-muffle.pdf" class="btn-download" download>Download Muffle Furnace Brochure</a><br><br>
  <a href="brochure-oven.pdf" class="btn-download" download>Download Hot Air Oven Brochure</a>
</section><!-- Contact Page --><section class="hero-sub container">
  <h1>Contact Us</h1>
  <form>
    <input type="text" placeholder="Your Name" required>
    <input type="email" placeholder="Your Email" required>
    <textarea rows="4" placeholder="Your Message" required></textarea>
    <button type="submit">Send Message</button>
  </form>
  <br>
  <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3672.2561947174436!2d72.5130891752056!3d23.01175827917454!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x395e84f9ac57f7b7%3A0x8bcaaed9ddecf703!2sBhagwati%20Scientific!5e0!3m2!1sen!2sin!4v1692025269096!5m2!1sen!2sin" allowfullscreen="" loading="lazy"></iframe>
</section><footer>
  <div class="container">
    <p>© 2025 FORSTER. All rights reserved.</p>
  </div>
</footer>
</body>
</html>
