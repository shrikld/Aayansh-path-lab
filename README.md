<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aayansh Path Lab - Advanced Medical Diagnostics</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            font-size: 1.5rem;
            font-weight: bold;
        }

        .logo img {
            width: 60px;
            height: 60px;
            margin-right: 15px;
            background: white;
            padding: 5px;
            border-radius: 10px;
            object-fit: contain;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 25px;
        }

        .nav-links a:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 120px 0 80px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse"><path d="M 10 0 L 0 0 0 10" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="1"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>');
            opacity: 0.3;
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease 0.2s both;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            color: white;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease 0.4s both;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.25);
        }

        /* Services Section */
        .services {
            padding: 80px 0;
            background: #f8f9fa;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #2c3e50;
            position: relative;
        }

        .section-title::after {
            content: '';
            width: 80px;
            height: 4px;
            background: linear-gradient(45deg, #3498db, #2980b9);
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .service-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 5px 25px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            border: 1px solid #e9ecef;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.15);
        }

        .service-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #3498db;
        }

        .service-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #2c3e50;
        }

        /* About Section */
        .about {
            padding: 80px 0;
            background: linear-gradient(135deg, #74b9ff 0%, #0984e3 100%);
            color: white;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-text h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
        }

        .about-text p {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            opacity: 0.9;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1rem;
            margin-top: 2rem;
        }

        .stat-item {
            text-align: center;
            padding: 1rem;
            background: rgba(255,255,255,0.1);
            border-radius: 10px;
        }

        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            display: block;
        }

        /* Contact Section */
        .contact {
            padding: 80px 0;
            background: #2c3e50;
            color: white;
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }

        .contact-info h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #3498db;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
        }

        .contact-item span {
            font-size: 1.2rem;
            margin-right: 1rem;
            color: #3498db;
        }

        .contact-form {
            background: rgba(255,255,255,0.1);
            padding: 2rem;
            border-radius: 15px;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: none;
            border-radius: 8px;
            background: rgba(255,255,255,0.9);
            color: #333;
            font-size: 1rem;
        }

        .form-group textarea {
            resize: vertical;
            height: 120px;
        }

        .submit-btn {
            background: linear-gradient(45deg, #00b894, #00a085);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: bold;
            transition: all 0.3s ease;
            width: 100%;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        /* Footer */
        footer {
            background: #1a1a1a;
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .about-content,
            .contact-content {
                grid-template-columns: 1fr;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Floating elements */
        .floating-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 1;
        }

        .floating-element {
            position: absolute;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        .floating-element:nth-child(1) {
            width: 80px;
            height: 80px;
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }

        .floating-element:nth-child(2) {
            width: 60px;
            height: 60px;
            top: 60%;
            right: 10%;
            animation-delay: 2s;
        }

        .floating-element:nth-child(3) {
            width: 100px;
            height: 100px;
            bottom: 20%;
            left: 20%;
            animation-delay: 4s;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <div class="logo">
                <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR42mNkYPhfDwAChwGA60e6kgAAAABJRU5ErkJggg==" alt="Aayansh Path Lab Logo" style="background-image: url('data:image/svg+xml;charset=UTF-8,%3csvg xmlns=\'http://www.w3.org/2000/svg\' viewBox=\'0 0 400 400\'%3e%3cdefs%3e%3cstyle%3e.cls-1%7bfill:%23e74c3c;font-family:Arial-Black,Arial;font-size:48px;font-weight:800;%7d.cls-2%7bfill:none;stroke:%2334495e;stroke-width:20;%7d.cls-3%7bfill:%2327ae60;%7d.cls-4%7bfill:%233498db;%7d.cls-5%7bfill:%232c3e50;%7d%3c/style%3e%3c/defs%3e%3ccircle class=\'cls-2\' cx=\'200\' cy=\'200\' r=\'180\'/%3e%3cpath class=\'cls-3\' d=\'M120,250 Q150,200 180,250 Q210,200 240,250 L260,270 Q200,320 140,270 Z\'/%3e%3cpath class=\'cls-4\' d=\'M160,250 Q190,200 220,250 Q250,200 280,250 L300,270 Q240,320 180,270 Z\'/%3e%3cpath class=\'cls-5\' d=\'M200,250 Q230,200 260,250 Q290,200 320,250 L340,270 Q280,320 220,270 Z\'/%3e%3crect x=\'190\' y=\'120\' width=\'20\' height=\'80\' fill=\'%23666\'/%3e%3ccircle cx=\'200\' cy=\'110\' r=\'15\' fill=\'%23333\'/%3e%3ctext class=\'cls-1\' x=\'50\' y=\'80\' transform=\'rotate(-45 200 200)\'%3eAAYANSH%3c/text%3e%3ctext class=\'cls-1\' x=\'50\' y=\'320\' transform=\'rotate(-45 200 200)\'%3ePATH LAB%3c/text%3e%3c/svg%3e'); background-size: contain; background-repeat: no-repeat; background-position: center;">
                Aayansh Path Lab
            </div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="home" class="hero">
        <div class="floating-elements">
            <div class="floating-element"></div>
            <div class="floating-element"></div>
            <div class="floating-element"></div>
        </div>
        <div class="container hero-content">
            <h1>Aayansh Path Lab</h1>
            <p>Advanced Medical Diagnostics for Better Healthcare</p>
            <a href="https://wa.me/917607576610?text=Hello%20Aayansh%20Path%20Lab,%20I%20would%20like%20to%20book%20a%20test.%20Please%20provide%20me%20with%20more%20details." class="cta-button" target="_blank">Book Your Test Today</a>
        </div>
    </section>

    <section id="services" class="services">
        <div class="container">
            <h2 class="section-title">Our Services</h2>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">🩸</div>
                    <h3>Blood Tests</h3>
                    <p>Complete blood count, lipid profile, diabetes screening, and comprehensive metabolic panels with accurate results.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🦠</div>
                    <h3>Microbiology</h3>
                    <p>Culture and sensitivity testing, infection diagnosis, and antimicrobial susceptibility testing.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🧬</div>
                    <h3>Molecular Diagnostics</h3>
                    <p>DNA/RNA testing, genetic screening, and advanced molecular pathology services.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🔬</div>
                    <h3>Histopathology</h3>
                    <p>Tissue examination, biopsy analysis, and cancer screening with expert pathologist review.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🫀</div>
                    <h3>Cardiology Tests</h3>
                    <p>Cardiac markers, ECG, and comprehensive heart health assessment packages.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🏠</div>
                    <h3>Home Collection</h3>
                    <p>Convenient sample collection at your doorstep with trained phlebotomists and proper safety protocols.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="about" class="about">
        <div class="container">
            <div class="about-content">
                <div class="about-text">
                    <h2>About Aayansh Path Lab</h2>
                    <p>With state-of-the-art technology and a team of experienced pathologists, Aayansh Path Lab is committed to providing accurate, reliable, and timely diagnostic services.</p>
                    <p>We understand the importance of precise diagnosis in healthcare and strive to deliver results that healthcare providers can trust for better patient outcomes.</p>
                    <div class="stats">
                        <div class="stat-item">
                            <span class="stat-number">50,000+</span>
                            <span>Tests Performed</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">24/7</span>
                            <span>Emergency Services</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">99.9%</span>
                            <span>Accuracy Rate</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">10+</span>
                            <span>Years Experience</span>
                        </div>
                    </div>
                </div>
                <div class="about-image">
                    <div style="background: rgba(255,255,255,0.1); padding: 3rem; border-radius: 20px; text-align: center;">
                        <div style="font-size: 8rem; color: rgba(255,255,255,0.8);">🏥</div>
                        <h3>Advanced Equipment</h3>
                        <p>Latest diagnostic technology for precise results</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title" style="color: white;">Contact Us</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Get in Touch</h3>
                    <div class="contact-item">
                        <span>📍</span>
                        <div>
                            <strong>Address:</strong><br>
                            Abdul Wahab Complex, Sehuda<br>
                            Baghnagar Bazar, Sant Kabir Nagar, UP
                        </div>
                    </div>
                    <div class="contact-item">
                        <span>📞</span>
                        <div>
                            <strong>Phone:</strong><br>
                            +91 7607576610<br>
                            +91 7518209549<br>
                            +91 9580026125
                        </div>
                    </div>
                    <div class="contact-item">
                        <span>✉️</span>
                        <div>
                            <strong>Email:</strong><br>
                            aayansh.pathlab64@gmail.com
                        </div>
                    </div>
                    <div class="contact-item">
                        <span>🕒</span>
                        <div>
                            <strong>Hours:</strong><br>
                            Mon-Sat: 7:00 AM - 9:00 PM<br>
                            Sunday: 8:00 AM - 6:00 PM
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <h3>Book an Appointment</h3>
                    <p style="margin-bottom: 1.5rem; color: rgba(255,255,255,0.8);">Click the button below to book your appointment via WhatsApp:</p>
                    <a href="https://wa.me/917607576610?text=Hello%20Aayansh%20Path%20Lab,%20I%20would%20like%20to%20book%20an%20appointment.%20Please%20provide%20me%20with%20available%20slots%20and%20test%20packages." class="submit-btn" target="_blank" style="display: inline-block; text-decoration: none; text-align: center;">
                        📱 Book via WhatsApp
                    </a>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2025 Aayansh Path Lab. All rights reserved. | Committed to Excellence in Medical Diagnostics</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Form submission handler - removed as form is replaced with WhatsApp button

        // Add scroll effect to header
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(30, 60, 114, 0.95)';
                header.style.backdropFilter = 'blur(10px)';
            } else {
                header.style.background = 'linear-gradient(135deg, #1e3c72 0%, #2a5298 100%)';
                header.style.backdropFilter = 'none';
            }
        });

        // Animate service cards on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.service-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'all 0.6s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>
