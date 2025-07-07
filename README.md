# K-FIT
<!DOCTYPE html>
<html lang="en">
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"/>
  <title>Team K-Fit</title>
  <style>
    * { 
      margin: 0; 
      padding: 0; 
      box-sizing: border-box; 
    }
    
    body, html { 
      font-family: 'Arial', sans-serif; 
      background-color: #0a2033; 
      color: white; 
      line-height: 1.6;
      height: 100%;
      overflow-x: hidden;
      touch-action: pan-y;
    }
    
  .navbar {
  background-color: #0a2033;
  padding: 8px 5px;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  box-shadow: 0 2px 5px rgba(0,0,0,0.3);
  overflow-x: auto; /* Allows horizontal scrolling if needed */
  white-space: nowrap; /* Keeps items in one line */
}


.navbar-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  min-width: 100%; /* Ensures container fills navbar */
}

    .logo {
      font-family: 'Segoe UI', sans-serif;
      font-weight: 1000;
      font-size: 22px;
      background: linear-gradient(90deg, #B37BE8, #8EC5FC, #6EE7B7, #FBD786, #F7797D);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      color: transparent;
      letter-spacing: 1px;
      text-decoration: none;
      transition: transform 0.3s ease;
      margin-right: 10px;
      white-space: nowrap;
    }
    
    .navbar ul {
      display: flex;
      gap: 8px;
      padding: 0 5px;
      margin: 0;
      list-style: none;
      flex-wrap: nowrap; /* Prevents wrapping */
    }
    .navbar a { 
      text-decoration: none; 
      color: white; 
      font-size: 0.8rem; 
      font-weight: bold; 
      transition: all 0.3s ease; 
      padding: 5px 6px;
      position: relative;
      white-space: nowrap;
    }
    
    .navbar a:hover { 
      color: #00ffae; 
    }
    
    .navbar a::after {
      content: '';
      position: absolute;
      width: 0;
      height: 2px;
      background: #00ffae;
      bottom: 0;
      left: 0;
      transition: width 0.3s ease;
    }
    
    .navbar a:hover::after {
      width: 100%;
    }
    
    .navbar a.active-nav {
      color: #00ffae;
    }
    
    .navbar a.active-nav::after {
      width: 100%;
    }
    
    .page {
      display: none;
      padding: 60px 10px 20px;
      min-height: 100vh;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      text-align: center;
      opacity: 0;
      animation: fadeIn 0.5s ease forwards;
      width: 100%;
    }
    
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    .active-page {
      display: flex;
    }
    
    h1 { 
      margin-bottom: 15px; 
      font-size: clamp(1.5rem, 4vw, 2rem);
      padding: 0 10px;
    }
    
    h2 {
      margin: 20px 0 10px;
      color: #00ffae;
      font-size: clamp(1.2rem, 3vw, 1.4rem);
      padding: 0 10px;
    }
    
    h3 {
      margin: 15px 0;
      color: #00ffae;
      font-size: clamp(1rem, 2.5vw, 1.2rem);
      padding: 0 10px;
    }
    
    p { 
      max-width: min(600px, 90%); 
      margin-bottom: 15px; 
      padding: 0 10px;
      font-size: clamp(0.85rem, 2vw, 0.95rem);
    }

    .gradient-title {
      font-family: 'Arial Black', 'Arial Bold', sans-serif;
      font-weight: 900;
      background: linear-gradient(to right, 
        #8a5cf4, 
        #a88df4, 
        #91bff4, 
        #a5f4cf, 
        #f4e891);
      -webkit-background-clip: text;
      background-clip: text;
      -webkit-text-fill-color: transparent;
      display: inline-block;
    }

    .cta-button {
      position: relative;
      display:inline-block;
      padding: 8px 15px;
      margin: 15px auto;
      text-align: center;
      border: 2px solid transparent;
      border-image: linear-gradient(to right, #8a5cf4, #a88df4, #91bff4, #a5f4cf, #f4e891);
      border-image-slice: 1;
      border-radius: 5px;
      background: rgba(10, 32, 51, 0.7);
      cursor: pointer;
      transition: all 0.3s ease;
      text-decoration: none;
    }
    
    .cta-button:hover {
      background: rgba(10, 32, 51, 0.9);
      transform: scale(1.05);
      box-shadow: 0 0 15px rgba(138, 92, 244, 0.5);
    }
    
    .cta-button .gradient-title {
      margin: 0;
    }

    /* Message page styles */
    .message-content {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 100%;
      max-width: min(900px, 95%);
    }
    
    .message-content > p {
      font-family: 'Arial';
      font-size: clamp(0.9rem, 3vw, 1.1rem);
      line-height: 1.4;
    }
    
    .highlight-message {
      font-size: clamp(0.9rem, 3vw, 1.2rem);
      color: #00ffae;
      text-transform: uppercase;
      letter-spacing: 1px;
      text-shadow: 0 2px 4px rgba(0,0,0,0.3);
      padding: 10px 15px;
      border: 2px solid #00ffae;
      border-radius: 8px;
      background-color: #0a2033;
      display: inline-block;
      margin: 15px 0;
    }

    .message-title-img {
      max-width: min(400px, 90%);
      height: auto;
      border: 2px solid #00ffae;
      border-radius: 10px;
      margin-bottom: 15px;
      animation: fadeIn 0.8s ease 0.3s forwards;
      opacity: 0;
    }

    .message-photos {
      display: flex;
      justify-content: center;
      gap: 15px;
      flex-wrap: wrap;
      margin: 15px 0;
      width: 100%;
    }

    .message-photo {
      max-width: min(300px, 90%);
      height: auto;
      border-radius: 10px;
      border: 2px solid #00ffae;
      box-shadow: 0 4px 10px rgba(0, 255, 174, 0.3);
      opacity: 0;
      animation: fadeIn 0.8s ease forwards;
    }

    .message-photo:nth-child(1) {
      animation-delay: 0.4s;
    }

    .message-photo:nth-child(2) {
      animation-delay: 0.6s;
    }

    /* Contact section styles */
    .contact-section {
      margin-top: 25px;
      width: 100%;
      max-width: min(800px, 95%);
    }
    
    .contact-info {
      background-color: #112a44;
      padding: 15px;
      border-radius: 10px;
      max-width: min(450px, 90%);
      margin: 15px auto;
      box-shadow: 0 4px 10px rgba(0, 255, 174, 0.1);
    }
    
    .contact-info p {
      margin: 10px 0;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-wrap: wrap;
      font-size: clamp(0.85rem, 2vw, 0.9rem);
    }
    
    .contact-info a {
      color: #00ffae;
      text-decoration: none;
      margin-left: 5px;
    }
    
    .contact-info a:hover {
      text-decoration: underline;
    }
    
    .social-icons-container {
      display: flex;
      justify-content: center;
      gap: 20px;
      margin-top: 30px;
      flex-wrap: wrap;
    }

    .social-frame {
      border: 2px solid #00ffae;
      border-radius: 8px;
      padding: 15px;
      width: 100px;
      text-align: center;
      transition: all 0.3s ease;
      box-shadow: 0 4px 10px rgba(0, 255, 174, 0.1);
    }

    .social-frame:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 20px rgba(0, 255, 174, 0.3);
      background: rgba(16, 42, 68, 1);
    }

    .social-link {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-decoration: none;
      color: white;
    }

    .social-icon {
      width: 40px;
      height: 40px;
      margin-bottom: 8px;
      transition: transform 0.3s ease;
    }

    .social-frame:hover .social-icon {
      transform: scale(1.1);
    }

    .social-name {
      font-size: 0.8rem;
      font-weight: 500;
      color: #00ffae;
      margin-top: 5px;
    }

    /* Contact form styles */
    .contact-form {
      max-width: min(450px, 90%);
      width: 100%;
      margin: 20px auto;
      background-color: #112a44;
      padding: 15px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 255, 174, 0.1);
    }
    
    .form-group {
      margin-bottom: 12px;
      text-align: left;
    }
    
    .form-group label {
      display: block;
      margin-bottom: 5px;
      color: #00ffae;
      font-size: clamp(0.85rem, 2vw, 0.9rem);
    }
    
    .form-group input,
    .form-group textarea {
      width: 100%;
      padding: 8px;
      background-color: #0d2438;
      border: 1px solid #1a3a5a;
      border-radius: 5px;
      color: white;
      font-size: clamp(0.85rem, 2vw, 0.9rem);
    }
    
    .form-group textarea {
      height: 100px;
      resize: vertical;
    }
    
    .submit-btn {
      background-color: #00ffae;
      color: #0a2033;
      border: none;
      padding: 8px 15px;
      border-radius: 5px;
      font-weight: bold;
      cursor: pointer;
      transition: background-color 0.3s ease;
      font-size: clamp(0.85rem, 2vw, 0.9rem);
      width: 100%;
      margin-top: 5px;
    }
    
    .submit-btn:hover {
      background-color: #00e69c;
    }

    /* Tables container */
    .tables-container {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 20px;
      margin-top: 20px;
      width: 100%;
      max-width: min(900px, 95%);
      flex-wrap: wrap;
    }
    
    .plan-intro {
      font-size: clamp(0.95rem, 3vw, 1.1rem) !important;
      margin-bottom: clamp(10px, 3vw, 20px) !important;
      color: #ffffff !important;
      font-weight: 500;
      max-width: min(600px, 90%) !important;
      text-shadow: 0 1px 3px rgba(0,0,0,0.3);
    }

    /* Training Programs table styles */
    .programs-table {
      border-collapse: collapse;
      width: 100%;
      max-width: 400px;
      background-color: #112a44;
      border-radius: 8px;
      overflow: hidden;
      opacity: 0;
      transform: translateY(20px);
      animation: fadeIn 0.6s ease 0.4s forwards;
    }
    
    .programs-table th, .programs-table td {
      padding: 10px 12px;
      text-align: left;
      border: 1px solid #1a3a5a;
      font-size: clamp(0.8rem, 2vw, 0.85rem);
    }
    
    .programs-table th {
      background-color: #00ffae;
      color: #0a2033;
      font-size: clamp(0.85rem, 2vw, 0.9rem);
      text-align: center;
    }
    
    .programs-table tr:nth-child(even) {
      background-color: #0d2438;
    }
    
    .programs-table tr {
      transition: all 0.3s ease;
      position: relative;
    }
    
    .programs-table tr:hover {
      background-color: #14314d;
      transform: scale(1.02);
      box-shadow: 0 5px 10px rgba(0, 255, 174, 0.2);
      z-index: 1;
    }
    
    .program-title {
      font-weight: bold;
      color: #00ffae;
      width: 100px;
    }
    
    .program-description {
      font-size: clamp(0.75rem, 2vw, 0.8rem);
      position: relative;
      color:color(from color srgb r g b)
    }
    
    #plans p,
    #plans table,
    #plans td,
    #plans th,
    #plans .program-title,
    #plans .program-description,
    #plans .price-amount,
    #plans .price-saving {
       font-family: 'Arial';
       font-size: clamp(0.8rem, 2vw, 0.9rem);
    }
    
    /* Pricing table styles */
    .pricing-table {
      border-collapse: collapse;
      width: 100%;
      max-width: 400px;
      background-color: #112a44;
      border-radius: 8px;
      overflow: hidden;
      opacity: 0;
      transform: translateY(20px);
      animation: fadeIn 0.6s ease 0.6s forwards;
    }
    
    .pricing-table th, .pricing-table td {
      padding: 10px 12px;
      text-align: center;
      border: 1px solid #1a3a5a;
      font-size: clamp(0.8rem, 2vw, 0.85rem);
    }
    
    .pricing-table th {
      background-color: #00ffae;
      color: #0a2033;
      font-size: clamp(0.85rem, 2vw, 0.9rem);
    }
    
    .pricing-table tr:nth-child(even) {
      background-color: #0d2438;
    }
    
    .pricing-table tr {
      transition: all 0.3s ease;
      position: relative;
    }
    
    .pricing-table tr:hover {
      background-color: #14314d;
      transform: scale(1.02);
      box-shadow: 0 5px 10px rgba(0, 255, 174, 0.2);
      z-index: 1;
    }
    
    .price-amount {
      font-weight: bold;
      color: #00ffae;
    }
    
    .price-saving {
      font-size: clamp(0.7rem, 2vw, 0.75rem);
      color: #aaa;
    }
    
    .plan-button {
      background-color: #00ffae;
      color: #0a2033;
      border: none;
      padding: 6px 12px;
      border-radius: 5px;
      font-weight: bold;
      cursor: pointer;
      transition: background-color 0.3s ease;
      text-decoration: none;
      display: inline-block;
      font-size: clamp(0.75rem, 2vw, 0.8rem);
    }
    
    .plan-button:hover {
      background-color: #00e69c;
    }

    /* Home page styles */
    .welcome-img {
      max-width: min(500px, 95%);
      height: auto;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 255, 174, 0.3);
      opacity: 0;
      animation: fadeIn 0.8s ease 0.3s forwards;
    }

    /* Transformations Carousel */
    .carousel-container {
      position: relative;
      width: 90%;
      max-width: min(400px, 90%);
      margin: 20px auto;
      overflow: hidden;
      border-radius: 8px;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
    }

    .carousel {
      display: flex;
      transition: transform 0.3s ease-out;
      width: 100%;
      height: 300px;
    }

    .carousel-slide {
      min-width: 100%;
      height: 100%;
      position: relative;
    }

    .carousel-img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .carousel-info {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      background: rgba(10, 32, 51, 0.9);
      padding: 15px;
      color: white;
      text-align: center;
      transform: translateY(100%);
      transition: transform 0.3s ease;
    }

    .carousel-slide:hover .carousel-info {
      transform: translateY(0);
    }

    .carousel-results {
      font-family: 'Arial';
      font-size: clamp(0.9rem, 3vw, 1.1rem);
      margin-bottom: 5px;
    }

    .carousel-details {
      font-family: 'Arial';
      font-size: clamp(0.8rem, 2.5vw, 0.9rem);
      color: #ccc;
      margin-top: 8px;
    }

    .carousel-btn {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background: rgba(0, 255, 174, 0.7);
      color: #0a2033;
      border: none;
      padding: 10px;
      cursor: pointer;
      font-size: 1rem;
      font-weight: bold;
      z-index: 10;
      transition: all 0.3s ease;
      opacity: 0;
    }

    .carousel-container:hover .carousel-btn {
      opacity: 1;
    }

    #prevBtn {
      left: 5px;
      border-radius: 0 5px 5px 0;
    }

    #nextBtn {
      right: 5px;
      border-radius: 5px 0 0 5px;
    }

    .carousel-indicators {
      display: flex;
      justify-content: center;
      margin-top: 10px;
    }

    .indicator {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: #1a3a5a;
      margin: 0 4px;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    .indicator.active {
      background: #00ffae;
    }
    
    #transformations p {
      font-family: 'Arial';
      font-size: clamp(0.9rem, 2.5vw, 1rem);
    }

    .bold-text {
      font-weight: 900;
      color: #ffffff;
    }

    /* Contact page background */
    #contact {
      background: url('gym-background.jpg') no-repeat center center;
      background-size: cover;
      background-attachment: fixed;
      background-color: #0a2033; /* Fallback color */
      position: relative;
      min-height: 100vh;
      padding: 70px 10px 20px;  
    }
    .contact-cta {
      font-family: 'Arial';
      font-size: clamp(0.9rem, 3vw, 1.1rem);
      letter-spacing: 0.3px;
    }

    /* Responsive adjustments */
   @media (max-width: 768px) {
  .navbar {
    padding: 6px 2px;
  }
  
  .navbar a {
    font-size: 0.7rem;
    padding: 5px 6px;
  }
  
  .logo {
    font-size: 1rem;
    margin-right: 5px;
  }
}

      .page {
        padding: 55px 8px 15px;
      }
      
      .carousel {
        height: 250px;
      }
      
      .carousel-info {
        padding: 10px;
      }
      
      .tables-container {
        flex-direction: column;
        gap: 15px;
      }
      
      .programs-table,
      .pricing-table {
        max-width: 350px;
      }
      
      .social-icons-container {
        gap: 15px;
      }
      
      .social-frame {
        width: 90px;
        padding: 12px;
      }
      
      .social-icon {
        width: 35px;
        height: 35px;
      }
    @media (max-width: 768px) {
  #contact {
    background-attachment: scroll; /* Better for mobile performance */
    background-size: contain; /* Or 'cover' depending on your preference */
    background-position: top center;
  } }

    @media (max-width: 480px) {
      .navbar ul {
        gap: 3px;
      }
      
      .navbar a {
        font-size: 0.7rem;
        padding: 3px 4px;
      }
      
      .logo {
        font-size: 18px;
      }
      
      .carousel {
        height: 220px;
      }
      
      .message-photos {
        flex-direction: column;
      }
      
      .message-photo {
        max-width: 90%;
      }
      
      .social-icons-container {
        gap: 10px;
      }
      
      .social-frame {
        width: 80px;
        padding: 10px;
      }
      
      .social-icon {
        width: 30px;
        height: 30px;
      }
      
      .social-name {
        font-size: 0.7rem;
      }
    }
  </style>
