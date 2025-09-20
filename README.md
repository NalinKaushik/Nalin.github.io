<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Nalin Kaushik - Computer Science Graduate | AI/ML Enthusiast | Full-Stack Developer">
    <meta name="author" content="Nalin Kaushik">
    <title>Nalin Kaushik - Portfolio</title>
    <link rel="icon" type="image/x-icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>👨‍💻</text></svg>">
    <style>
        :root {
            --primary-color: #2563eb;
            --secondary-color: #1e40af;
            --accent-color: #3b82f6;
            --text-color: #1f2937;
            --text-light: #6b7280;
            --bg-color: #ffffff;
            --bg-light: #f9fafb;
            --border-color: #e5e7eb;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--bg-color);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: var(--bg-color);
            border-bottom: 1px solid var(--border-color);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
            background: rgba(255, 255, 255, 0.95);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: var(--text-color);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -4px;
            left: 0;
            background-color: var(--primary-color);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            color: white;
            padding: 120px 0 80px;
            text-align: center;
            position: relative;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent 49%, rgba(255,255,255,0.03) 50%, transparent 51%);
            background-size: 20px 20px;
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .hero .subtitle {
            font-size: 1.25rem;
            margin-bottom: 2rem;
            opacity: 0.95;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            display: inline-block;
            padding: 12px 24px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
        }

        .btn-primary {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .btn-primary:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
        }

        .btn-secondary {
            background: white;
            color: var(--primary-color);
        }

        .btn-secondary:hover {
            background: var(--bg-light);
            transform: translateY(-2px);
        }

        /* Sections */
        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            font-weight: 700;
            color: var(--text-color);
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary-color), var(--accent-color));
            border-radius: 2px;
        }

        /* About Section */
        .about {
            background: var(--bg-light);
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--text-light);
        }

        .about-text p {
            margin-bottom: 1.5rem;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .stat {
            text-align: center;
            padding: 1.5rem;
            background: white;
            border-radius: 12px;
            box-shadow: var(--shadow);
        }

        .stat-number {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary-color);
        }

        .stat-label {
            color: var(--text-light);
            font-size: 0.9rem;
            margin-top: 0.5rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
        }

        .skill-card {
            background: white;
            padding: 2rem;
            border-radius: 12px;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
        }

        .skill-card:hover {
            transform: translateY(-4px);
            box-shadow: var(--shadow-lg);
        }

        .skill-icon {
            width: 48px;
            height: 48px;
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1rem;
            color: white;
            font-weight: bold;
            font-size: 1.2rem;
        }

        .skill-card h3 {
            color: var(--text-color);
            margin-bottom: 0.5rem;
            font-size: 1.2rem;
        }

        .skill-card p {
            color: var(--text-light);
            font-size: 0.95rem;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: white;
            border-radius: 16px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            border: 1px solid var(--border-color);
        }

        .project-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-lg);
        }

        .project-header {
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            color: white;
            padding: 1.5rem;
        }

        .project-card h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .project-type {
            opacity: 0.9;
            font-size: 0.9rem;
        }

        .project-content {
            padding: 2rem;
        }

        .project-card p {
            color: var(--text-light);
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 2rem;
        }

        .tech-tag {
            background: var(--bg-light);
            color: var(--text-color);
            padding: 0.4rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
            border: 1px solid var(--border-color);
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .project-link {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 600;
            font-size: 0.9rem;
            transition: opacity 0.3s ease;
        }

        .project-link:hover {
            opacity: 0.7;
        }

        /* Experience Section */
        .experience {
            background: var(--bg-light);
        }

        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: var(--border-color);
            transform: translateX(-50%);
        }

        .timeline-item {
            position: relative;
            margin-bottom: 3rem;
            width: 50%;
        }

        .timeline-item:nth-child(even) {
            left: 50%;
            padding-left: 2rem;
        }

        .timeline-item:nth-child(odd) {
            padding-right: 2rem;
            text-align: right;
        }

        .timeline-content {
            background: white;
            padding: 2rem;
            border-radius: 12px;
            box-shadow: var(--shadow);
            position: relative;
        }

        .timeline-date {
            background: var(--primary-color);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            display: inline-block;
            margin-bottom: 1rem;
        }

        .timeline-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--text-color);
        }

        .timeline-company {
            color: var(--primary-color);
            font-weight: 600;
            margin-bottom: 1rem;
        }

        .timeline-description {
            color: var(--text-light);
            line-height: 1.6;
        }

        /* Contact Section */
        .contact {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            color: white;
            text-align: center;
        }

        .contact .section-title {
            color: white;
        }

        .contact .section-title::after {
            background: rgba(255, 255, 255, 0.3);
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .contact-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 2rem;
            border-radius: 12px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .contact-card:hover {
            background: rgba(255, 255, 255, 0.15);
            transform: translateY(-4px);
        }

        .contact-icon {
            font-size: 2rem;
            margin-bottom: 1rem;
        }

        .contact-card h3 {
            margin-bottom: 0.5rem;
            font-size: 1.1rem;
        }

        .contact-card a {
            color: white;
            text-decoration: none;
            font-weight: 500;
        }

        /* Footer */
        footer {
            background: var(--text-color);
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .social-links {
            display: flex;
            gap: 1rem;
        }

        .social-link {
            color: white;
            text-decoration: none;
            padding: 0.5rem;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .social-link:hover {
            background: var(--primary-color);
            transform: translateY(-2px);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero .subtitle {
                font-size: 1.1rem;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .about-grid {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .stats {
                grid-template-columns: 1fr;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .timeline::before {
                left: 20px;
            }

            .timeline-item {
                width: 100%;
                left: 0 !important;
                padding-left: 3rem !important;
                padding-right: 0 !important;
                text-align: left !important;
            }

            .contact-grid {
                grid-template-columns: 1fr;
            }

            .footer-content {
                flex-direction: column;
                text-align: center;
            }
        }

        @media (max-width: 480px) {
            .container {
                padding: 0 15px;
            }

            section {
                padding: 60px 0;
            }

            .section-title {
                font-size: 2rem;
            }

            .skill-card, .project-content {
                padding: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <div class="logo">NK</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="home" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Nalin Kaushik</h1>
                <p class="subtitle">Computer Science Graduate • AI/ML Enthusiast • Full-Stack Developer</p>
                <div class="hero-buttons">
                    <a href="#projects" class="btn btn-primary">View My Work</a>
                    <a href="#contact" class="btn btn-secondary">Get In Touch</a>
                </div>
            </div>
        </div>
    </section>

    <section id="about" class="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-grid">
                <div class="about-text">
                    <p>I'm a passionate Computer Science graduate specializing in Information Security from Chandigarh University, with a strong foundation in AI, machine learning, and full-stack development.</p>
                    <p>Recently completed intensive training at Celebal Technologies, where I honed my skills in enterprise-level software development practices.</p>
                    <p>I'm actively seeking opportunities to contribute to innovative teams in AI, data science, machine learning, and software development roles.</p>
                    
                    <div class="stats">
                        <div class="stat">
                            <div class="stat-number">2+</div>
                            <div class="stat-label">Projects</div>
                        </div>
                        <div class="stat">
                            <div class="stat-number">1</div>
                            <div class="stat-label">Certification</div>
                        </div>
                    </div>
                </div>
                <div class="skills-grid">
                    <div class="skill-card">
                        <div class="skill-icon">💻</div>
                        <h3>Programming</h3>
                        <p>Python, JavaScript, C/C++</p>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">🌐</div>
                        <h3>Web Development</h3>
                        <p>React.js, Node.js, HTML5, CSS, Tailwind CSS</p>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">🗄️</div>
                        <h3>Databases</h3>
                        <p>MongoDB, SQL</p>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">🤖</div>
                        <h3>AI/ML</h3>
                        <p>Scikit-learn, Data Analysis, Statistical Modeling</p>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">🔒</div>
                        <h3>Security</h3>
                        <p>Cybersecurity, Web Security, Information Security</p>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">⚙️</div>
                        <h3>Tools & Others</h3>
                        <p>Git/GitHub, Flutter, Data Structures & Algorithms</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="projects" class="projects">
        <div class="container">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-header">
                        <h3>Python Online Compiler</h3>
                        <div class="project-type">Full-Stack Web Application</div>
                    </div>
                    <div class="project-content">
                        <p>A sophisticated web-based Python compiler featuring real-time code execution, syntax highlighting, and secure server-side processing with an intuitive user interface.</p>
                        <div class="tech-stack">
                            <span class="tech-tag">Node.js</span>
                            <span class="tech-tag">Express.js</span>
                            <span class="tech-tag">Tailwind CSS</span>
                            <span class="tech-tag">CodeMirror</span>
                            <span class="tech-tag">JavaScript</span>
                        </div>
                        <div class="project-links">
                            <a href="https://github.com/NalinKaushik/" class="project-link">View Code →</a>
                            <a href="https://github.com/NalinKaushik/" class="project-link">Live Demo →</a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">
                        <h3>House Price Prediction</h3>
                        <div class="project-type">Machine Learning Model</div>
                    </div>
                    <div class="project-content">
                        <p>Advanced machine learning model predicting house prices with 85% accuracy using regression algorithms, comprehensive data preprocessing, and feature engineering techniques.</p>
                        <div class="tech-stack">
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">Scikit-learn</span>
                            <span class="tech-tag">Pandas</span>
                            <span class="tech-tag">Matplotlib</span>
                            <span class="tech-tag">NumPy</span>
                        </div>
                        <div class="project-links">
                            <a href="https://github.com/NalinKaushik/" class="project-link">View Code →</a>
                            <a href="https://github.com/NalinKaushik/" class="project-link">Documentation →</a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">
                        <h3>Upcoming Projects</h3>
                        <div class="project-type">AI & Cybersecurity Focus</div>
                    </div>
                    <div class="project-content">
                        <p>Currently developing innovative projects in AI/ML applications and cybersecurity tools. These projects will demonstrate advanced algorithms and security implementations.</p>
                        <div class="tech-stack">
                            <span class="tech-tag">AI/ML</span>
                            <span class="tech-tag">TensorFlow</span>
                            <span class="tech-tag">Cybersecurity</span>
                            <span class="tech-tag">Python</span>
                        </div>
                        <div class="project-links">
                            <a href="https://github.com/NalinKaushik/" class="project-link">GitHub Profile →</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="experience" class="experience">
        <div class="container">
            <h2 class="section-title">Experience & Education</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="timeline-date">Jan 2025 - Feb 2025</span>
                        <h3 class="timeline-title">Software Developer Training</h3>
                        <div class="timeline-company">Celebal Technologies</div>
                        <p class="timeline-description">
                            Completed intensive software development training program focusing on enterprise-level development practices, collaborative coding, and real-world application development.
                        </p>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="timeline-date">2025</span>
                        <h3 class="timeline-title">Oracle Cloud Infrastructure Certified</h3>
                        <div class="timeline-company">Oracle Corporation</div>
                        <p class="timeline-description">
                            Achieved Oracle Cloud Infrastructure 2025 Foundations Associate certification (1Z0-1085-25), demonstrating proficiency in cloud computing concepts and Oracle's cloud services.
                        </p>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="timeline-date">2021 - 2025</span>
                        <h3 class="timeline-title">Bachelor's of Engineering (CSE)</h3>
                        <div class="timeline-company">Chandigarh University (In Association with IBM)</div>
                        <p class="timeline-description">
                            Specialized in Computer Science with Information Security. Key coursework: Data Structures & Algorithms, Database Management, Computer Networks, Cybersecurity, Statistics/Probability, and Python Programming.
                        </p>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="timeline-date">Achievement</span>
                        <h3 class="timeline-title">Gold Medalist</h3>
                        <div class="timeline-company">National Softball Championship</div>
                        <p class="timeline-description">
                            Demonstrated excellence in competitive sports, showcasing teamwork, leadership, and dedication alongside academic pursuits.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Let's Connect</h2>
            <p>I'm actively seeking opportunities in AI, Machine Learning, Data Science, and Software Development. Let's discuss how we can create innovative solutions together!</p>
            
            <div class="contact-grid">
                <div class="contact-card">
                    <div class="contact-icon">📧</div>
                    <h3>Email</h3>
                    <a href="mailto:nalinkaushik4184@gmail.com">nalinkaushik4184@gmail.com</a>
                </div>
                <div class="contact-card">
                    <div class="contact-icon">💼</div>
                    <h3>LinkedIn</h3>
                    <a href="https://www.linkedin.com/in/nalin-kaushik-245a52230/" target="_blank">Connect with me</a>
                </div>
                <div class="contact-card">
                    <div class="contact-icon">💻</div>
                    <h3>GitHub</h3>
                    <a href="https://github.com/NalinKaushik/" target="_blank">View my repositories</a>
                </div>
                <div class="contact-card">
                    <div class="contact-icon">📍</div>
                    <h3>Location</h3>
                    <p>Jodhpur, Rajasthan, India</p>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <p>&copy; 2025 Nalin Kaushik. All rights reserved.</p>
                <div class="social-links">
                    <a href="mailto:nalinkaushik4184@gmail.com" class="social-link" title="Email">📧</a>
                    <a href="https://www.linkedin.com/in/nalin-kaushik-245a52230/" class="social-link" title="LinkedIn" target="_blank">💼</a>
                    <a href="https://github.com/NalinKaushik/" class="social-link" title="GitHub" target="_blank">💻</a>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    const headerHeight = document.querySelector('header').offsetHeight;
                    const targetPosition = target.offsetTop - headerHeight;
                    window.scrollTo({
                        top: targetPosition,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Header background on scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 50) {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
                header.style.boxShadow = '0 2px 10px rgba(0, 0, 0, 0.1)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
                header.style.boxShadow = 'none';
            }
        });

        // Simple animation on scroll
        function animateOnScroll() {
            const elements = document.querySelectorAll('.skill-card, .project-card, .timeline-item, .contact-card');
            elements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;
                if (elementTop < window.innerHeight - elementVisible) {
                    element.style.opacity = '1';
                    element.style.transform = 'translateY(0)';
                }
            });
        }

        // Initialize animation styles
        document.quer
