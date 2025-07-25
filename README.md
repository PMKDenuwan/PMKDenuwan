<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kavindu Denuwan - Full Stack Innovator</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a3e 50%, #2d1b69 100%);
            color: #ffffff;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Animated background particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            background: rgba(100, 255, 218, 0.1);
            border-radius: 50%;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) rotate(360deg); opacity: 0; }
        }

        /* Header Section */
        .hero {
            position: relative;
            z-index: 10;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: radial-gradient(ellipse at center, rgba(100, 255, 218, 0.1) 0%, transparent 70%);
        }

        .hero-content {
            max-width: 1200px;
            padding: 2rem;
        }

        .glitch-text {
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 900;
            text-transform: uppercase;
            background: linear-gradient(45deg, #64ffda, #ff6b6b, #4ecdc4, #45b7d1);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease-in-out infinite, glitch 2s infinite;
            margin-bottom: 1rem;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @keyframes glitch {
            0%, 90%, 100% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
        }

        .typing-effect {
            font-size: clamp(1.2rem, 3vw, 2rem);
            color: #64ffda;
            margin-bottom: 2rem;
            height: 3rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .subtitle {
            font-size: 1.3rem;
            color: #a8b2d1;
            max-width: 600px;
            margin: 0 auto 3rem;
            opacity: 0;
            animation: fadeInUp 1s ease-out 0.5s forwards;
        }

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

        .cta-buttons {
            display: flex;
            gap: 2rem;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 4rem;
        }

        .cta-btn {
            padding: 1rem 2rem;
            background: linear-gradient(45deg, #64ffda, #4ecdc4);
            color: #0f0f23;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            border: none;
            cursor: pointer;
        }

        .cta-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(100, 255, 218, 0.3);
        }

        .cta-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.5s;
        }

        .cta-btn:hover::before {
            left: 100%;
        }

        /* Skills Matrix */
        .skills-matrix {
            position: relative;
            z-index: 10;
            padding: 5rem 2rem;
            background: rgba(15, 15, 35, 0.9);
            backdrop-filter: blur(10px);
        }

        .section-title {
            font-size: 3rem;
            text-align: center;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, #64ffda, #ff6b6b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .skill-category {
            background: linear-gradient(135deg, rgba(100, 255, 218, 0.1), rgba(255, 107, 107, 0.1));
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(100, 255, 218, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-category::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, #64ffda, #ff6b6b, #4ecdc4);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .skill-category:hover::before {
            transform: scaleX(1);
        }

        .skill-category:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(100, 255, 218, 0.2);
        }

        .skill-category h3 {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: #64ffda;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
        }

        .skill-tag {
            padding: 0.5rem 1rem;
            background: rgba(100, 255, 218, 0.1);
            border: 1px solid rgba(100, 255, 218, 0.3);
            border-radius: 25px;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .skill-tag:hover {
            background: rgba(100, 255, 218, 0.2);
            transform: scale(1.05);
        }

        /* Projects Showcase */
        .projects-showcase {
            position: relative;
            z-index: 10;
            padding: 5rem 2rem;
            background: linear-gradient(135deg, rgba(26, 26, 62, 0.9), rgba(45, 27, 105, 0.9));
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(100, 255, 218, 0.1);
            transition: all 0.3s ease;
            position: relative;
        }

        .project-card:hover {
            transform: translateY(-10px) rotateX(5deg);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.3);
        }

        .project-header {
            height: 200px;
            background: linear-gradient(45deg, #64ffda, #4ecdc4, #45b7d1);
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: #0f0f23;
        }

        .project-content {
            padding: 2rem;
        }

        .project-title {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #64ffda;
        }

        .project-description {
            color: #a8b2d1;
            margin-bottom: 1.5rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .tech-badge {
            padding: 0.3rem 0.8rem;
            background: rgba(255, 107, 107, 0.2);
            border-radius: 15px;
            font-size: 0.8rem;
            color: #ff6b6b;
        }

        /* Stats Dashboard */
        .stats-dashboard {
            position: relative;
            z-index: 10;
            padding: 5rem 2rem;
            background: rgba(15, 15, 35, 0.95);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            max-width: 1000px;
            margin: 0 auto;
        }

        .stat-card {
            text-align: center;
            padding: 2rem;
            background: linear-gradient(135deg, rgba(100, 255, 218, 0.1), rgba(69, 183, 209, 0.1));
            border-radius: 20px;
            border: 1px solid rgba(100, 255, 218, 0.2);
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: scale(1.05);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            color: #64ffda;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            color: #a8b2d1;
            font-size: 1.1rem;
        }

        /* Contact Section */
        .contact-section {
            position: relative;
            z-index: 10;
            padding: 5rem 2rem;
            background: linear-gradient(135deg, rgba(45, 27, 105, 0.9), rgba(15, 15, 35, 0.9));
            text-align: center;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
            margin-top: 3rem;
        }

        .contact-link {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem 2rem;
            background: rgba(100, 255, 218, 0.1);
            border: 1px solid rgba(100, 255, 218, 0.3);
            border-radius: 50px;
            color: #64ffda;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .contact-link:hover {
            background: rgba(100, 255, 218, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(100, 255, 218, 0.2);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .glitch-text {
                font-size: 3rem;
            }
            
            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .skills-grid,
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        /* Loading animation */
        .loading-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #0f0f23;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            animation: fadeOut 2s ease-out 3s forwards;
        }

        .loader {
            width: 50px;
            height: 50px;
            border: 3px solid rgba(100, 255, 218, 0.3);
            border-top: 3px solid #64ffda;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        @keyframes fadeOut {
            to {
                opacity: 0;
                visibility: hidden;
            }
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div class="loading-overlay">
        <div class="loader"></div>
    </div>

    <!-- Animated Background -->
    <div class="particles" id="particles"></div>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1 class="glitch-text">Kavindu Denuwan</h1>
            <div class="typing-effect" id="typingText"></div>
            <p class="subtitle">
                🚀 Crafting digital experiences that merge innovation, design, and data into scalable solutions. 
                From pixel-perfect UIs to robust backends, I transform complex problems into elegant, user-centered products.
            </p>
            <div class="cta-buttons">
                <a href="#projects" class="cta-btn">View My Work</a>
                <a href="#contact" class="cta-btn">Let's Collaborate</a>
            </div>
        </div>
    </section>

    <!-- Skills Matrix -->
    <section class="skills-matrix">
        <h2 class="section-title">Tech Arsenal</h2>
        <div class="skills-grid">
            <div class="skill-category">
                <h3>🎯 Frontend Mastery</h3>
                <div class="skill-tags">
                    <span class="skill-tag">React.js</span>
                    <span class="skill-tag">JavaScript ES6+</span>
                    <span class="skill-tag">TypeScript</span>
                    <span class="skill-tag">Tailwind CSS</span>
                    <span class="skill-tag">HTML5/CSS3</span>
                    <span class="skill-tag">Bootstrap</span>
                    <span class="skill-tag">Responsive Design</span>
                </div>
            </div>
            <div class="skill-category">
                <h3>⚡ Backend Engineering</h3>
                <div class="skill-tags">
                    <span class="skill-tag">Spring Boot</span>
                    <span class="skill-tag">Node.js</span>
                    <span class="skill-tag">Express.js</span>
                    <span class="skill-tag">Java</span>
                    <span class="skill-tag">Python</span>
                    <span class="skill-tag">RESTful APIs</span>
                    <span class="skill-tag">Microservices</span>
                </div>
            </div>
            <div class="skill-category">
                <h3>🗄️ Database & Cloud</h3>
                <div class="skill-tags">
                    <span class="skill-tag">MongoDB</span>
                    <span class="skill-tag">MySQL</span>
                    <span class="skill-tag">Hibernate</span>
                    <span class="skill-tag">Database Design</span>
                    <span class="skill-tag">Cloud Integration</span>
                    <span class="skill-tag">Performance Optimization</span>
                </div>
            </div>
            <div class="skill-category">
                <h3>📊 Data & Analytics</h3>
                <div class="skill-tags">
                    <span class="skill-tag">Power BI</span>
                    <span class="skill-tag">Python Analytics</span>
                    <span class="skill-tag">Data Visualization</span>
                    <span class="skill-tag">Matplotlib</span>
                    <span class="skill-tag">Seaborn</span>
                    <span class="skill-tag">Business Intelligence</span>
                </div>
            </div>
            <div class="skill-category">
                <h3>🎨 Design & UX</h3>
                <div class="skill-tags">
                    <span class="skill-tag">UI/UX Design</span>
                    <span class="skill-tag">Figma</span>
                    <span class="skill-tag">Prototyping</span>
                    <span class="skill-tag">User Research</span>
                    <span class="skill-tag">Design Systems</span>
                    <span class="skill-tag">Brand Identity</span>
                </div>
            </div>
            <div class="skill-category">
                <h3>🛠️ DevOps & Tools</h3>
                <div class="skill-tags">
                    <span class="skill-tag">Git/GitHub</span>
                    <span class="skill-tag">Postman</span>
                    <span class="skill-tag">Testing</span>
                    <span class="skill-tag">CI/CD</span>
                    <span class="skill-tag">Code Review</span>
                    <span class="skill-tag">Agile/Scrum</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Showcase -->
    <section class="projects-showcase" id="projects">
        <h2 class="section-title">Featured Projects</h2>
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-header">🚀</div>
                <div class="project-content">
                    <h3 class="project-title">E-Commerce Platform</h3>
                    <p class="project-description">Full-stack MERN application with advanced features like real-time inventory, payment integration, and analytics dashboard.</p>
                    <div class="project-tech">
                        <span class="tech-badge">React</span>
                        <span class="tech-badge">Node.js</span>
                        <span class="tech-badge">MongoDB</span>
                        <span class="tech-badge">Stripe API</span>
                    </div>
                </div>
            </div>
            <div class="project-card">
                <div class="project-header">📊</div>
                <div class="project-content">
                    <h3 class="project-title">Business Intelligence Suite</h3>
                    <p class="project-description">Comprehensive data visualization platform with interactive dashboards and automated reporting systems.</p>
                    <div class="project-tech">
                        <span class="tech-badge">Power BI</span>
                        <span class="tech-badge">Python</span>
                        <span class="tech-badge">SQL</span>
                        <span class="tech-badge">REST APIs</span>
                    </div>
                </div>
            </div>
            <div class="project-card">
                <div class="project-header">🎨</div>
                <div class="project-content">
                    <h3 class="project-title">Design System & UI Kit</h3>
                    <p class="project-description">Scalable design system with component library, ensuring consistency across multiple applications.</p>
                    <div class="project-tech">
                        <span class="tech-badge">Figma</span>
                        <span class="tech-badge">React</span>
                        <span class="tech-badge">Storybook</span>
                        <span class="tech-badge">Tailwind</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Dashboard -->
    <section class="stats-dashboard">
        <h2 class="section-title">Impact Metrics</h2>
        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-number" data-target="50">0</div>
                <div class="stat-label">Projects Completed</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-target="100">0</div>
                <div class="stat-label">Happy Clients</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-target="10000">0</div>
                <div class="stat-label">Lines of Code</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" data-target="24">0</div>
                <div class="stat-label">Technologies Mastered</div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact-section" id="contact">
        <h2 class="section-title">Let's Build Something Amazing</h2>
        <p style="font-size: 1.2rem; color: #a8b2d1; max-width: 600px; margin: 0 auto;">
            Ready to transform your ideas into reality? Whether it's a full-stack application, 
            data visualization project, or UI/UX design, let's collaborate and create something extraordinary.
        </p>
        <div class="contact-links">
            <a href="mailto:your.email@example.com" class="contact-link">
                <span>📧</span>
                <span>Email</span>
            </a>
            <a href="https://linkedin.com/in/your-profile" class="contact-link">
                <span>💼</span>
                <span>LinkedIn</span>
            </a>
            <a href="https://github.com/PMKDenuwan" class="contact-link">
                <span>💻</span>
                <span>GitHub</span>
            </a>
            <a href="#" class="contact-link">
                <span>📱</span>
                <span>Portfolio</span>
            </a>
        </div>
    </section>

    <script>
        // Create floating particles
        function createParticles() {
            const particles = document.getElementById('particles');
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.width = Math.random() * 5 + 2 + 'px';
                particle.style.height = particle.style.width;
                particle.style.animationDelay = Math.random() * 20 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                particles.appendChild(particle);
            }
        }

        // Typing effect
        const typingTexts = [
            "Full-Stack Developer 💻",
            "UI/UX Designer 🎨",
            "Data Analyst 📊",
            "Problem Solver 🧩",
            "Innovation Catalyst 🚀"
        ];

        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typingText');

        function typeWriter() {
            const currentText = typingTexts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }

            let typeSpeed = isDeleting ? 50 : 100;

            if (!isDeleting && charIndex === currentText.length) {
                typeSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % typingTexts.length;
                typeSpeed = 500;
            }

            setTimeout(typeWriter, typeSpeed);
        }

        // Animate statistics
        function animateStats() {
            const stats = document.querySelectorAll('.stat-number');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const target = parseInt(entry.target.getAttribute('data-target'));
                        let current = 0;
                        const increment = target / 100;
                        const timer = setInterval(() => {
                            current += increment;
                            entry.target.textContent = Math.floor(current);
                            if (current >= target) {
                                entry.target.textContent = target;
                                clearInterval(timer);
                            }
                        }, 20);
                        observer.unobserve(entry.target);
                    }
                });
            });

            stats.forEach(stat => observer.observe(stat));
        }

        // Smooth scrolling for anchor links
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

        // Initialize everything
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
            typeWriter();
            animateStats();
        });

        // Add parallax effect
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallaxElements = document.querySelectorAll('.hero');
            parallaxElements.forEach(element => {
                const speed = 0.5;
                element.style.transform = `translateY(${scrolled * speed}px)`;
            });
        });
    </script>
</body>
</html>