</head>
<body>

 <!-- Navigation Bar -->
<nav class="navbar">
  <div class="navbar-container">
    <!-- Logo on the left -->
    <div class="logo">K-FIT</div>
    
    <!-- Navigation links on the right -->
    <ul>
      <li><a href="#home" class="nav-link active-nav">Home</a></li>
      <li><a href="#message" class="nav-link">Message</a></li>
      <li><a href="#transformations" class="nav-link">Transformations</a></li>
      <li><a href="#plans" class="nav-link">Plans</a></li>
      <li><a href="#contact" class="nav-link">Contact 📞</a></li>
    </ul>
  </div>
</nav>

  <!-- Home Page -->
  <div id="home" class="page active-page">
    <img src="logo.png" alt="K-Fit Welcome" class="welcome-img" />
  </div>

  <!-- Message Page -->
  <div id="message" class="page">
    <div class="message-content">
      <img src="message.png" 
           alt="Message for you" 
           class="message-title-img">
      <p>Hi ~ I'm Karim<br><br>
      Whether your goal is fat loss, building muscle, or simply improving your overall fitness — you're in the right place.<br><br>
      I offer fully customized training and nutrition plans tailored to your lifestyle and goals, with continuous support and expert guidance every step of the way.<br><br>
      Let's work together to unlock your full potential. </p>
      <a href="#plans" class="cta-button">
        <span class="gradient-title">STARTING TODAY</span>
      </a>
      <!-- Add your styled new sentence here -->
        <p class="highlight-message"> EXAMPLES !</p>
      
      <div class="message-photos">
        <img src="photo1.jpg" alt="Training Session" class="message-photo">
        <img src="photo2.jpg" alt="Nutrition Guidance" class="message-photo">
      </div>
    </div>
  </div>
  

  <!-- Transformations Page -->
  <div id="transformations" class="page">
    <h1 class="gradient-title">K-Fit Transformations</h1>
    <p>Be inspired by the incredible results achieved by our team members.</p>
    <P> <span class="bold-text">Real stories. Real people. Real change.</span></p>

    
    <div class="carousel-container">
      <div class="carousel">
        <!-- Slide 1 -->
        <div class="carousel-slide">
          <img src="transformation1.jpg" alt="Transformation 1" class="carousel-img">
          <div class="carousel-info">
            <div class="carousel-results">gained 10kg in 3 months</div>
            <div class="carousel-details">"K-Fit changed my life! I achieved results I never thought possible."</div>
          </div>
        </div>
        <!-- Slide 2 -->
        <div class="carousel-slide">
          <img src="transformation2.jpg" alt="Transformation 2" class="carousel-img">
          <div class="carousel-info">
            <div class="carousel-results">Gained 5kg muscle in 4 months</div>
            <div class="carousel-details">"The muscle-building program helped me transform my physique while maintaining feminine curves."</div>
          </div>
        </div>
        <!-- Slide 3 -->
        <div class="carousel-slide">
          <img src="transformation3.jpg" alt="Transformation 3" class="carousel-img">
          <div class="carousel-info">
            <div class="carousel-results">Reduced body fat by 8%</div>
            <div class="carousel-details">"From skinny fat to lean and defined - the perfect program for body recomposition."</div>
          </div>
        </div>
        <!-- Slide 4 -->
        <div class="carousel-slide">
          <img src="transformation4.jpg" alt="Transformation 4" class="carousel-img">
          <div class="carousel-info">
            <div class="carousel-results">Improved endurance by 40%</div>
            <div class="carousel-details">"I can now run 10km without stopping! The cardio program boosted my stamina dramatically."</div>
          </div>
        </div>
        <!-- Slide 5 -->
        <div class="carousel-slide">
          <img src="transformation5.jpg" alt="Transformation 5" class="carousel-img">
          <div class="carousel-info">
            <div class="carousel-results">Lost 12kg, gained muscle</div>
            <div class="carousel-details">"The perfect balance of fat loss and strength training for amazing results."</div>
          </div>
        </div>
        <!-- Slide 6 -->
        <div class="carousel-slide">
          <img src="transformation6.jpg" alt="Transformation 6" class="carousel-img">
          <div class="carousel-info">
            <div class="carousel-results">Toned entire body in 8 weeks</div>
            <div class="carousel-details">"Finally achieved the toned look I wanted without getting bulky."</div>
          </div>
        </div>
      </div>
      
      <button class="carousel-btn" id="prevBtn">&#10094;</button>
      <button class="carousel-btn" id="nextBtn">&#10095;</button>
    </div>
    
    <div class="carousel-indicators">
      <span class="indicator active" data-slide="0"></span>
      <span class="indicator" data-slide="1"></span>
      <span class="indicator" data-slide="2"></span>
      <span class="indicator" data-slide="3"></span>
      <span class="indicator" data-slide="4"></span>
      <span class="indicator" data-slide="5"></span>
    </div>
  </div>

  <!-- Plans Page -->
  <div id="plans" class="page">
   <h1 class="keep-original-font gradient-title">Our Plans</h1>
    <p class="plan-intro">Choose the perfect plan for your fitness journey</p>
    
    <div class="tables-container">
      <!-- Training Programs Table -->
      <table class="programs-table">
        <thead>
          <tr>
            <th colspan="2">Training Programs</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td class="program-title">Gain Muscle</td>
            <td class="program-description">
              • Progressive overload training<br>
              • High-protein nutrition plan<br>
              • Recovery strategies<br>
              • Supplement guidance
              
            </td>
          </tr>
          <tr>
            <td class="program-title">Lose Fat</td>
            <td class="program-description">
              • Fat-burning workouts<br>
              • Calorie-deficit meal plans<br>
              • Cardio strategies<br>
              • Metabolism boosting
              
            </td>
          </tr>
          <tr>
            <td class="program-title">Fitness Lifestyle</td>
            <td class="program-description">
              • Balanced workout routine<br>
              • Sustainable nutrition<br>
              • Stress management<br>
              • Long-term wellness
              
            </td>
          </tr>
        </tbody>
      </table>

      <!-- Pricing Table -->
      <table class="pricing-table">
        <thead>
          <tr>
            <th colspan="3">Pricing Plans</th>
          </tr>
          <tr>
            <th>Duration</th>
            <th>Price</th>
            <th>Action</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>1 Month</td>
            <td class="price-amount">$24 (1200 EGP)</td>
            <td><a href="https://ipn.eg/S/karim.arafat8640/instapay/0fheId-for-1month" class="plan-button" target="_blank">Choose</a></td>
          </tr>
          <tr>
            <td>3 Months</td>
            <td class="price-amount">$60 (3000 EGP)<br><span class="price-saving">Save $12 (600 EGP)</span>
           
            </td>
            <td><a href="https://ipn.eg/S/karim.arafat8640/instapay/0fheId-for-3months" class="plan-button" target="_blank">Choose</a></td>
          </tr>
          <tr>
            <td>6 Months</td>
            <td class="price-amount">$108 (5400 EGP)<br><span class="price-saving">Save $36 (1800 EGP)</span>
              
            </td>
            <td><a href="https://ipn.eg/S/karim.arafat8640/instapay/0fheId-for-6months" class="plan-button" target="_blank">Choose</a></td>
          </tr>
          <tr>
            <td>1 Year</td>
            <td class="price-amount">$192 (9600 EGP)<br><span class="price-saving">Save $96 (4800 EGP)</span>
              
            </td>
            <td><a href="https://ipn.eg/S/karim.arafat8640/instapay/0fheId-for-1year" class="plan-button" target="_blank">Choose</a></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>

 <!-- Contact Page -->
