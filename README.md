<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nalin Kaushik - Portfolio</title>
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
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: opacity 0.3s ease;
        }

        .nav-links a:hover {
            opacity: 0.8;
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
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><polygon fill="%23ffffff08" points="0,1000 1000,0 1000,1000"/></svg>');
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            animation: slideInUp 1s ease-out;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            animation: slideInUp 1s ease-out 0.2s both;
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .cta-button {
            display: inline-block;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            padding: 15px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            animation: slideInUp 1s ease-out 0.4s both;
        }

        .cta-button:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        /* Sections */
        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 3px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        /* About Section */
        .about {
            background: #f8f9fa;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .skill-category {
            background: white;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
        }

        .skill-category h3 {
            color: #667eea;
            margin-bottom: 0.5rem;
            font-size: 1.1rem;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            position: relative;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .project-content {
            padding: 2rem;
        }

        .project-card h3 {
            color: #333;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .project-card p {
            color: #666;
            margin-bottom: 1.5rem;
        }

        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .tech-tag {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .project-link {
            color: #667eea;
            text-decoration: none;
            font-weight: bold;
            transition: opacity 0.3s ease;
        }

        .project-link:hover {
            opacity: 0.7;
        }

        /* Experience Section */
        .experience {
            background: #f8f9fa;
        }

        .experience-item {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            position: relative;
            margin-bottom: 2rem;
        }

        .experience-item::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 4px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 0 4px 4px 0;
        }

        .experience-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 1rem;
        }

        .experience-title {
            font-size: 1.3rem;
            color: #333;
            margin-bottom: 0.3rem;
        }

        .experience-company {
            color: #667eea;
            font-weight: bold;
        }

        .experience-date {
            color: #666;
            font-weight: 500;
            background: #f0f2f5;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.9rem;
        }

        /* Contact Section */
        .contact {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }

        .contact-link {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            padding: 15px 25px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .contact-link:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
        }

        /* Footer */
        footer {
            background: #333;
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .experience-header {
                flex-direction: column;
                gap: 0.5rem;
            }

            .contact-links {
                flex-direction: column;
                align-items: center;
                gap: 1rem;
            }
        }

        /* Scroll animations */
        .animate-on-scroll {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease-out;
        }

        .animate-on-scroll.animate {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <div class="logo">Nalin Kaushik</div>
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
                <p>Computer Science Graduate | AI/ML Enthusiast | Full-Stack Developer</p>
                <a href="#contact" class="cta-button">Get In Touch</a>
            </div>
        </div>
    </section>

    <section id="about" class="about">
        <div class="container">
            <h2 class="section-title animate-on-scroll">About Me</h2>
            <div class="about-content animate-on-scroll">
                <div class="about-text">
                    <p>I'm an enthusiastic Computer Science graduate with a specialization in Information Security from Chandigarh University. My passion lies in the intersection of AI, machine learning, and software development.</p>
                    <br>
                    <p>With hands-on experience in full-stack development and machine learning algorithms, I'm committed to leveraging technology to create innovative solutions. I recently completed training at Celebal Technologies and am actively seeking opportunities in AI, data science, and software development.</p>
                </div>
                <div class="skills-grid">
                    <div class="skill-category">
                        <h3>Programming</h3>
                        <p>Python, JavaScript, C/C++</p>
                    </div>
                    <div class="skill-category">
                        <h3>Web Development</h3>
                        <p>React.js, Node.js, HTML5, CSS, Tailwind CSS</p>
                    </div>
                    <div class="skill-category">
                        <h3>Databases</h3>
                        <p>MongoDB, SQL</p>
                    </div>
                    <div class="skill-category">
                        <h3>Machine Learning</h3>
                        <p>Scikit-learn, Data Analysis, Statistical Modeling</p>
                    </div>
                    <div class="skill-category">
                        <h3>Other Technologies</h3>
                        <p>Flutter, Git/GitHub, Web Security</p>
                    </div>
                    <div class="skill-category">
                        <h3>Coursework</h3>
                        <p>Data Structures, Algorithms, Cybersecurity</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="projects" class="projects">
        <div class="container">
            <h2 class="section-title animate-on-scroll">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card animate-on-scroll">
                    <div class="project-content">
                        <h3>Python Online Compiler</h3>
                        <p>A web-based Python compiler with real-time code execution, featuring a responsive frontend and secure server-side processing.</p>
                        <div class="tech-tags">
                            <span class="tech-tag">Node.js</span>
                            <span class="tech-tag">Express.js</span>
                            <span class="tech-tag">Tailwind CSS</span>
                            <span class="tech-tag">CodeMirror</span>
                        </div>
                        <div class="project-links">
                            <a href="https://github.com/NalinKaushik/" class="project-link">View Code →</a>
                        </div>
                    </div>
                </div>

                <div class="project-card animate-on-scroll">
                    <div class="project-content">
                        <h3>House Price Prediction Model</h3>
                        <p>Machine learning model predicting house prices using regression algorithms with 85% accuracy through comprehensive data preprocessing and feature engineering.</p>
                        <div class="tech-tags">
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">Scikit-learn</span>
                            <span class="tech-tag">Pandas</span>
                            <span class="tech-tag">Matplotlib</span>
                        </div>
                        <div class="project-links">
                            <a href="https://github.com/NalinKaushik/" class="project-link">View Code →</a>
                        </div>
                    </div>
                </div>

                <div class="project-card animate-on-scroll">
                    <div class="project-content">
                        <h3>More Projects Coming Soon</h3>
                        <p>Currently working on exciting new projects involving AI, cybersecurity tools, and full-stack applications. Stay tuned for updates!</p>
                        <div class="tech-tags">
                            <span class="tech-tag">AI/ML</span>
                            <span class="tech-tag">Cybersecurity</span>
                            <span class="tech-tag">Full-Stack</span>
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
            <h2 class="section-title animate-on-scroll">Experience</h2>
            <div class="experience-item animate-on-scroll">
                <div class="experience-header">
                    <div>
                        <div class="experience-title">Software Developer</div>
                        <div class="experience-company">Celebal Technologies</div>
                    </div>
                    <div class="experience-date">Jan 2025 - Feb 2025</div>
                </div>
                <p>Participated in intensive software development training program, gaining hands-on experience in enterprise-level development practices and collaborating with development teams on real-world projects and applications.</p>
            </div>

            <div class="experience-item animate-on-scroll">
                <div class="experience-header">
                    <div>
                        <div class="experience-title">Bachelor's of Engineering (CSE)</div>
                        <div class="experience-company">Chandigarh University (In Association with IBM)</div>
                    </div>
                    <div class="experience-date">2021 - 2025</div>
                </div>
                <p>Specialized in Information Security with comprehensive coursework in Data Structures, Algorithms, Database Management, Computer Networks, Cybersecurity, and Machine Learning fundamentals.</p>
            </div>

            <div class="experience-item animate-on-scroll">
                <div class="experience-header">
                    <div>
                        <div class="experience-title">Oracle Cloud Infrastructure Certified</div>
                        <div class="experience-company">Oracle</div>
                    </div>
                    <div class="experience-date">2025</div>
                </div>
                <p>Achieved Oracle Cloud Infrastructure 2025 Foundations Associate certification, demonstrating proficiency in cloud computing concepts and Oracle's cloud services.</p>
            </div>
        </div>
    </section>

    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Let's Work Together</h2>
            <p>I'm actively seeking opportunities in AI, Machine Learning, Data Science, and Software Development. Let's connect and discuss how we can create something amazing together!</p>
            <div class="contact-links">
                <a href="mailto:nalinkaushik4184@gmail.com" class="contact-link">Email Me</a>
                <a href="https://www.linkedin.com/in/nalin-kaushik-245a52230/" class="contact-link">LinkedIn</a>
                <a href="https://github.com/NalinKaushik/" class="contact-link">GitHub</a>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2025 Nalin Kaushik. All rights reserved. | Gold Medalist - National Softball Championship</p>
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

        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animate');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.animate-on-scroll').forEach(el => {
            observer.observe(el);
        });

        // Header background on scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(102, 126, 234, 0.95)';
            } else {
                header.style.background = 'linear-gradient(135deg, #667eea 0%, #764ba2 100%)';
            }
        });

        // Dynamic typing effect for hero subtitle
        function typeWriter(element, text, speed = 50) {
            let i = 0;
            element.innerHTML = '';
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                }
            }
            type();
        }

        // Initialize typing effect after page load
        window.addEventListener('load', function() {
            setTimeout(() => {
                const subtitle = document.querySelector('.hero p');
                const originalText = subtitle.textContent;
                typeWriter(subtitle, originalText, 30);
            }, 1500);
        });
    </script>
</body>
</html>
