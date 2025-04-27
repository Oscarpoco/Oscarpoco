<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Oscar Poco - MERN Stack Developer</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/js/all.min.js"></script>
    <style>
        :root {
            --primary: #4F46E5;
            --primary-light: #818CF8;
            --secondary: #10B981;
            --dark: #1F2937;
            --light: #F9FAFB;
            --accent: #F59E0B;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
            padding-bottom: 4rem;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 0 2rem;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary), var(--primary-light));
            color: white;
            padding: 4rem 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        header::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: repeating-linear-gradient(45deg, rgba(255,255,255,0.05), rgba(255,255,255,0.05) 10px, transparent 10px, transparent 20px);
            z-index: 1;
        }
        
        .header-content {
            position: relative;
            z-index: 2;
        }
        
        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid white;
            margin-bottom: 1.5rem;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            animation: float 4s ease-in-out infinite;
            background-color: #ddd;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: var(--primary);
            margin: 0 auto 1.5rem;
        }
        
        .header-title {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            animation: fadeInUp 1s ease-out;
        }
        
        .header-subtitle {
            font-size: 1.25rem;
            opacity: 0.9;
            max-width: 700px;
            margin: 0 auto 1.5rem;
            animation: fadeInUp 1s ease-out 0.3s both;
        }
        
        .social-icons {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 1.5rem;
            animation: fadeInUp 1s ease-out 0.6s both;
        }
        
        .social-icons a {
            color: white;
            font-size: 1.5rem;
            transition: transform 0.3s ease;
        }
        
        .social-icons a:hover {
            transform: translateY(-5px);
        }
        
        section {
            padding: 3rem 0;
            animation: fadeIn 1s ease-out;
        }
        
        section:nth-child(odd) {
            background-color: white;
        }
        
        .section-title {
            text-align: center;
            font-size: 2rem;
            margin-bottom: 2.5rem;
            color: var(--primary);
            position: relative;
            padding-bottom: 0.5rem;
        }
        
        .section-title::after {
            content: "";
            position: absolute;
            left: 50%;
            bottom: 0;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: var(--secondary);
        }
        
        .tech-container {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: center;
            margin-top: 1.5rem;
        }
        
        .tech-category {
            background-color: white;
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            width: calc(50% - 1rem);
            min-width: 280px;
            flex-grow: 1;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .tech-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }
        
        .tech-category h3 {
            font-size: 1.25rem;
            margin-bottom: 1rem;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        .tech-items {
            display: flex;
            flex-wrap: wrap;
            gap: 0.75rem;
        }
        
        .tech-item {
            padding: 0.5rem 1rem;
            background-color: #EEF2FF;
            border-radius: 20px;
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transition: background-color 0.3s ease;
        }
        
        .tech-item:hover {
            background-color: #DDD6FE;
        }
        
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 1.5rem;
        }
        
        .project-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }
        
        .project-img {
            height: 200px;
            background-color: #ddd;
            position: relative;
            overflow: hidden;
        }
        
        .project-img::before {
            content: '🏨';
            position: absolute;
            font-size: 5rem;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        
        .project-content {
            padding: 1.5rem;
        }
        
        .project-title {
            font-size: 1.25rem;
            margin-bottom: 0.75rem;
            color: var(--dark);
        }
        
        .project-description {
            color: #6B7280;
            margin-bottom: 1rem;
        }
        
        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }
        
        .project-tech span {
            padding: 0.25rem 0.75rem;
            background-color: #EEF2FF;
            border-radius: 20px;
            font-size: 0.8rem;
        }
        
        .project-links {
            display: flex;
            justify-content: space-between;
        }
        
        .project-links a {
            padding: 0.5rem 1rem;
            border-radius: 4px;
            text-decoration: none;
            font-weight: 500;
            font-size: 0.9rem;
            transition: background-color 0.3s ease;
        }
        
        .primary-btn {
            background-color: var(--primary);
            color: white;
        }
        
        .primary-btn:hover {
            background-color: var(--primary-light);
        }
        
        .secondary-btn {
            background-color: #E5E7EB;
            color: var(--dark);
        }
        
        .secondary-btn:hover {
            background-color: #D1D5DB;
        }
        
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }
        
        .contact-info {
            text-align: center;
            margin-bottom: 2rem;
        }
        
        .contact-email {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.75rem 1.5rem;
            background-color: #EEF2FF;
            border-radius: 30px;
            text-decoration: none;
            color: var(--primary);
            font-weight: 500;
            transition: background-color 0.3s ease;
        }
        
        .contact-email:hover {
            background-color: #DDD6FE;
        }
        
        footer {
            text-align: center;
            padding: 2rem 0;
            background-color: var(--dark);
            color: white;
            font-size: 0.9rem;
        }
        
        .scroll-animation {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }
        
        .visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        @keyframes float {
            0% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-15px);
            }
            100% {
                transform: translateY(0);
            }
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
        
        @media (max-width: 768px) {
            .tech-category {
                width: 100%;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .header-title {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="header-content container">
            <div class="profile-img">
                OP
            </div>
            <h1 class="header-title">Oscar Poco</h1>
            <p class="header-subtitle">A 24-year-old MERN stack developer with a passion for crafting innovative mobile and web applications that make a difference 🌟</p>
            <div class="social-icons">
                <a href="https://github.com/" aria-label="GitHub Profile"><i class="fab fa-github"></i></a>
                <a href="https://linkedin.com/" aria-label="LinkedIn Profile"><i class="fab fa-linkedin"></i></a>
                <a href="mailto:oscarkylepoco@gmail.com" aria-label="Email"><i class="fas fa-envelope"></i></a>
                <a href="#" aria-label="Portfolio Website"><i class="fas fa-globe"></i></a>
            </div>
        </div>
    </header>
    
    <section id="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="scroll-animation">
                <p>With a strong foundation in React, React Native, and Firebase, I deliver high-quality solutions that drive results 🚀. I'm passionate about creating seamless user experiences and powerful backend systems that work together flawlessly.</p>
                <p>My approach combines technical excellence with creative problem-solving, ensuring each project not only functions perfectly but also delivers an exceptional user experience.</p>
            </div>
        </div>
    </section>
    
    <section id="tech-stack">
        <div class="container">
            <h2 class="section-title">Tech Stack</h2>
            <div class="tech-container">
                <div class="tech-category scroll-animation">
                    <h3><i class="fas fa-laptop-code"></i> Frontend</h3>
                    <div class="tech-items">
                        <span class="tech-item"><i class="fab fa-react"></i> React</span>
                        <span class="tech-item"><i class="fab fa-react"></i> React Native</span>
                        <span class="tech-item"><i class="fab fa-js"></i> JavaScript (ES6+)</span>
                        <span class="tech-item"><i class="fab fa-html5"></i> HTML5</span>
                        <span class="tech-item"><i class="fab fa-css3-alt"></i> CSS3</span>
                    </div>
                </div>
                
                <div class="tech-category scroll-animation">
                    <h3><i class="fas fa-server"></i> Backend</h3>
                    <div class="tech-items">
                        <span class="tech-item"><i class="fab fa-node-js"></i> Node.js</span>
                        <span class="tech-item"><i class="fab fa-node-js"></i> Express.js</span>
                        <span class="tech-item"><i class="fas fa-cogs"></i> RESTful APIs</span>
                    </div>
                </div>
                
                <div class="tech-category scroll-animation">
                    <h3><i class="fas fa-database"></i> Database</h3>
                    <div class="tech-items">
                        <span class="tech-item"><i class="fas fa-leaf"></i> MongoDB</span>
                        <span class="tech-item"><i class="fas fa-fire"></i> Firebase</span>
                    </div>
                </div>
                
                <div class="tech-category scroll-animation">
                    <h3><i class="fas fa-palette"></i> UI/UX</h3>
                    <div class="tech-items">
                        <span class="tech-item"><i class="fas fa-user"></i> User-centered design</span>
                        <span class="tech-item"><i class="fas fa-mobile-alt"></i> Responsive design</span>
                        <span class="tech-item"><i class="fas fa-universal-access"></i> Accessibility</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <section id="projects">
        <div class="container">
            <h2 class="section-title">Projects</h2>
            <div class="projects-grid">
                <div class="project-card scroll-animation">
                    <div class="project-img"></div>
                    <div class="project-content">
                        <h3 class="project-title">Hotel CMS</h3>
                        <p class="project-description">A comprehensive hotel management system built using the MERN stack with room management, booking system, and user authentication.</p>
                        <div class="project-tech">
                            <span>React</span>
                            <span>Node.js</span>
                            <span>MongoDB</span>
                            <span>Express</span>
                        </div>
                        <div class="project-links">
                            <a href="https://hotel-management-system-iota.vercel.app/" class="primary-btn" target="_blank">Live Demo</a>
                            <a href="#" class="secondary-btn">Code</a>
                        </div>
                    </div>
                </div>
                
                <div class="project-card scroll-animation">
                    <div class="project-img"></div>
                    <div class="project-content">
                        <h3 class="project-title">Hotel Application</h3>
                        <p class="project-description">A user-friendly hotel application showcasing my UI/UX skills with room booking, amenities, and services.</p>
                        <div class="project-tech">
                            <span>React</span>
                            <span>JavaScript</span>
                            <span>Firebase</span>
                            <span>CSS</span>
                        </div>
                        <div class="project-links">
                            <a href="https://hotel-application-beta.vercel.app/" class="primary-btn" target="_blank">Live Demo</a>
                            <a href="#" class="secondary-btn">Code</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <section id="contact">
        <div class="container">
            <h2 class="section-title">Let's Collaborate</h2>
            <div class="contact-info scroll-animation">
                <p>I'm always excited to work on new projects and collaborate with like-minded individuals. If you have an idea or project in mind, let's chat!</p>
                <a href="mailto:oscarkylepoco@gmail.com" class="contact-email">
                    <i class="fas fa-envelope"></i> oscarkylepoco@gmail.com
                </a>
            </div>
        </div>
    </section>
    
    <footer>
        <div class="container">
            <p>&copy; 2025 Oscar Poco. All rights reserved.</p>
        </div>
    </footer>
    
    <script>
        // Scroll animation
        document.addEventListener('DOMContentLoaded', function() {
            const scrollElements = document.querySelectorAll('.scroll-animation');
            
            const elementInView = (el, percentageScroll = 100) => {
                const elementTop = el.getBoundingClientRect().top;
                return (
                    elementTop <= 
                    ((window.innerHeight || document.documentElement.clientHeight) * (percentageScroll/100))
                );
            };
            
            const displayScrollElement = (element) => {
                element.classList.add('visible');
            };
            
            const handleScrollAnimation = () => {
                scrollElements.forEach((el) => {
                    if (elementInView(el, 80)) {
                        displayScrollElement(el);
                    }
                })
            }
            
            // Initial check
            handleScrollAnimation();
            
            // Add scroll event
            window.addEventListener('scroll', () => {
                handleScrollAnimation();
            });
        });
    </script>
</body>
</html>