<div id="contact" class="page">
  <h1 class="gradient-title">Contact Us</h1>
  <p class="contact-cta">Get in touch with Team K-Fit for any questions or to start your fitness journey today!</p>
  
  <div class="social-icons-container">
    <!-- Instagram -->
    <div class="social-frame">
      <a href="https://www.instagram.com/karimarafat_?igsh=OWI3dGZpbTE4NDhh" target="_blank" class="social-link">
        <img src="instagram logo.png" alt="Instagram" class="social-icon">
        <span class="social-name">Instagram</span>
      </a>
    </div>
    
    <!-- Facebook -->
    <div class="social-frame">
      <a href="https://www.facebook.com/share/16mR7niBYz/?mibextid=wwXIfr" target="_blank" class="social-link">
        <img src="facebook logo.png" alt="Facebook" class="social-icon">
        <span class="social-name">Facebook</span>
      </a>
    </div>
    
    <!-- WhatsApp -->
    <div class="social-frame">
      <a href="http://wa.me/201281085427" target="_blank" class="social-link">
        <img src="whatsapp logo.png" alt="WhatsApp" class="social-icon">
        <span class="social-name">WhatsApp</span>
      </a>
    </div>
  </div>
</div>

  <script>
    // Function to show selected page
    function showPage(pageId) {
      // Hide all pages
      document.querySelectorAll('.page').forEach(page => {
        page.classList.remove('active-page');
      });
      
      // Show selected page
      const newPage = document.getElementById(pageId);
      newPage.classList.add('active-page');
      
      // Update active nav link
      document.querySelectorAll('.nav-link').forEach(link => {
        link.classList.remove('active-nav');
        if (link.getAttribute('href') === `#${pageId}`) {
          link.classList.add('active-nav');
        }
      });
      
      // Force reflow to restart animations
      void newPage.offsetWidth;
    }

    // Carousel functionality
    document.addEventListener('DOMContentLoaded', function() {
      const carousel = document.querySelector('.carousel');
      const slides = document.querySelectorAll('.carousel-slide');
      const prevBtn = document.getElementById('prevBtn');
      const nextBtn = document.getElementById('nextBtn');
      const indicators = document.querySelectorAll('.indicator');
      
      let currentIndex = 0;
      const slideCount = slides.length;
      let isDragging = false;
      let startPos = 0;
      let currentTranslate = 0;
      let prevTranslate = 0;
      let animationID;
      
      // Update carousel position
      function updateCarousel() {
        carousel.style.transform = `translateX(-${currentIndex * 100}%)`;
        
        // Update indicators
        indicators.forEach((indicator, index) => {
          indicator.classList.toggle('active', index === currentIndex);
        });
      }
      
      // Next slide
      function nextSlide() {
        currentIndex = (currentIndex + 1) % slideCount;
        updateCarousel();
      }
      
      // Previous slide
      function prevSlide() {
        currentIndex = (currentIndex - 1 + slideCount) % slideCount;
        updateCarousel();
      }
      
      // Button events
      nextBtn.addEventListener('click', nextSlide);
      prevBtn.addEventListener('click', prevSlide);
      
      // Indicator events
      indicators.forEach(indicator => {
        indicator.addEventListener('click', function() {
          currentIndex = parseInt(this.getAttribute('data-slide'));
          updateCarousel();
        });
      });
      
      // Touch events for swipe
      carousel.addEventListener('touchstart', touchStart, {passive: true});
      carousel.addEventListener('touchend', touchEnd, {passive: true});
      carousel.addEventListener('touchmove', touchMove, {passive: true});
      
      // Mouse events for drag
      carousel.addEventListener('mousedown', touchStart);
      carousel.addEventListener('mouseup', touchEnd);
      carousel.addEventListener('mouseleave', touchEnd);
      carousel.addEventListener('mousemove', touchMove);
      
      function touchStart(e) {
        if (e.type === 'touchstart') {
          startPos = e.touches[0].clientX;
        } else {
          startPos = e.clientX;
          e.preventDefault();
        }
        isDragging = true;
        animationID = requestAnimationFrame(animation);
        carousel.style.transition = 'none';
      }
      
      function touchMove(e) {
        if (isDragging) {
          const currentPosition = e.type === 'touchmove' ? e.touches[0].clientX : e.clientX;
          currentTranslate = prevTranslate + currentPosition - startPos;
        }
      }
      
      function touchEnd() {
        isDragging = false;
        cancelAnimationFrame(animationID);
        
        const movedBy = currentTranslate - prevTranslate;
        
        if (movedBy < -50 && currentIndex < slideCount - 1) {
          currentIndex += 1;
        }
        
        if (movedBy > 50 && currentIndex > 0) {
          currentIndex -= 1;
        }
        
        setPositionByIndex();
      }
      
      function animation() {
        carousel.style.transform = `translateX(${currentTranslate}px)`;
        if (isDragging) {
          requestAnimationFrame(animation);
        }
      }
      
      function setPositionByIndex() {
        currentTranslate = currentIndex * -window.innerWidth;
        prevTranslate = currentTranslate;
        carousel.style.transition = 'transform 0.3s ease-out';
        carousel.style.transform = `translateX(${currentTranslate}px)`;
        updateCarousel();
      }

      // Set up navigation
      // Handle nav link clicks
      document.querySelectorAll('.nav-link').forEach(link => {
        link.addEventListener('click', function(e) {
          e.preventDefault();
          const pageId = this.getAttribute('href').substring(1);
          showPage(pageId);
          history.pushState(null, null, this.getAttribute('href'));
        });
      });

      // Check URL hash on load
      const hash = window.location.hash.substring(1);
      if (hash) {
        showPage(hash);
      } else {
        showPage('home');
      }

      // Handle back/forward navigation
      window.addEventListener('popstate', function() {
        const hash = window.location.hash.substring(1);
        showPage(hash || 'home');
      });
    });
  </script>
</body>
</html>
