<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Abdellm - Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'SF Pro Display', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
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
            background: radial-gradient(circle at 50% 50%, rgba(14, 165, 233, 0.1) 0%, transparent 70%);
            pointer-events: none;
        }

        .hero-content {
            z-index: 2;
            position: relative;
        }

        .name {
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 800;
            background: linear-gradient(135deg, #ffffff 0%, #0ea5e9 50%, #3b82f6 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1rem;
            letter-spacing: -0.02em;
        }

        .tagline {
            font-size: clamp(1.2rem, 3vw, 1.8rem);
            color: #94a3b8;
            margin-bottom: 2rem;
            font-weight: 300;
        }

        .subtitle {
            font-size: clamp(1rem, 2.5vw, 1.4rem);
            color: #64748b;
            margin-bottom: 3rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .section {
            padding: 80px 0;
            text-align: center;
        }

        .section-title {
            font-size: clamp(2rem, 5vw, 3rem);
            font-weight: 700;
            margin-bottom: 3rem;
            background: linear-gradient(135deg, #ffffff 0%, #0ea5e9 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 2rem;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.08);
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .tech-category {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 24px;
            padding: 2.5rem;
            transition: all 0.4s ease;
        }

        .tech-category:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(14, 165, 233, 0.2);
        }

        .tech-title {
            font-size: 1.5rem;
            font-weight: 600;
            color: #0ea5e9;
            margin-bottom: 1.5rem;
        }

        .tech-list {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            justify-content: center;
        }

        .tech-item {
            background: rgba(14, 165, 233, 0.1);
            border: 1px solid rgba(14, 165, 233, 0.3);
            border-radius: 12px;
            padding: 0.8rem 1.2rem;
            font-size: 0.9rem;
            font-weight: 500;
            color: #e2e8f0;
            transition: all 0.3s ease;
        }

        .tech-item:hover {
            background: rgba(14, 165, 233, 0.2);
            transform: scale(1.05);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 24px;
            padding: 2.5rem;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #0ea5e9, #3b82f6, #8b5cf6);
        }

        .project-card:hover {
            transform: translateY(-12px);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: 700;
            color: #ffffff;
            margin-bottom: 1rem;
        }

        .project-desc {
            color: #94a3b8;
            margin-bottom: 1.5rem;
            font-size: 1rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .project-tech-item {
            background: rgba(59, 130, 246, 0.1);
            border: 1px solid rgba(59, 130, 246, 0.3);
            border-radius: 8px;
            padding: 0.4rem 0.8rem;
            font-size: 0.8rem;
            color: #93c5fd;
        }

        .project-link {
            display: inline-block;
            background: linear-gradient(135deg, #0ea5e9, #3b82f6);
            color: white;
            text-decoration: none;
            padding: 0.8rem 1.5rem;
            border-radius: 12px;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(14, 165, 233, 0.4);
        }

        .contact {
            background: rgba(255, 255, 255, 0.02);
            backdrop-filter: blur(20px);
            border-radius: 32px;
            padding: 4rem 2rem;
            margin: 2rem 0;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
            margin-top: 2rem;
        }

        .contact-link {
            display: inline-block;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.2);
            color: #e2e8f0;
            text-decoration: none;
            padding: 1rem 2rem;
            border-radius: 16px;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .contact-link:hover {
            background: rgba(14, 165, 233, 0.2);
            border-color: #0ea5e9;
            transform: translateY(-4px);
        }

        .floating-elements {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .floating-dot {
            position: absolute;
            width: 4px;
            height: 4px;
            background: #0ea5e9;
            border-radius: 50%;
            opacity: 0.6;
            animation: float 6s ease-in-out infinite;
        }

        .floating-dot:nth-child(1) { top: 20%; left: 10%; animation-delay: 0s; }
        .floating-dot:nth-child(2) { top: 60%; right: 15%; animation-delay: 2s; }
        .floating-dot:nth-child(3) { bottom: 30%; left: 20%; animation-delay: 4s; }
        .floating-dot:nth-child(4) { top: 40%; right: 25%; animation-delay: 1s; }
        .floating-dot:nth-child(5) { bottom: 20%; right: 10%; animation-delay: 3s; }

        @keyframes float {
            0%, 100% { transform: translateY(0px) translateX(0px); opacity: 0.6; }
            50% { transform: translateY(-20px) translateX(10px); opacity: 1; }
        }

        @media (max-width: 768px) {
            .section { padding: 60px 0; }
            .tech-grid { grid-template-columns: 1fr; }
            .projects-grid { grid-template-columns: 1fr; }
            .contact-links { flex-direction: column; align-items: center; }
        }
    </style>
</head>
<body>
    <div class="floating-elements">
        <div class="floating-dot"></div>
        <div class="floating-dot"></div>
        <div class="floating-dot"></div>
        <div class="floating-dot"></div>
        <div class="floating-dot"></div>
    </div>

    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1 class="name">Abdellm</h1>
                <p class="tagline">Full Stack Developer & UI/UX Designer</p>
                <p class="subtitle">Founder of UPSICAST • Building digital experiences that matter</p>
            </div>
        </div>
    </section>

    <section class="section">
        <div class="container">
            <h2 class="section-title">GitHub Stats</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api?username=Init-Abdellm&show_icons=true&theme=tokyonight&hide_border=true&bg_color=00000000&title_color=0ea5e9&icon_color=0ea5e9&text_color=ffffff" alt="GitHub Stats"/>
                </div>
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Init-Abdellm&layout=compact&theme=tokyonight&hide_border=true&bg_color=00000000&title_color=0ea5e9&text_color=ffffff" alt="Top Languages"/>
                </div>
            </div>
            <div class="stat-card">
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=Init-Abdellm&theme=tokyonight&hide_border=true&background=00000000&ring=0ea5e9&fire=0ea5e9&currStreakLabel=ffffff" alt="GitHub Streak"/>
            </div>
        </div>
    </section>

    <section class="section">
        <div class="container">
            <h2 class="section-title">Technology Stack</h2>
            <div class="tech-grid">
                <div class="tech-category">
                    <h3 class="tech-title">Frontend</h3>
                    <div class="tech-list">
                        <span class="tech-item">React</span>
                        <span class="tech-item">Angular</span>
                        <span class="tech-item">TypeScript</span>
                        <span class="tech-item">JavaScript</span>
                        <span class="tech-item">HTML5</span>
                        <span class="tech-item">CSS3</span>
                        <span class="tech-item">Sass</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h3 class="tech-title">Backend</h3>
                    <div class="tech-list">
                        <span class="tech-item">Python</span>
                        <span class="tech-item">Node.js</span>
                        <span class="tech-item">Express.js</span>
                        <span class="tech-item">RESTful APIs</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h3 class="tech-title">Database & Cloud</h3>
                    <div class="tech-list">
                        <span class="tech-item">MongoDB</span>
                        <span class="tech-item">PostgreSQL</span>
                        <span class="tech-item">Azure</span>
                        <span class="tech-item">Firebase</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h3 class="tech-title">DevOps & Tools</h3>
                    <div class="tech-list">
                        <span class="tech-item">Git</span>
                        <span class="tech-item">Docker</span>
                        <span class="tech-item">Kubernetes</span>
                        <span class="tech-item">CI/CD</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="section">
        <div class="container">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3 class="project-title">YAKOUB</h3>
                    <p class="project-desc">Modern web application with real-time features and responsive design</p>
                    <div class="project-tech">
                        <span class="project-tech-item">React</span>
                        <span class="project-tech-item">Firebase</span>
                        <span class="project-tech-item">Real-time</span>
                    </div>
                    <a href="https://yakoub-5bd60.web.app/" class="project-link">View Project</a>
                </div>
                <div class="project-card">
                    <h3 class="project-title">HIRESHUB</h3>
                    <p class="project-desc">Comprehensive recruitment platform connecting talent with opportunities</p>
                    <div class="project-tech">
                        <span class="project-tech-item">React</span>
                        <span class="project-tech-item">Node.js</span>
                        <span class="project-tech-item">MongoDB</span>
                    </div>
                    <a href="https://hireshub.vercel.app/" class="project-link">View Project</a>
                </div>
                <div class="project-card">
                    <h3 class="project-title">KHALILIA</h3>
                    <p class="project-desc">E-commerce solution with payment integration and admin dashboard</p>
                    <div class="project-tech">
                        <span class="project-tech-item">Angular</span>
                        <span class="project-tech-item">MongoDB</span>
                        <span class="project-tech-item">Payment API</span>
                    </div>
                    <a href="https://khalilia.vercel.app" class="project-link">View Project</a>
                </div>
                <div class="project-card">
                    <h3 class="project-title">UPSICAST</h3>
                    <p class="project-desc">Digital agency platform with AI integration and cloud architecture</p>
                    <div class="project-tech">
                        <span class="project-tech-item">Full Stack</span>
                        <span class="project-tech-item">AI Integration</span>
                        <span class="project-tech-item">Cloud</span>
                    </div>
                    <a href="#" class="project-link">Coming Soon</a>
                </div>
            </div>
        </div>
    </section>

    <section class="section">
        <div class="container">
            <div class="contact">
                <h2 class="section-title">Let's Connect</h2>
                <p class="subtitle">Available for freelance projects, startup collaborations, and consulting opportunities</p>
                <div class="contact-links">
                    <a href="https://www.linkedin.com/in/abdellm/" class="contact-link">LinkedIn</a>
                    <a href="mailto:Abdelmoughitezinebi@gmail.com" class="contact-link">Email</a>
                </div>
            </div>
        </div>
    </section>
</body>
</html>
