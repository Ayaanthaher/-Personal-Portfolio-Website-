<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ayaan Thaher N - Developer Portfolio</title>
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

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: linear-gradient(135deg, #ea580c 0%, #dc2626 100%);
            z-index: 1000;
            padding: 1rem 2rem;
            transition: all 0.3s ease;
        }

        .navbar.scrolled {
            background: rgba(234, 88, 12, 0.95);
            backdrop-filter: blur(10px);
        }

        .nav-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: white;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s ease;
            font-weight: 500;
        }

        .nav-links a:hover {
            color: #fbbf24;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #ea580c 0%, #dc2626 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.05'%3E%3Ccircle cx='30' cy='30' r='2'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: translateX(-50%) translateY(-50%) rotate(0deg); }
            100% { transform: translateX(-50%) translateY(-50%) rotate(360deg); }
        }

        .hero-content {
            position: relative;
            z-index: 1;
            animation: fadeInUp 1s ease;
        }

        .profile-img {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            border: 5px solid rgba(255, 255, 255, 0.3);
            margin-bottom: 2rem;
            animation: profilePulse 2s infinite;
            margin: 0 auto 2rem;
            background: linear-gradient(45deg, #fbbf24, #f59e0b);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            font-weight: bold;
            color: white;
        }

        @keyframes profilePulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #fbbf24, #f59e0b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto 2rem;
            opacity: 0.9;
        }

        .cta-button {
            background: linear-gradient(45deg, #f59e0b, #fbbf24);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 30px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: transform 0.3s ease;
            text-decoration: none;
            display: inline-block;
            font-weight: 600;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(245, 158, 11, 0.3);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Skills Section */
        .skills {
            background: linear-gradient(135deg, #fffbeb 0%, #fef3c7 100%);
            padding: 5rem 2rem;
            color: #1f2937;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            position: relative;
            color: #ea580c;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: linear-gradient(45deg, #f59e0b, #fbbf24);
            margin: 1rem auto;
            border-radius: 2px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .skill-card {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease;
            border: 1px solid rgba(234, 88, 12, 0.2);
            box-shadow: 0 4px 15px rgba(234, 88, 12, 0.1);
        }

        .skill-card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 8px 25px rgba(234, 88, 12, 0.2);
        }

        .skill-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ea580c, #dc2626);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .skill-card h3 {
            color: #ea580c;
            margin-bottom: 1rem;
        }

        /* Projects Section */
        .projects {
            background: linear-gradient(135deg, #fff7ed 0%, #fecaca 100%);
            padding: 5rem 2rem;
        }

        .projects .section-title {
            color: #dc2626;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 3rem;
            margin-top: 3rem;
        }

        .project-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 30px rgba(234, 88, 12, 0.1);
            transition: transform 0.3s ease;
            border: 1px solid rgba(234, 88, 12, 0.1);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 50px rgba(234, 88, 12, 0.15);
        }

        .project-image {
            height: 200px;
            background: linear-gradient(45deg, #ea580c, #dc2626);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        .project-content {
            padding: 2rem;
        }

        .project-card h3 {
            color: #dc2626;
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }

        .project-card p {
            color: #666;
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .tech-tag {
            background: linear-gradient(45deg, #f59e0b, #fbbf24);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .project-link {
            background: linear-gradient(45deg, #ea580c, #dc2626);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            text-decoration: none;
            transition: transform 0.3s ease;
            font-size: 0.9rem;
            font-weight: 500;
        }

        .project-link:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(234, 88, 12, 0.3);
        }

        /* Contact Section */
        .contact {
            background: linear-gradient(135deg, #fffbeb 0%, #fed7aa 100%);
            padding: 5rem 2rem;
            color: #1f2937;
        }

        .contact .section-title {
            color: #ea580c;
        }

        .contact-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .contact-form {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px);
            padding: 3rem;
            border-radius: 20px;
            border: 1px solid rgba(234, 88, 12, 0.2);
            box-shadow: 0 10px 30px rgba(234, 88, 12, 0.1);
        }

        .form-group {
            margin-bottom: 2rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: #ea580c;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid rgba(234, 88, 12, 0.2);
            border-radius: 10px;
            background: rgba(255, 255, 255, 0.9);
            color: #1f2937;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #ea580c;
        }

        .form-group input::placeholder,
        .form-group textarea::placeholder {
            color: rgba(31, 41, 55, 0.5);
        }

        .submit-btn {
            background: linear-gradient(45deg, #ea580c, #dc2626);
            color: white;
            padding: 1rem 3rem;
            border: none;
            border-radius: 30px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: transform 0.3s ease;
            width: 100%;
            font-weight: 600;
        }

        .submit-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(234, 88, 12, 0.3);
        }

        .contact-info {
            text-align: center;
            margin-bottom: 3rem;
        }

        .contact-item {
            display: inline-block;
            margin: 0 1rem;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 10px;
            margin-bottom: 1rem;
            border: 1px solid rgba(234, 88, 12, 0.2);
            color: #ea580c;
            font-weight: 500;
        }

        /* Footer */
        .footer {
            background: linear-gradient(135deg, #991b1b 0%, #000000 100%);
            color: white;
            text-align: center;
            padding: 2rem;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .profile-img {
                width: 150px;
                height: 150px;
                font-size: 3rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .skills-grid,
            .projects-grid {
                grid-template-columns: 1fr;
            }

            .contact-form {
                padding: 2rem;
            }

            .contact-item {
                display: block;
                margin: 1rem 0;
            }
        }

        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .fade-in.appear {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar" id="navbar">
        <div class="nav-content">
            <div class="logo">Ayaan Thaher N</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <div class="profile-img">AT</div>
            <h1>Ayaan Thaher N</h1>
            <p>Passionate Full-Stack Developer & Computer Science Student at SRM University. I create innovative solutions using modern technologies and have experience in web development, database management, and AI/ML integration.</p>
            <a href="#contact" class="cta-button">Get In Touch</a>
        </div>
    </section>

    <!-- Skills Section -->
    <section class="skills" id="skills">
        <div class="container">
            <h2 class="section-title fade-in">Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill-card fade-in">
                    <div class="skill-icon">🐍</div>
                    <h3>Python</h3>
                    <p>Backend development, data analysis, and AI/ML integration</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">⚡</div>
                    <h3>C/C++</h3>
                    <p>System programming and performance-critical applications</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">🌐</div>
                    <h3>Web Development</h3>
                    <p>HTML, CSS, JavaScript for modern web applications</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">🗄️</div>
                    <h3>Database</h3>
                    <p>SQL database design and management</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">🤖</div>
                    <h3>AI/ML</h3>
                    <p>Machine learning algorithms and AI integration</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">📱</div>
                    <h3>Frontend</h3>
                    <p>Responsive design and user interface development</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="projects" id="projects">
        <div class="container">
            <h2 class="section-title fade-in">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card fade-in">
                    <div class="project-image">📊</div>
                    <div class="project-content">
                        <h3>Real-Time Detection Dashboard</h3>
                        <p>Developed a comprehensive real-time detection dashboard with integrated rule-based and machine learning engines for anomaly identification. Features dynamic visualization and enhanced decision-making capabilities.</p>
                        <div class="project-tech">
                            <span class="tech-tag">C++</span>
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">Machine Learning</span>
                        </div>
                        <div class="project-links">
                            <a href="https://github.com/Ayaanthaher" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>

                <div class="project-card fade-in">
                    <div class="project-image">🩸</div>
                    <div class="project-content">
                        <h3>Blood Bank Management System</h3>
                        <p>Designed and developed a comprehensive blood bank system for locating required blood types and nearby hospitals. Integrated donor health history for safe transfusions and improved emergency response efficiency.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">SQL</span>
                            <span class="tech-tag">Database</span>
                        </div>
                        <div class="project-links">
                            <a href="https://github.com/Ayaanthaher" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>

                <div class="project-card fade-in">
                    <div class="project-image">🐕</div>
                    <div class="project-content">
                        <h3>Smart Pet Feeder System</h3>
                        <p>Developed an AI-powered automatic pet feeding system that leverages artificial intelligence to manage and optimize pet feeding schedules. Features smart scheduling and health monitoring.</p>
                        <div class="project-tech">
                            <span class="tech-tag">C</span>
                            <span class="tech-tag">AI/ML</span>
                            <span class="tech-tag">IoT</span>
                        </div>
                        <div class="project-links">
                            <a href="https://github.com/Ayaanthaher" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <div class="container">
            <h2 class="section-title fade-in">Get In Touch</h2>
            <div class="contact-content">
                <div class="contact-info fade-in">
                    <div class="contact-item">
                        <strong>📞 Phone:</strong> +91 9000387635
                    </div>
                    <div class="contact-item">
                        <strong>📧 Email:</strong> thaher2505@gmail.com
                    </div>
                    <div class="contact-item">
                        <strong>💼 LinkedIn:</strong> linkedin.com/in/ayaan-thaher-n
                    </div>
                </div>
                
                <form class="contact-form fade-in">
                    <div class="form-group">
                        <label for="name">Full Name</label>
                        <input type="text" id="name" name="name" placeholder="Enter your full name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email Address</label>
                        <input type="email" id="email" name="email" placeholder="Enter your email" required>
                    </div>
                    <div class="form-group">
                        <label for="subject">Subject</label>
                        <input type="text" id="subject" name="subject" placeholder="Enter subject" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" rows="5" placeholder="Enter your message" required></textarea>
                    </div>
                    <button type="submit" class="submit-btn">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <p>&copy; 2025 Ayaan Thaher N. All rights reserved. | Computer Science Student & Full-Stack Developer</p>
        </div>
    </footer>

    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

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
                    entry.target.classList.add('appear');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Contact form submission
        document.querySelector('.contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you for your message! I\'ll get back to you soon.');
            this.reset();
        });
    </script>
</body>
</html>
