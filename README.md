<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Ayurveda Care</title>

  <!-- ===================== CSS STYLES ===================== -->
  <style>
    :root {
      --primary: #1d78df;
      --secondary: #2978f0;
      --third: #042d6b;
      --bg:  linear-gradient(to right, rgb(41, 237, 165), rgb(135, 243, 189),rgb(229, 229, 229),rgb(229, 229, 229),rgb(229, 229, 229),rgb(229, 229, 229),rgb(229, 229, 229),rgb(229, 229, 229), rgb(113, 224, 255), rgb(42, 212, 243));
      --text: #241f1f;
      --link: #1a1a1a; 
    }

    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.6;
      overflow-x: hidden;
    }

    h1, h2, h3 {
      color: var(--third);
    }

    .container {
      width: 90%;
      max-width: 1200px;
      margin: auto;
      position: relative;
      z-index: 2; /* make content above leaves */
    }

    a {
      color: var(--link);
      text-decoration: none;
      position: relative;
    }

    a::after {
      content: "";
      position: absolute;
      bottom: -2px;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--primary);
      transition: width 0.4s ease;
    }

    a:hover {
      color: var(--primary);
    }

    a:hover::after {
      width: 100%;
    }

    a.btn,
    a.btn:hover {
      text-decoration: none !important;
      color: #fff;
    }

    header {
      background: rgb(220, 248, 225);
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      position: sticky;
      top: 0;
      z-index: 1001;
    }

    header .container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 0;
    }

    .logo {
      font-size: 1.9rem;
      font-weight: bold;
      color: var(--third);
    }

    nav ul {
      list-style: none;
      display: flex;
      gap: 1.5rem;
      margin: 0;
      padding: 0;
    }

    nav a {
      font-weight: 500;
    }

    .hero {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 4rem 0;
      flex-wrap: wrap;
      position: relative;
      z-index: 2;
    }

    .hero img {
      width: 50%;
      border-radius: 10px;
      min-width: 300px;
    }

    .hero-text {
      max-width: 45%;
      min-width: 280px;
    }

    .hero h1 {
      font-size: 2.5rem;
      margin-bottom: 1rem;
    }

    .btn {
      display: inline-block;
      background: var(--primary);
      color: rgb(237, 227, 227);
      padding: 0.7rem 1.5rem;
      border-radius: 5px;
      margin-top: 1rem;
      transition: background 0.4s ease;
    }

    .btn:hover {
      background: var(--secondary);
    }

    section {
      padding: 4rem 0;
    }

    .grid {
      display: grid;
      gap: 2rem;
    }

    .grid-3 {
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    }

    .card {
      background: rgb(246, 246, 246);
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(9, 9, 9, 0.1);
      transition: transform 0.4s ease;
      overflow: hidden;
    }

    .card:hover {
      transform: translateY(-5px);
    }

    .card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
    }

    .card-content {
      padding: 1.5rem;
    }

    /* Contact Section */
    .contact {
      background: rgb(242, 248, 251);
      padding: 3rem;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      text-align: center;
    }

    .contact p {
      margin: 0.5rem 0;
    }

    /* Social Links inline with text */
    .social-inline {
      display: flex;
      justify-content: center;
      gap: 15px;
      margin-top: 1rem;
      font-size: 1.2rem;
    }

    .social-inline a {
      display: flex;
      align-items: center;
      gap: 5px;
      color: var(--primary);
      font-weight: bold;
    }

    footer {
      background: var(--secondary);
      color: white;
      text-align: center;
      padding: 2rem 0;
      margin-top: 2rem;
      position: relative;
      z-index: 2;
    }

    /* ==================== LIVE LEAVES EFFECT ==================== */
    #leaves {
      position: fixed;
      top: 0;
      left: 0;
      width: 1000%;
      height: 1000%;
      pointer-events: none;
      overflow: hidden;
      z-index: -1;
    }

    .leaf {
      position: absolute;
      width: 2000px;
      height: 2000px;
      background: url('ayurveditem.png') no-repeat center/contain;
      opacity: 0.8;
      animation-name: floatLeaf;
      animation-timing-function: linear;
      animation-iteration-count: infinite;
    }


    @keyframes floatLeaf {
      0% {
        transform: translateY(100vh) rotate(0deg) scale(0.1);
        opacity: 2;
      }
      10% {
        opacity: 2;
      }
      80%{
        opacity: 0.5;;
      }
      90%{
        opacity:0.1;
      }
      95%{
        opacity:0.05;
      }
      100% {
        transform: translateY(-100vh) rotate(0deg) scale(0.5);
        opacity: -1;
      }
    }
    
  </style>

  <!-- FontAwesome Icons -->
  <script src="https://kit.fontawesome.com/yourkitid.js" crossorigin="anonymous"></script>
  <!-- GSAP -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.13.0/gsap.min.js"></script>
