<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mugabe Yunusu - Full Stack Developer Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #4361ee;
            --primary-dark: #3a0ca3;
            --secondary: #f72585;
            --accent: #4cc9f0;
            --dark: #14213d;
            --light: #f8f9fa;
            --gray: #6c757d;
            --white: #ffffff;
            --success: #2ecc71;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Navigation */
        header {
            background-color: var(--white);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1.5rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo i {
            color: var(--secondary);
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            position: relative;
            padding: 0.5rem 0;
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--primary);
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--dark);
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 8rem 2rem 4rem;
            background: linear-gradient(135deg, rgba(67, 97, 238, 0.1) 0%, rgba(248, 249, 250, 1) 100%);
        }

        .hero-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            line-height: 1.2;
            color: var(--dark);
        }

        .hero-content h1 span {
            color: var(--primary);
        }

        .hero-content p {
            font-size: 1.2rem;
            color: var(--gray);
            margin-bottom: 2rem;
            max-width: 600px;
        }

        .contact-info {
            margin-top: 2rem;
        }

        .contact-info div {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1rem;
            color: var(--dark);
        }

        .contact-info i {
            color: var(--primary);
            width: 24px;
            text-align: center;
        }

        .hero-image {
            position: relative;
            display: flex;
            justify-content: center;
        }

        .hero-image img {
            width: 100%;
            max-width: 400px;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
            z-index: 2;
        }

        .hero-image::before {
            content: '';
            position: absolute;
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            opacity: 0.2;
            z-index: 1;
            top: -50px;
            right: -50px;
            animation: float 6s ease-in-out infinite;
        }

        .hero-image::after {
            content: '';
            position: absolute;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--secondary), var(--accent));
            opacity: 0.2;
            z-index: 1;
            bottom: -50px;
            left: -50px;
            animation: float 8s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        /* Projects Section */
        .projects {
            padding: 6rem 2rem;
            background-color: var(--white);
        }

        .section-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--dark);
            position: relative;
            display: inline-block;
            padding-bottom: 1rem;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 2px;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2.5rem;
        }

        .project-card {
            background-color: var(--white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid rgba(0, 0, 0, 0.1);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .project-image {
            height: 200px;
            overflow: hidden;
        }

        .project-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .project-card:hover .project-image img {
            transform: scale(1.1);
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-content h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary-dark);
        }

        .project-meta {
            display: flex;
            gap: 1rem;
            margin-bottom: 1rem;
            font-size: 0.9rem;
            color: var(--gray);
        }

        .project-meta span {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .project-content p {
            color: var(--gray);
            margin-bottom: 1.5rem;
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .tech-tag {
            background-color: var(--light);
            color: var(--primary);
            padding: 0.3rem 0.8rem;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 500;
            border: 1px solid rgba(67, 97, 238, 0.2);
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .project-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.5rem 1.2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
        }

        .primary-link {
            background-color: var(--primary);
            color: var(--white);
        }

        .primary-link:hover {
            background-color: var(--primary-dark);
        }

        .secondary-link {
            background-color: transparent;
            color: var(--primary);
            border: 1px solid var(--primary);
        }

        .secondary-link:hover {
            background-color: rgba(67, 97, 238, 0.1);
        }

        /* Contact Section */
        .contact {
            padding: 6rem 2rem;
            background: linear-gradient(135deg, rgba(67, 97, 238, 0.1) 0%, rgba(248, 249, 250, 1) 100%);
        }

        .contact-container {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1.5rem;
            margin-top: 3rem;
        }

        .contact-link {
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            padding: 0.8rem 1.8rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            background-color: var(--white);
            color: var(--primary);
            box-shadow: var(--shadow);
        }

        .contact-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            color: var(--primary-dark);
        }

        /* Footer */
        footer {
            background-color: var(--dark);
            color: var(--white);
            padding: 2rem;
            text-align: center;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 1rem;
        }

        .social-links {
            display: flex;
            gap: 1.5rem;
        }

        .social-link {
            color: var(--white);
            font-size: 1.2rem;
            transition: var(--transition);
        }

        .social-link:hover {
            color: var(--accent);
        }

        .copyright {
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 1024px) {
            .hero-container {
                gap: 2rem;
            }

            .hero-content h1 {
                font-size: 3rem;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero-container {
                grid-template-columns: 1fr;
                text-align: center;
                gap: 3rem;
            }

            .hero-content {
                order: 2;
            }

            .hero-image {
                order: 1;
            }

            .hero-content p {
                margin-left: auto;
                margin-right: auto;
            }

            .contact-info {
                justify-content: center;
            }

            .hero-image::before, 
            .hero-image::after {
                display: none;
            }
        }

        @media (max-width: 576px) {
            .hero {
                padding-top: 6rem;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .section-title h2 {
                font-size: 2rem;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .project-links {
                flex-direction: column;
            }

            .project-link {
                justify-content: center;
            }

            .contact-links {
                flex-direction: column;
                align-items: center;
            }

            .contact-link {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <header>
        <div class="nav-container">
            <div class="logo">
                <i class="fas fa-code"></i>
                <span>Mugabe Yunusu</span>
            </div>
            <nav class="nav-links">
                <a href="#home">Home</a>
                <a href="#projects">Projects</a>
                <a href="#contact">Contact</a>
            </nav>
            <button class="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </button>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-container">
            <div class="hero-content">
                <h1>Full Stack <span>Developer</span></h1>
                <p>I build innovative digital solutions that solve real-world problems with clean, efficient code and user-centric design.</p>
                
                <div class="contact-info">
                    <div>
                        <i class="fas fa-map-marker-alt"></i>
                        <span>Macarenhas street, Beau Bassin, Mauritius</span>
                    </div>
                    <div>
                        <i class="fas fa-phone"></i>
                        <span>(230) 5473 5538</span>
                    </div>
                    <div>
                        <i class="fas fa-envelope"></i>
                        <span>mugabeyunusu@gmail.com</span>
                    </div>
                    <div>
                        <i class="fab fa-linkedin"></i>
                        <span>linkedin.com/in/Mugabe-yunusu</span>
                    </div>
                    <div>
                        <i class="fab fa-github"></i>
                        <span>github.com/mugabeyu</span>
                    </div>
                </div>
            </div>
            <div class="hero-image">
                <!-- Replace with your actual photo -->
                <img src="images/donor.jpeg" alt="Mugabe Yunusu">
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <div class="section-container">
            <div class="section-title">
                <h2>My Projects</h2>
            </div>
            
            <div class="projects-grid">
                <!-- Mauritius Explorer Project -->
                <div class="project-card">
                    <div class="project-image">
                        <img src="https://images.unsplash.com/photo-1520250497591-112f2f40a3f4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Mauritius Explorer">
                    </div>
                    <div class="project-content">
                        <h3>Mauritius Explorer</h3>
                        <div class="project-meta">
                            <span><i class="fas fa-calendar-alt"></i> March 2025 - July 2025</span>
                            <span><i class="fas fa-users"></i> Team Project</span>
                        </div>
                        <p>A comprehensive tourism progreesive web application serving as a local guide and treasure hunt map for tourists, students, and locals with QR code scanning functionality.</p>
                        
                        <div class="tech-stack">
                            <span class="tech-tag">PHP</span>
                            <span class="tech-tag">MariaDB</span>
                            <span class="tech-tag">OpenAPI</span>
                            <span class="tech-tag">Swagger</span>
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">Google Maps API</span>
                            <span class="tech-tag">QR Codes</span>
                        </div>
                        
                        <div class="project-links">
                            <!-- <a href="#" class="project-link primary-link">
                                <i class="fas fa-external-link-alt"></i> Live Demo
                            </a> -->
                            <a href="#" class="project-link secondary-link">
                                <i class="fab fa-github"></i> View Code
                            </a>
                        </div>
                    </div>
                </div>
                
                <!-- Autism School System -->
                <div class="project-card">
                    <div class="project-image">
                        <img src="https://images.unsplash.com/photo-1588072432836-e10032774350?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1472&q=80" alt="Learning System for Autism School">
                    </div>
                    <div class="project-content">
                        <h3>Learning System for Autism School</h3>
                        <div class="project-meta">
                            <span><i class="fas fa-calendar-alt"></i> August 2024</span>
                            <span><i class="fas fa-user"></i> Individual Project</span>
                        </div>
                        <p>Desktop application designed to support special education needs with customized learning modules and progress tracking.</p>
                        
                        <div class="tech-stack">
                            <span class="tech-tag">Java</span>
                            <span class="tech-tag">NetBeans</span>
                            <span class="tech-tag">Derby DB</span>
                            <span class="tech-tag">Swing</span>
                        </div>
                        
                        <div class="project-links">
                            <!-- <a href="#" class="project-link primary-link">
                                <i class="fas fa-external-link-alt"></i> View Project
                            </a> -->
                            <a href="#" class="project-link secondary-link">
                                <i class="fab fa-github"></i> Source Code
                            </a>
                        </div>
                    </div>
                </div>
                
                <!-- Cinema Ticketing System -->
                <div class="project-card">
                    <div class="project-image">
                        <img src="https://images.unsplash.com/photo-1517604931442-7e0c8ed2963c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Cinema Ticketing System">
                    </div>
                    <div class="project-content">
                        <h3>Cinema Ticketing System</h3>
                        <div class="project-meta">
                            <span><i class="fas fa-calendar-alt"></i> July 2024</span>
                            <span><i class="fas fa-user"></i> Individual Project</span>
                        </div>
                        <p>A desktop application for managing cinema ticket sales with seat selection and payment processing simulation.</p>
                        
                        <div class="tech-stack">
                            <span class="tech-tag">Java</span>
                            <span class="tech-tag">JFrame</span>
                            <span class="tech-tag">Arrays</span>
                            <span class="tech-tag">GUI</span>
                        </div>
                        
                        <div class="project-links">
                            <!-- <a href="#" class="project-link primary-link">
                                <i class="fas fa-external-link-alt"></i> Demo
                            </a> -->
                            <a href="#" class="project-link secondary-link">
                                <i class="fab fa-github"></i> Code
                            </a>
                        </div>
                    </div>
                </div>
                
                <!-- Movie Website -->
                <div class="project-card">
                    <div class="project-image">
                        <img src="https://images.unsplash.com/photo-1489599849927-2ee91cede3ba?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Movie Website">
                    </div>
                    <div class="project-content">
                        <h3>Movie Database Website</h3>
                        <div class="project-meta">
                            <span><i class="fas fa-calendar-alt"></i> June 2024</span>
                            <span><i class="fas fa-user"></i> Individual Project</span>
                        </div>
                        <p>A responsive website featuring movie listings, user ratings, and personalized recommendations.</p>
                        
                        <div class="tech-stack">
                            <span class="tech-tag">C#</span>
                            <span class="tech-tag">ASP.NET</span>
                            <span class="tech-tag">SQL Server</span>
                            <span class="tech-tag">Bootstrap</span>
                        </div>
                        
                        <div class="project-links">
                            <!-- <a href="#" class="project-link primary-link">
                                <i class="fas fa-external-link-alt"></i> Visit Site
                            </a> -->
                            <a href="#" class="project-link secondary-link">
                                <i class="fab fa-github"></i> Repository
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="contact-container">
            <div class="section-title">
                <h2>Get In Touch</h2>
            </div>
            <p></p>
            
            <div class="contact-links">
                <a href="mailto:mugabeyunusu@gmail.com" class="contact-link">
                    <i class="fas fa-envelope"></i> Email Me
                </a>
                <a href="tel:23054735538" class="contact-link">
                    <i class="fas fa-phone"></i> Call Me
                </a>
                <a href="https://www.linkedin.com/in/Mugabe-yunusu" target="_blank" class="contact-link">
                    <i class="fab fa-linkedin"></i> LinkedIn
                </a>
                <a href="https://github.com/mugabeyu" target="_blank" class="contact-link">
                    <i class="fab fa-github"></i> GitHub
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="social-links">
                <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
                <a href="https://www.linkedin.com/in/Mugabe-yunusu" target="_blank" class="social-link"><i class="fab fa-linkedin"></i></a>
                <a href="https://github.com/mugabeyu" target="_blank" class="social-link"><i class="fab fa-github"></i></a>
            </div>
            <p class="copyright">&copy; <span id="year"></span> Mugabe Yunusu. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Update copyright year
        document.getElementById('year').textContent = new Date().getFullYear();

        // Mobile menu toggle
        const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
        const navLinks = document.querySelector('.nav-links');
        
        mobileMenuBtn.addEventListener('click', () => {
            navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
        });

        // Close mobile menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                if (window.innerWidth <= 768) {
                    navLinks.style.display = 'none';
                }
            });
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 50) {
                header.style.padding = '1rem 2rem';
                header.style.boxShadow = '0 4px 10px rgba(0, 0, 0, 0.1)';
            } else {
                header.style.padding = '1.5rem 2rem';
                header.style.boxShadow = '0 4px 6px rgba(0, 0, 0, 0.1)';
            }
        });

        // Responsive adjustments
        function handleResize() {
            if (window.innerWidth > 768) {
                navLinks.style.display = 'flex';
            } else {
                navLinks.style.display = 'none';
            }
        }

        window.addEventListener('resize', handleResize);
        handleResize();
    </script>
</body>
</html>
