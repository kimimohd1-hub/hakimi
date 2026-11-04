# hakimi
My personal CV website with Fetch API city clock
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Curriculum of Mohamad Hakimi">
    <meta name="keywords" content="CV, technologies, HTML, Programming, Student">
    <meta name="author" content="Mohamad Hakimi">
    <title>Mohamad Hakimi - Curriculum</title>
    
    <!-- ========================================== -->
    <!-- KOD CSS DIMASUKKAN DI SINI -->
    <!-- ========================================== -->
    <style>
        /* GLOBAL STYLES & RESET */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f4f7f6;
            color: #333;
            line-height: 1.6;
        }

        /* HEADER & NAVIGATION */
        header {
            background-color: #0D47A1;
            color: white;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
        }

        .nav-container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo-title {
            font-size: 1.5rem;
            font-weight: bold;
            letter-spacing: 1px;
        }

        .burger-btn {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.8rem;
            cursor: pointer;
        }

        .nav-menu {
            display: flex;
            gap: 20px;
        }

        .nav-menu a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-menu a:hover {
            color: #90caf9;
        }

        /* MAIN WRAPPER & CONTENT */
        .main-wrapper {
            max-width: 900px;
            margin: 40px auto;
            background: white;
            padding: 40px;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        svg, h1 {
            display: block;
            margin: 0 auto 10px auto;
            text-align: center;
        }

        h1 {
            color: #0D47A1;
            font-size: 2.2rem;
            margin-bottom: 30px;
        }

        /* SECTIONS */
        section {
            margin-bottom: 40px;
            padding-top: 20px;
            border-top: 2px solid #e0e0e0;
        }

        h2 {
            color: #1E88E5;
            margin-bottom: 15px;
            font-size: 1.5rem;
        }

        p {
            margin-bottom: 15px;
            text-align: justify;
        }

        ul {
            list-style-type: square;
            margin-left: 20px;
            margin-bottom: 20px;
        }

        li {
            margin-bottom: 8px;
        }

        /* CAROUSEL SECTION */
        .carousel-container {
            position: relative;
            background-color: #f8f9fa;
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
            overflow: hidden;
        }

        .carousel-slide {
            display: none;
            animation: fadeEffect 0.5s ease-in-out;
        }

        .carousel-slide.active {
            display: block;
        }

        .carousel-card h3 {
            color: #0D47A1;
            margin-bottom: 10px;
        }

        .carousel-prev, .carousel-next {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: #1E88E5;
            color: white;
            border: none;
            padding: 10px 15px;
            cursor: pointer;
            border-radius: 50%;
            font-size: 1rem;
            transition: background 0.3s;
        }

        .carousel-prev:hover, .carousel-next:hover {
            background-color: #0D47A1;
        }

        .carousel-prev { left: 10px; }
        .carousel-next { right: 10px; }

        @keyframes fadeEffect {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* CONTACT FORM */
        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-group label {
            font-weight: 600;
            margin-bottom: 5px;
            color: #555;
        }

        .form-group input, 
        .form-group textarea {
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 6px;
            font-family: inherit;
            font-size: 1rem;
            transition: border-color 0.3s;
        }

        .form-group input:focus, 
        .form-group textarea:focus {
            outline: none;
            border-color: #1E88E5;
            box-shadow: 0 0 5px rgba(30, 136, 229, 0.3);
        }

        .submit-btn {
            background-color: #1E88E5;
            color: white;
            padding: 12px;
            border: none;
            border-radius: 6px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.3s;
        }

        .submit-btn:hover {
            background-color: #0D47A1;
        }

        /* SCROLL TO TOP BUTTON */
        .scroll-top-btn {
            display: none; 
            position: fixed;
            bottom: 30px;
            right: 30px;
            background-color: #1E88E5;
            color: white;
            border: none;
            padding: 15px 20px;
            border-radius: 50%;
            font-size: 1.2rem;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
            z-index: 999;
            transition: background 0.3s;
        }

        .scroll-top-btn:hover {
            background-color: #0D47A1;
        }

        /* RESPONSIVE DESIGN (UNTUK HANDPHONE) */
        @media (max-width: 768px) {
            .main-wrapper {
                margin: 15px;
                padding: 20px;
            }

            .nav-menu {
                display: none;
                flex-direction: column;
                width: 100%;
                position: absolute;
                top: 60px;
                left: 0;
                background-color: #0D47A1;
                padding: 10px 0;
                text-align: center;
            }

            .nav-menu.active {
                display: flex;
            }

            .nav-menu a {
                padding: 10px;
                border-bottom: 1px solid #1565C0;
            }

            .burger-btn {
                display: block;
            }

            h1 {
                font-size: 1.8rem;
            }
        }
    </style>
</head>

<body>

    <!-- Header & Burger Navigation Menu -->
    <header>
        <div class="nav-container">
            <div class="logo-title">Mohamad Hakimi</div>
            <button class="burger-btn" id="burgerBtn" aria-label="Toggle navigation">
                &#9776;
            </button>
            <nav class="nav-menu" id="navMenu">
                <a href="#about">About</a>
                <a href="#carousel-section">Portfolio</a>
                <a href="#contact">Contact Me</a>
            </nav>
        </div>
    </header>

    <div class="main-wrapper">
        
        <!-- SVG Logo -->
        <svg width="180" height="180" viewBox="0 0 180 180" xmlns="http://www.w3.org/2000/svg">
            <circle cx="90" cy="90" r="80" fill="#1E88E5" stroke="#0D47A1" stroke-width="5" />
            <rect x="45" y="55" width="90" height="55" rx="6" fill="white" stroke="#0D47A1" stroke-width="3" />
            <rect x="35" y="115" width="110" height="10" rx="3" fill="#0D47A1" />
            <rect x="60" y="90" width="10" height="15" fill="#42A5F5" />
            <rect x="78" y="80" width="10" height="25" fill="#1E88E5" />
            <rect x="96" y="70" width="10" height="35" fill="#1565C0" />
            <rect x="114" y="60" width="10" height="45" fill="#0D47A1" />
            <text x="90" y="45" text-anchor="middle" font-size="20" font-family="Arial" font-weight="bold" fill="white">
                KIMI
            </text>
        </svg>

        <h1>My Curriculum</h1>

        <!-- TAMBAHAN WORKSHOP 8: FETCH API CITY CLOCK -->
        <div id="city-clock" style="text-align: center; font-size: 1.1rem; margin-bottom: 25px; padding: 15px; background-color: #e3f2fd; border-radius: 8px; border: 1px solid #90caf9; color: #0D47A1;">
            Loading time and city...
        </div>

        <!-- Counter Visitor -->
        <div class="visitor-counter" style="text-align: center; margin-bottom: 20px; font-weight: bold; color: #555;">
            📊 Website Visitors: <span id="visitorCount">0</span>
        </div>

        <!-- Personal Information Section -->
        <section id="about">
            <h2>Personal Information</h2>
            <p>
                My name is <strong>Mohamad Hakimi</strong>. I am an IT student at Fatoni University. I am interested in web
                development and programming. I speak Khmer, English, Malay, and basic Thai. I have experience using HTML, CSS, JavaScript, and SQL.
                I enjoy learning new technologies and developing useful websites and projects.
            </p>

            <h2>Languages I Speak</h2>
            <ul>
                <li>Khmer</li>
                <li>English</li>
                <li>Malay</li>
                <li>Basic Thai</li>
            </ul>

            <h2>Programming Languages I Have Used</h2>
            <ul>
                <li>HTML</li>
                <li>CSS</li>
                <li>JavaScript</li>
            </ul>
        </section>

        <!-- Carousel Section -->
        <section id="carousel-section">
            <h2>Featured Work & Highlights</h2>
            <div class="carousel-container">
                <div class="carousel-slide active">
                    <div class="carousel-card">
                        <h3>Web Development</h3>
                        <p>Building responsive and modern web interfaces using standard technologies.</p>
                    </div>
                </div>
                <div class="carousel-slide">
                    <div class="carousel-card">
                        <h3>UI/UX Design</h3>
                        <p>Focusing on user-centered design, user flows, and clear structures.</p>
                    </div>
                </div>
                <div class="carousel-slide">
                    <div class="carousel-card">
                        <h3>Database & SQL</h3>
                        <p>Managing and querying relational databases like PostgreSQL.</p>
                    </div>
                </div>

                <button class="carousel-prev" id="prevBtn">&#10094;</button>
                <button class="carousel-next" id="nextBtn">&#10095;</button>
            </div>
        </section>

        <!-- Contact Me Form Section -->
        <section id="contact">
            <h2>Contact Me</h2>
            <form id="contactForm" class="contact-form">
                
                <div class="form-group">
                    <label for="userName">Full Name (Letters and spaces only):</label>
                    <input type="text" id="userName" name="userName" required 
                           pattern="^[A-Za-z\s]{3,50}$" 
                           title="Please enter 3 to 50 characters, letters and spaces only.">
                </div>

                <div class="form-group">
                    <label for="userEmail">Email Address:</label>
                    <input type="email" id="userEmail" name="userEmail" required>
                </div>

                <div class="form-group">
                    <label for="userPhone">Phone Number (e.g. 0812345678):</label>
                    <input type="tel" id="userPhone" name="userPhone" required 
                           pattern="^[0-9]{9,12}$" 
                           title="Please enter a valid phone number with 9 to 12 digits.">
                </div>

                <div class="form-group">
                    <label for="userMessage">Message:</label>
                    <textarea id="userMessage" name="userMessage" rows="4" required></textarea>
                </div>

                <button type="submit" class="submit-btn">Send Message</button>
            </form>
            <div id="formFeedback" class="form-feedback"></div>
        </section>

    </div>

    <!-- Floating Go To Top Button -->
    <button id="scrollTopBtn" class="scroll-top-btn" title="Go to top">&#8593;</button>

    <!-- ========================================== -->
    <!-- KOD JAVASCRIPT DIMASUKKAN DI SINI -->
    <!-- ========================================== -->
    <script>
        // --- WORKSHOP 8: JS FETCH API - CITY CLOCK ---
        function fetchCityClock() {
            const apiURL = 'https://worldtimeapi.org/api/timezone/Asia/Kuala_Lumpur';

            fetch(apiURL)
                .then(response => {
                    if (!response.ok) {
                        throw new Error('Ralat rangkaian');
                    }
                    return response.json();
                })
                .then(data => {
                    const cityRaw = data.timezone.split('/')[1];
                    const cityName = cityRaw.replace('_', ' ');

                    const timePart = data.datetime.split('T')[1]; 
                    const timeOnly = timePart.substring(0, 5); 

                    const clockElement = document.getElementById('city-clock');
                    clockElement.innerHTML = `🕒 <strong>O'clock:</strong> It is currently <strong>${timeOnly}</strong> in <strong>${cityName}</strong>`;
                })
                .catch(error => {
                    console.error('Fetch API Error:', error);
                    document.getElementById('city-clock').innerHTML = `⚠️ Could not load city clock. Please check your internet connection.`;
                });
        }

        document.addEventListener('DOMContentLoaded', () => {
            fetchCityClock();
            setInterval(fetchCityClock, 60000); 
            
            // --- NAVIGATION, CAROUSEL, FORM ---
            const burgerBtn = document.getElementById('burgerBtn');
            const navMenu = document.getElementById('navMenu');

            if (burgerBtn && navMenu) {
                burgerBtn.addEventListener('click', () => {
                    navMenu.classList.toggle('active');
                });
            }

            const slides = document.querySelectorAll('.carousel-slide');
            const prevBtn = document.getElementById('prevBtn');
            const nextBtn = document.getElementById('nextBtn');
            let currentSlide = 0;

            function showSlide(index) {
                if(slides.length > 0) {
                    slides.forEach(slide => slide.classList.remove('active'));
                    slides[index].classList.add('active');
                }
            }

            if (nextBtn && prevBtn) {
                nextBtn.addEventListener('click', () => {
                    currentSlide = (currentSlide + 1) % slides.length;
                    showSlide(currentSlide);
                });

                prevBtn.addEventListener('click', () => {
                    currentSlide = (currentSlide - 1 + slides.length) % slides.length;
                    showSlide(currentSlide);
                });
            }

            const contactForm = document.getElementById('contactForm');
            const formFeedback = document.getElementById('formFeedback');

            if (contactForm) {
                contactForm.addEventListener('submit', (e) => {
                    e.preventDefault(); 
                    formFeedback.textContent = "Thank you! Your message has been sent successfully.";
                    formFeedback.style.color = "green";
                    formFeedback.style.marginTop = "10px";
                    contactForm.reset();
                });
            }

            const scrollTopBtn = document.getElementById('scrollTopBtn');

            if (scrollTopBtn) {
                window.addEventListener('scroll', () => {
                    if (window.scrollY > 300) {
                        scrollTopBtn.style.display = "block";
                    } else {
                        scrollTopBtn.style.display = "none";
                    }
                });

                scrollTopBtn.addEventListener('click', () => {
                    window.scrollTo({
                        top: 0,
                        behavior: 'smooth'
                    });
                });
            }

            const visitorCount = document.getElementById('visitorCount');
            if (visitorCount) {
                visitorCount.textContent = Math.floor(Math.random() * 1000) + 500; 
            }
        });
    </script>
</body>

</html>