</head>
<body>
  <!-- LEAVES BACKGROUND -->
  <div id="leaves"></div>

  <!-- HEADER -->
  <header>
    
    <div class="container">
      <div class="logo">Anjali Ayurveda Care 🌿</div>
      <nav>
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#treatments">Treatments</a></li>
          <li><a href="#benefits">Benefits</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </div>
  </header>
  <!-- HERO -->
  <section class="hero container">
    <img src="ayurveditem.png" alt="Ayurveda Wellness" />
    <div class="hero-text">
      <h1>Thuthi Health & Care</h1>
      <p>Discover ancient Ayurveda practices for modern wellness and a healthier gut.</p>
      <h2>Thuthi health & support</h2>
      <a href="#" class="btn">Book Consultation</a> 
    </div>
    <img src="thuthi.jpg" width="900" height="700" alt="Ayurveda Wellness" />
     <img src="thuthi3.jpg" width="900" height="700" alt="Ayurveda Wellness" />
  </section>

  <!-- TREATMENTS -->
  <section id="treatments" class="container">
    <h2>Our Treatments</h2>
    <div class="grid grid-3">
      <a href="panchakarma.html" class="card">
        <img src="https://i.ibb.co/spYbBcvH/panchkarma3.jpg" alt="Panchakarma" />
        <div class="card-content">
          <h3>Panchakarma</h3>
          <p>A 5-step detoxification therapy that removes toxins and restores balance in body & mind.</p>
        </div>
      </a>
      <a href="gut-healing.html" class="card">
        <img src="https://i.ibb.co/RGhYjR3C/gut-health.jpg" alt="Gut Healing" />
        <div class="card-content">
          <h3>Gut Healing</h3>
          <p>Natural herbs & diet adjustments to improve digestion, boost metabolism and immunity.</p>
        </div>
      </a>
      <a href="yoga.html" class="card">
        <img src="https://i.ibb.co/9H2B1SSF/yoga.webpg" alt="Yoga & Meditation" />
        <div class="card-content">
          <h3>Yoga & Meditation</h3>
          <p>Strengthen your mind-body connection with guided yoga, breathing and mindfulness practices.</p>
        </div>
      </a>
    </div>
  </section>

  <!-- BENEFITS -->
  <section id="benefits" class="container">
    <h2>Benefits of Ayurveda</h2>
    <div class="grid grid-3">
      <a href="immunity.html" class="card">
        <img src="https://i.ibb.co/mF4y4XSG/immunity.png" alt="Immunity" />
        <div class="card-content">
          <h3>Boost Immunity</h3>
          <p>Learn how Ayurveda strengthens natural immunity using herbs & diet.</p>
        </div>
      </a>
      <a href="mental-health.html" class="card">
        <img src="https://i.ibb.co/Z1XxCdt5/mental.jpg" alt="Mental Health" />
        <div class="card-content">
          <h3>Mental Wellness</h3>
          <p>Ayurveda balances mind & body, helping reduce stress and anxiety naturally.</p>
        </div>
      </a>
      <a href="detoxification.html" class="card">
        <img src="https://i.ibb.co/wFns7TVZ/detoxii.jpg" alt="Detoxification" />
        <div class="card-content">
          <h3>Detoxification</h3>
          <p>Detoxification is extremely important for maintaining good health. As already explained, toxins are the root cause of disease.</p>
        </div>
      </a>
      <a href="better_diet.html" class="card">
        <img src="https://i.ibb.co/Pzvmh5kv/healthydiet.jpg" alt="Better diet" />
        <div class="card-content">
          <h3>Better diet</h3>
          <p>Focuses on nutrient-rich foods and balanced portions to support overall health and well-being</p>
        </div>
      </a>
      <a href="obesity.html" class="card">
        <img src="https://i.ibb.co/JjTr7Bjw/obesity2.jpg" alt="obesity" />
        <div class="card-content">
          <h3>Obesity management</h3>
          <p>Manages health , reduces fat and risk of disease</p>
        </div>
      </a>
      <a href="skin_health.html" class="card">
        <img src="https://images.unsplash.com/photo-1529626455594-4ff0802cfb7e" alt="Skin health" />
        <div class="card-content">
          <h3>Skin health</h3>
          <p>Using natural ingredients, moisturizing regularly, protecting from sun exposure, and following a balanced diet and lifestyle.</p>
        </div>
      </a>
      <a href="lowerbloodpressure.html" class="card">
        <img src="https://i.ibb.co/RpdvRTRd/bloodpressure.jpg" alt="Lower blood pressure and cholesterol" />
        <div class="card-content">
          <h3>Lower blood pressure and cholesterol</h3>
          <p>Ayurveda balances blood pressure and cholesterol.</p>
        </div>
      </a>
      <a href="ayurveda.html" class="card">
        <img src="https://i.ibb.co/CsTdm9Dw/ayurvedaa.jpg" alt="Ayurveda benifits" />
        <div class="card-content">
          <h3>More benfits - </h3>
          <p>Discover more in Ayurveda longer, healthier, and happier life.</p>
        </div>
      </a>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact" class="container">
    <div class="contact">
      <h2>Contact Us</h2>
      <p><strong>Phone:</strong>+91 70886 66791</p>
      <p><strong>Email:</strong> info@ayurvedacare.com</p>
      <p><strong>Address:</strong> Ayurveda Care Center, Delhi, India</p>

      <div class="social-inline">
        <a href="https://wa.me/70886 66791" target="_blank">
          <i class="fab fa-whatsapp"></i> WhatsApp
        </a>
        <a href="https://instagram.com/bhandari1038" target="_blank">
          <i class="fab fa-instagram"></i> Instagram
        </a>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <p>&copy; 2025 Anjali Ayurveda Care. All rights reserved.</p>
    <p>&copy; Dr Anjali bhandari .</p>
  </footer>

  <!-- ==================== LEAVES SCRIPT ==================== -->
  <script>
    const leavesContainer = document.getElementById('leaves');

    function createLeaf() {
      const leaf = document.createElement('div');
      leaf.classList.add('leaf');
      leaf.style.left = Math.random() * window.innerWidth + 'px';
      leaf.style.animationDuration = (12 + Math.random() * 1) + 's';
      leaf.style.transform = `rotate(${Math.random() * 360}deg) scale(${0.99 + Math.random() * 0.6})`;
      leavesContainer.appendChild(leaf);

      setTimeout(() => {
        leaf.remove();
      }, 12000);
    }

    setInterval(createLeaf, 400);
  </script>
 
</body>
</html>


