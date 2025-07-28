<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Greenscape Retreat - Luxury Villa in Dubai</title>
  
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;600&family=Cinzel:wght@400;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/flatpickr/dist/flatpickr.min.css">

  <style>
    :root { --brand-color: #b79f69; }
    body { margin: 0; background-color: #f5f0e6; color: #3a3a2e; font-family: 'Cormorant Garamond', serif; line-height: 1.6; }
    a { text-decoration: none; color: inherit; }
    
    .main-header {
      position: relative; height: 100vh; display: flex; align-items: center; justify-content: center;
      text-align: center; color: white;
      background: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.3)), url('https://i.ibb.co/C36BZpCY/pexels-abid-ali-150086727-10647349-1-1.jpg') no-repeat center center/cover;
    }
    .main-header h1 { font-size: 5.5rem; font-family: 'Cinzel', serif; }

    .sticky-nav { background-color: white; display: flex; justify-content: space-between; align-items: center; padding: 15px 30px; box-shadow: 0 4px 8px rgba(0,0,0,0.05); position: sticky; top: 0; z-index: 1000; }
    .logo { font-size: 22px; font-weight: bold; color: #000; font-family: 'Cinzel', serif; }
    .nav-links { list-style: none; display: flex; gap: 30px; margin: 0; }
    .nav-links a { font-weight: 600; transition: color 0.3s; font-size: 1.1rem; }
    .nav-links a:hover { color: var(--brand-color); }
    .hamburger { display: none; cursor: pointer; font-size: 24px; }

    .btn { background-color: var(--brand-color); color: white; padding: 14px 28px; border: none; border-radius: 6px; font-size: 16px; cursor: pointer; transition: background-color 0.3s; width: 100%; font-family: 'Cormorant Garamond', serif; font-weight: 600; }
    .btn:hover { background-color: #a28b5a; }

    .section { padding: 60px 30px; max-width: 1200px; margin: auto; opacity: 0; transition: opacity 0.8s ease-in-out; }
    .section.visible { opacity: 1; }
    .section h2 { font-size: 2.8rem; color: var(--brand-color); margin-bottom: 30px; text-align: center; font-family: 'Cinzel', serif; }
    .section h3 { color: var(--brand-color); font-size: 24px; margin-top: 40px; border-bottom: 1px solid #e0e0e0; padding-bottom: 10px; margin-bottom: 30px; }
    .section > p { text-align: center; max-width: 850px; margin: 0 auto 30px auto; font-size: 1.2rem; line-height: 1.8; }
    
    #why-us, #booking, #services { background-color: #f9f6f2; }

    .services-grid, .gallery { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 30px; }
    .service-card { background-color: white; padding: 30px; border-radius: 12px; box-shadow: 0 5px 15px rgba(183, 159, 105, 0.1); text-align: center; }
    .service-card .service-icon { font-size: 40px; margin-bottom: 15px; display: block; color: var(--brand-color); }
    .service-card h4 { font-size: 20px; color: #333; margin-bottom: 10px; }
    .service-card p { font-size: 1rem; color: #666; margin: 0; line-height: 1.5; }
    
    .gallery-img { width: 100%; border-radius: 12px; height: 220px; object-fit: cover; }
    
    .quote-form-container { max-width: 700px; margin: auto; background: white; padding: 40px; border-radius: 12px; box-shadow: 0 5px 15px rgba(183, 159, 105, 0.1); }
    .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
    .form-grid .full-width { grid-column: 1 / -1; }
    .quote-form-container input { width: 100%; padding: 12px; border: 1px solid #ddd; border-radius: 6px; font-family: 'Cormorant Garamond', serif; font-size: 1rem; box-sizing: border-box; }
    
    .map-container { max-width: 800px; margin: 40px auto 0 auto; border-radius: 12px; overflow: hidden; box-shadow: 0 10px 25px rgba(0,0,0,0.1); }

    .whatsapp-fab { position: fixed; bottom: 30px; right: 30px; background-color: #25D366; color: white; width: 60px; height: 60px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 30px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); z-index: 1001; transition: transform 0.3s; }
    .whatsapp-fab:hover { transform: scale(1.1); }
    
    footer { background: #222; color: #eee; padding: 40px 20px; text-align: center; }

    /* --- Chatbot Styles --- */
    .chatbot-fab { position: fixed; bottom: 30px; left: 30px; background-color: var(--brand-color); color: white; width: 60px; height: 60px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 26px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); z-index: 1001; cursor: pointer; transition: transform 0.3s; }
    .chatbot-fab:hover { transform: scale(1.1); }
    #chatbot-window { display: none; position: fixed; bottom: 100px; left: 30px; width: 320px; max-height: 420px; background: white; border-radius: 12px; box-shadow: 0 5px 20px rgba(0,0,0,0.3); z-index: 1001; overflow: hidden; font-family: 'Cormorant Garamond', serif; }
    #chatbot-window .header { background-color: var(--brand-color); color: white; padding: 14px 18px; font-weight: bold; display: flex; justify-content: space-between; align-items: center; font-size: 18px; }
    #chatbot-window .header #close-chatbot { cursor: pointer; }
    #chat-content { padding: 15px; max-height: 280px; overflow-y: auto; font-size: 1rem; }
    .chat-option { background-color: #fff9ef; color: #3a3a2e; border: 1px solid var(--brand-color); border-radius: 25px; padding: 8px 14px; margin: 6px 4px 0 0; font-size: 0.9rem; cursor: pointer; transition: background-color 0.3s; display: inline-block; }
    .chat-option:hover { background-color: var(--brand-color); color: white; }
    .flatpickr-day.flatpickr-disabled, .flatpickr-day.flatpickr-disabled:hover { background: #e74c3c !important; color: white !important; border-color: #c0392b !important; text-decoration: line-through; }

    @media (max-width: 768px) {
        .main-header h1 { font-size: 3rem; }
        .section { padding: 50px 20px; }
        .nav-links { display: none; position: absolute; top: 72px; right: 0; background-color: white; width: 100%; flex-direction: column; text-align: center; box-shadow: 0 8px 16px rgba(0,0,0,0.1); }
        .nav-links.active { display: flex; }
        .hamburger { display: block; }
        .form-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>

<body>

  <header class="main-header"><h1>Greenscape Retreat</h1></header>

  <nav class="sticky-nav">
    <div class="logo">Greenscape Retreat</div>
    <ul class="nav-links" id="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#gallery">Gallery</a></li>
      <li><a href="#booking">Booking</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <div class="hamburger" id="hamburger"><i class="fa-solid fa-bars"></i></div>
  </nav>

  <main>
    <section id="about" class="section">
      <h2>Welcome to Your Private Paradise</h2>
      <p>Step into Greenscape Retreat, an architectural masterpiece where timeless Arabic heritage gracefully intertwines with sleek, modern minimalism. Located in the exclusive Al Jaffaliya district, our 22-bedroom villa is more than just a residence—it is a sanctuary of unparalleled luxury and privacy.</p>
    </section>

    <section id="why-us" class="section">
        <h2>Why Choose Us?</h2>
        <p>At Greenscape Retreat, we believe true luxury lies in seamless personalization. We move beyond a simple stay to offer a fully curated lifestyle experience. Our dedicated team, from the private chef anticipating your culinary desires to the VIP concierge securing exclusive reservations, works tirelessly behind the scenes. Every detail is meticulously managed, ensuring your time is spent creating memories, not managing logistics. This is your private sanctuary, run with the precision of a five-star hotel.</p>
    </section>

    <section id="services" class="section">
      <h2>Our Premium Services</h2>
      <div class="services-grid">
        <div class="service-card"><i class="fa-solid fa-utensils service-icon"></i><h4>Private Chef</h4><p>Indulge in bespoke gourmet meals crafted by our professional in-house chef, tailored to your every culinary desire.</p></div>
        <div class="service-card"><i class="fa-solid fa-car-side service-icon"></i><h4>Chauffeur Service</h4><p>Navigate Dubai in style and comfort with our discreet, professional chauffeur service, available to you around the clock.</p></div>
        <div class="service-card"><i class="fa-solid fa-champagne-glasses service-icon"></i><h4>Event Hosting</h4><p>From elegant weddings to exclusive corporate events, our dedicated team will provide seamless support to host an unforgettable occasion.</p></div>
        <div class="service-card"><i class="fa-solid fa-broom service-icon"></i><h4>Daily Cleaning</h4><p>Experience immaculate living every day with our professional and discreet housekeeping team ensuring your utmost comfort.</p></div>
        <div class="service-card"><i class="fa-solid fa-shield-halved service-icon"></i><h4>Private Security</h4><p>Your safety and privacy are paramount. We provide 24/7 high-grade security personnel to ensure complete peace of mind.</p></div>
        <div class="service-card"><i class="fa-solid fa-fire-burner service-icon"></i><h4>BBQ Setup</h4><p>Enjoy a memorable evening under the stars with a complete BBQ experience, fully set up, catered, and cleaned by our staff.</p></div>
        <div class="service-card"><i class="fa-solid fa-smog service-icon"></i><h4>Shisha Lounge</h4><p>Unwind in our authentic, Arabic-inspired shisha lounge, featuring plush seating and a selection of exotic, premium flavors.</p></div>
        <div class="service-card"><i class="fa-solid fa-concierge-bell service-icon"></i><h4>VIP Concierge</h4><p>Your personal genie. Our VIP concierge is on hand to manage exclusive reservations, bookings, and any special requests.</p></div>
      </div>
    </section>

    <section id="gallery" class="section">
      <h2>Villa Gallery</h2>
      <h3>Exterior Views</h3>
      <div class="gallery">
        <img src="https://i.ibb.co/hxPkz9x5/pexels-mjlo-19344317.jpg" class="gallery-img" alt="Terrace View">
        <img src="https://i.ibb.co/ymnwn4r0/pexels-abid-ali-150086727-10647349.jpg" class="gallery-img" alt="Front of Villa">
        <img src="https://i.ibb.co/gLZWvjKj/pexels-chad-populis-2148434888-30725656.jpg" class="gallery-img" alt="Villa at Night">
      </div>
      <h3>Interiors & Rooms</h3>
      <div class="gallery">
        <img src="https://i.ibb.co/1txpfbC6/pexels-heyho-6585762.jpg" class="gallery-img" alt="Bedroom Interior">
        <img src="https://i.ibb.co/6chWkTSM/pexels-heyho-7533759.jpg" class="gallery-img" alt="Elegant Room">
        <img src="https://i.ibb.co/bg3w0sdH/pexels-heyho-8134753.jpg" class="gallery-img" alt="Luxury Bathroom">
      </div>
    </section>

    <section id="booking" class="section">
      <h2>Request a Quote</h2>
      <p>Please fill out the form below to inquire about your desired dates. We will respond promptly with a personalized quote and availability.</p>
      
      <div class="quote-form-container">
        <form action="#" method="POST">
          <div class="form-grid">
            <div class="full-width"><input type="text" name="name" placeholder="Full Name" required></div>
            <div class="full-width"><input type="email" name="email" placeholder="Email Address" required></div>
            <div><input type="text" name="checkin" id="checkin-date" placeholder="Check-in Date" required></div>
            <div><input type="text" name="checkout" id="checkout-date" placeholder="Check-out Date" required></div>
            <div class="full-width"><input type="number" name="guests" placeholder="Number of Guests" min="1" required></div>
            <div class="full-width"><button type="submit" class="btn">Send Inquiry</button></div>
          </div>
        </form>
      </div>
    </section>

    <section id="contact" class="section">
      <h2>Our Location</h2>
      <p><strong>Phone:</strong> +971 63 553 23565 | <strong>Email:</strong> bookings@oasisevents.ae</p>
      <div class="map-container">
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3610.453982829598!2d55.18127167538232!3d25.10312697771618!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMjXCsDA2JzExLjIiTiA1NcKwMTEnMDIuMCJF!5e0!3m2!1sen!2sus!4v1678886400000!5m2!1sen!2sus" width="100%" height="350" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
      </div>
    </section>
  </main>
  
  <footer><p>© 2025 Greenscape Retreat | All rights reserved</p></footer>
  
  <a href="https://wa.me/9716355323565" target="_blank" class="whatsapp-fab" aria-label="Chat on WhatsApp"><i class="fab fa-whatsapp"></i></a>
  
  <!-- Chatbot -->
  <div class="chatbot-fab" id="chatbot-fab" aria-label="Open Chatbot"><i class="fa-solid fa-comment-dots"></i></div>

  <div id="chatbot-window">
    <div class="header">
      <span>Villa Assistant</span>
      <span id="close-chatbot">×</span>
    </div>
    <div id="chat-content">
      <p><strong>Bot:</strong> Hello! 👋 How can I assist you today?</p>
      <div>
        <button class="chat-option" data-reply="Our available dates are limited. Please check the form in the Booking section.">📅 Check Availability</button>
        <button class="chat-option" data-reply="We offer private chef, chauffeur, BBQ setup, shisha lounge, VIP concierge, and more.">💎 View Services</button>
        <button class="chat-option" data-reply="We are located in Al Jaffaliya, Dubai. Scroll to the Contact section for the map.">📍 Location Info</button>
      </div>
    </div>
  </div>
  <!-- End Chatbot -->

  <script src="https://cdn.jsdelivr.net/npm/flatpickr"></script>
  <script>
    document.addEventListener("DOMContentLoaded", function () {
        // --- Hamburger Menu ---
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.getElementById('nav-links');
        hamburger.addEventListener('click', () => navLinks.classList.toggle('active'));

        // --- Animate Sections on Scroll ---
        const sections = document.querySelectorAll('.section');
        const observer = new IntersectionObserver(entries => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    observer.unobserve(entry.target);
                }
            });
        }, { threshold: 0.15 });
        sections.forEach(section => observer.observe(section));

        // --- Date Picker (flatpickr) ---
        const bookedDates = ["2024-12-24", "2024-12-25", "2024-12-31", "2025-01-01"];
        flatpickr("#checkin-date", { minDate: "today", dateFormat: "Y-m-d", disable: bookedDates });
        flatpickr("#checkout-date", { minDate: "today", dateFormat: "Y-m-d", disable: bookedDates });

        // --- Chatbot Functionality ---
        const chatbotFab = document.getElementById("chatbot-fab");
        const chatbotWindow = document.getElementById("chatbot-window");
        const closeChatbot = document.getElementById("close-chatbot");
        const chatContent = document.getElementById("chat-content");

        chatbotFab.addEventListener("click", () => {
          chatbotWindow.style.display = (chatbotWindow.style.display === "none" || chatbotWindow.style.display === "") ? "block" : "none";
        });

        closeChatbot.addEventListener("click", () => {
          chatbotWindow.style.display = "none";
        });

        document.querySelectorAll(".chat-option").forEach(btn => {
          btn.addEventListener("click", () => {
            const userMsg = btn.textContent;
            const botReply = btn.dataset.reply;

            const userHTML = `<p><strong>You:</strong> ${userMsg}</p>`;
            const botHTML = `<p><strong>Bot:</strong> ${botReply}</p>`;

            chatContent.insertAdjacentHTML("beforeend", userHTML + botHTML);
            chatContent.scrollTop = chatContent.scrollHeight; // Auto-scroll to the latest message
          });
        });
    });
  </script>
</body>
</html>
