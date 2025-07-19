<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rupesh Chidupudi - Full Stack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0e27 0%, #1a1b3a 25%, #2d1b4e 50%, #1a1b3a 75%, #0a0e27 100%);
            background-attachment: fixed;
            color: #ffffff;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Section */
        .header {
            text-align: center;
            padding: 60px 0;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 100" fill="%23ffffff08"><polygon points="0,0 1000,0 1000,60 0,100"/></svg>');
            background-size: cover;
        }

        .profile-header {
            position: relative;
            z-index: 2;
        }

        .profile-title {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 700;
            background: linear-gradient(45deg, #64ffda, #00bcd4, #2196f3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 20px;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { filter: drop-shadow(0 0 20px #64ffda40); }
            to { filter: drop-shadow(0 0 30px #64ffda60); }
        }

        .typing-animation {
            font-size: clamp(1.2rem, 3vw, 1.8rem);
            color: #64ffda;
            margin-bottom: 30px;
            min-height: 60px;
        }

        .stats-badges {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .badge {
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(100, 255, 218, 0.3);
            border-radius: 25px;
            padding: 10px 20px;
            font-size: 0.9rem;
            font-weight: 600;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .badge:hover {
            background: rgba(100, 255, 218, 0.2);
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(100, 255, 218, 0.3);
        }

        /* Full Stack Definition Section */
        .fullstack-definition {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 40px;
            margin: 60px 0;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .fullstack-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 30px;
            background: linear-gradient(45deg, #ff6b6b, #feca57, #48dbfb, #ff9ff3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .fullstack-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .fullstack-card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            padding: 25px;
            border: 1px solid rgba(100, 255, 218, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .fullstack-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.5s;
        }

        .fullstack-card:hover::before {
            left: 100%;
        }

        .fullstack-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(100, 255, 218, 0.2);
            border-color: rgba(100, 255, 218, 0.5);
        }

        .card-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            display: block;
        }

        .card-title {
            font-size: 1.3rem;
            font-weight: 700;
            color: #64ffda;
            margin-bottom: 10px;
        }

        /* GitHub Stats Section */
        .stats-section {
            margin: 80px 0;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            background: linear-gradient(45deg, #64ffda, #2196f3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(100, 255, 218, 0.2);
        }

        .stat-card img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            transition: transform 0.3s ease;
        }

        .stat-card:hover img {
            transform: scale(1.05);
        }

        /* Tech Stack Section */
        .tech-section {
            margin: 80px 0;
        }

        .tech-categories {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
        }

        .tech-category {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
        }

        .tech-category h3 {
            color: #64ffda;
            font-size: 1.5rem;
            margin-bottom: 20px;
            text-align: center;
        }

        .tech-icons {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
        }

        .tech-icon {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 15px;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
        }

        .tech-icon:hover {
            background: rgba(100, 255, 218, 0.2);
            transform: translateY(-5px) rotate(5deg);
        }

        .tech-icon img {
            width: 40px;
            height: 40px;
        }

        /* Skills Progress Section */
        .skills-section {
            margin: 80px 0;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 40px;
        }

        .skill-category {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
        }

        .skill-item {
            margin-bottom: 20px;
        }

        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-weight: 600;
        }

        .skill-bar {
            background: rgba(255, 255, 255, 0.1);
            height: 8px;
            border-radius: 4px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background: linear-gradient(90deg, #64ffda, #2196f3);
            border-radius: 4px;
            transition: width 2s ease;
            position: relative;
        }

        .skill-progress::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            animation: shimmer 2s infinite;
        }

        @keyframes shimmer {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        /* Projects Section */
        .projects-section {
            margin: 80px 0;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(100, 255, 218, 0.2);
        }

        .project-title {
            color: #64ffda;
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 15px;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin: 15px 0;
        }

        .tech-tag {
            background: rgba(100, 255, 218, 0.2);
            color: #64ffda;
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        /* Contact Section */
        .contact-section {
            margin: 80px 0;
            text-align: center;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }

        .contact-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 25px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            text-decoration: none;
            color: inherit;
        }

        .contact-card:hover {
            background: rgba(100, 255, 218, 0.1);
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(100, 255, 218, 0.2);
        }

        .contact-icon {
            font-size: 2rem;
            margin-bottom: 10px;
            display: block;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                padding: 0 15px;
            }
            
            .fullstack-grid {
                grid-template-columns: 1fr;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .tech-categories {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: 1fr;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .contact-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 480px) {
            .contact-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Floating Animation */
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .floating {
            animation: float 3s ease-in-out infinite;
        }

        /* Particle Effect */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            background: #64ffda;
            border-radius: 50%;
            animation: particle-float 6s linear infinite;
        }

        @keyframes particle-float {
            0% {
                transform: translateY(100vh) scale(0);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) scale(1);
                opacity: 0;
            }
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1) rotate(0deg); opacity: 0.3; }
            50% { transform: scale(1.1) rotate(180deg); opacity: 0.1; }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>
    
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="profile-header">
                <h1 class="profile-title">Rupesh Chidupudi</h1>
                <div class="typing-animation" id="typingText"></div>
                <div class="stats-badges">
                    <div class="badge">🚀 Full Stack Developer</div>
                    <div class="badge">🔥 350+ Days Active</div>
                    <div class="badge">📍 Hyderabad, India</div>
                    <div class="badge">💼 3+ Years Experience</div>
                    <div class="badge">⚡ 1,200+ Commits</div>
                    <div class="badge">🎯 96% Consistency</div>
                </div>
            </div>
        </header>

        <!-- Live Consistency Tracker -->
        <section class="live-tracker" style="margin: 40px 0; background: rgba(255, 255, 255, 0.05); border-radius: 20px; padding: 30px; border: 1px solid rgba(100, 255, 218, 0.2); backdrop-filter: blur(10px);">
            <h3 style="text-align: center; color: #64ffda; margin-bottom: 25px; font-size: 1.8rem;">🔴 Live Consistency Tracker</h3>
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 20px; text-align: center;">
                <div class="live-stat" style="padding: 15px; background: rgba(100, 255, 218, 0.1); border-radius: 10px; border: 1px solid rgba(100, 255, 218, 0.3);">
                    <div style="font-size: 1.8rem; color: #64ffda; font-weight: bold;" id="currentStreak">350+</div>
                    <div style="color: #b0b8c5; font-size: 0.9rem;">Current Streak</div>
                    <div style="color: #64ffda; font-size: 0.7rem;">🔥 Still Growing</div>
                </div>
                <div class="live-stat" style="padding: 15px; background: rgba(255, 107, 107, 0.1); border-radius: 10px; border: 1px solid rgba(255, 107, 107, 0.3);">
                    <div style="font-size: 1.8rem; color: #ff6b6b; font-weight: bold;" id="todayCommits">✅</div>
                    <div style="color: #b0b8c5; font-size: 0.9rem;">Today's Status</div>
                    <div style="color: #ff6b6b; font-size: 0.7rem;">💪 Committed</div>
                </div>
                <div class="live-stat" style="padding: 15px; background: rgba(254, 202, 87, 0.1); border-radius: 10px; border: 1px solid rgba(254, 202, 87, 0.3);">
                    <div style="font-size: 1.8rem; color: #feca57; font-weight: bold;" id="weeklyAvg">8.5</div>
                    <div style="color: #b0b8c5; font-size: 0.9rem;">Weekly Avg</div>
                    <div style="color: #feca57; font-size: 0.7rem;">📊 Commits/Day</div>
                </div>
                <div class="live-stat" style="padding: 15px; background: rgba(72, 219, 251, 0.1); border-radius: 10px; border: 1px solid rgba(72, 219, 251, 0.3);">
                    <div style="font-size: 1.8rem; color: #48dbfb; font-weight: bold;" id="consistency">96%</div>
                    <div style="color: #b0b8c5; font-size: 0.9rem;">Year Coverage</div>
                    <div style="color: #48dbfb; font-size: 0.7rem;">🎯 Consistent</div>
                </div>
                <div class="live-stat" style="padding: 15px; background: rgba(255, 159, 243, 0.1); border-radius: 10px; border: 1px solid rgba(255, 159, 243, 0.3);">
                    <div style="font-size: 1.8rem; color: #ff9ff3; font-weight: bold;" id="totalCommits">1.2K+</div>
                    <div style="color: #b0b8c5; font-size: 0.9rem;">Total Commits</div>
                    <div style="color: #ff9ff3; font-size: 0.7rem;">🚀 Growing</div>
                </div>
                <div class="live-stat" style="padding: 15px; background: rgba(116, 185, 255, 0.1); border-radius: 10px; border: 1px solid rgba(116, 185, 255, 0.3);">
                    <div style="font-size: 1.8rem; color: #74b9ff; font-weight: bold;" id="longestStreak">87</div>
                    <div style="color: #b0b8c5; font-size: 0.9rem;">Longest Streak</div>
                    <div style="color: #74b9ff; font-size: 0.7rem;">🏆 Personal Best</div>
                </div>
            </div>
            <div style="text-align: center; margin-top: 20px; padding: 15px; background: rgba(100, 255, 218, 0.05); border-radius: 10px;">
                <p style="color: #64ffda; font-weight: 600; margin-bottom: 5px;">💡 "Success is the sum of small efforts repeated day in and day out"</p>
                <p style="color: #b0b8c5; font-size: 0.9rem;">Last updated: <span style="color: #64ffda;">Just now</span> • Next goal: <span style="color: #64ffda;">400-day streak</span></p>
            </div>
        </section>

        <!-- Consistency Commitment Section -->
        <section class="commitment-section" style="margin: 60px 0; background: linear-gradient(135deg, rgba(100, 255, 218, 0.1) 0%, rgba(33, 150, 243, 0.1) 100%); border-radius: 25px; padding: 50px; border: 1px solid rgba(100, 255, 218, 0.2); position: relative; overflow: hidden;">
            <div style="position: absolute; top: -50%; left: -50%; width: 200%; height: 200%; background: radial-gradient(circle, rgba(100, 255, 218, 0.05) 0%, transparent 70%); animation: pulse 4s ease-in-out infinite;"></div>
            <div style="position: relative; z-index: 2;">
                <h2 style="text-align: center; font-size: 2.8rem; margin-bottom: 30px; background: linear-gradient(45deg, #64ffda, #2196f3, #ff6b6b); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">
                    ⚡ The Power of Daily Consistency
                </h2>
                <div style="text-align: center; margin-bottom: 40px;">
                    <p style="font-size: 1.4rem; color: #b0b8c5; line-height: 1.6; max-width: 800px; margin: 0 auto;">
                        Behind every line of code, every solved problem, and every successful project lies one fundamental principle: 
                        <strong style="color: #64ffda;">showing up consistently, every single day</strong>.
                    </p>
                </div>
                
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; margin: 40px 0;">
                    <div style="background: rgba(255, 255, 255, 0.05); border-radius: 20px; padding: 30px; border: 1px solid rgba(100, 255, 218, 0.2); text-align: center;">
                        <div style="font-size: 4rem; margin-bottom: 15px;">📈</div>
                        <h3 style="color: #64ffda; margin-bottom: 15px;">Measurable Growth</h3>
                        <p style="color: #b0b8c5; line-height: 1.6;">
                            Every commit tells a story of improvement. From <strong>0 to 1,200+ commits</strong>, 
                            each day builds upon the last, creating a compound effect of skill development.
                        </p>
                    </div>
                    <div style="background: rgba(255, 255, 255, 0.05); border-radius: 20px; padding: 30px; border: 1px solid rgba(255, 107, 107, 0.2); text-align: center;">
                        <div style="font-size: 4rem; margin-bottom: 15px;">🎯</div>
                        <h3 style="color: #ff6b6b; margin-bottom: 15px;">Discipline Over Motivation</h3>
                        <p style="color: #b0b8c5; line-height: 1.6;">
                            Motivation gets you started, but <strong>discipline keeps you going</strong>. 
                            96% year coverage proves that consistency isn't about perfect days—it's about showing up.
                        </p>
                    </div>
                    <div style="background: rgba(255, 255, 255, 0.05); border-radius: 20px; padding: 30px; border: 1px solid rgba(254, 202, 87, 0.2); text-align: center;">
                        <div style="font-size: 4rem; margin-bottom: 15px;">🚀</div>
                        <h3 style="color: #feca57; margin-bottom: 15px;">Compound Excellence</h3>
                        <p style="color: #b0b8c5; line-height: 1.6;">
                            Small daily improvements add up to remarkable results. 
                            <strong>350+ days of coding</strong> has transformed challenges into opportunities and problems into solutions.
                        </p>
                    </div>
                </div>

                <div style="background: rgba(0, 0, 0, 0.3); border-radius: 15px; padding: 25px; margin: 30px 0; border-left: 4px solid #64ffda;">
                    <h4 style="color: #64ffda; margin-bottom: 15px; font-size: 1.3rem;">💭 My Daily Coding Manifesto</h4>
                    <p style="color: #b0b8c5; line-height: 1.8; font-style: italic;">
                        "I don't code every day because I have to—I code every day because I choose to grow. 
                        Each commit is a vote for the developer I'm becoming. Each solved problem is a step toward mastery. 
                        Each day of consistency is a building block in my journey to create meaningful impact through technology."
                    </p>
                </div>

                <div style="text-align: center; margin-top: 40px;">
                    <div style="display: inline-flex; gap: 20px; flex-wrap: wrap; justify-content: center;">
                        <div style="background: rgba(100, 255, 218, 0.1); padding: 15px 25px; border-radius: 25px; border: 1px solid rgba(100, 255, 218, 0.3);">
                            <span style="color: #64ffda; font-weight: bold;">🔥 Current Streak: 350+ days</span>
                        </div>
                        <div style="background: rgba(255, 107, 107, 0.1); padding: 15px 25px; border-radius: 25px; border: 1px solid rgba(255, 107, 107, 0.3);">
                            <span style="color: #ff6b6b; font-weight: bold;">🎯 Next Goal: 400 days</span>
                        </div>
                        <div style="background: rgba(254, 202, 87, 0.1); padding: 15px 25px; border-radius: 25px; border: 1px solid rgba(254, 202, 87, 0.3);">
                            <span style="color: #feca57; font-weight: bold;">⚡ Daily Avg: 8.5 commits</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Full Stack Definition Section -->
        <section class="fullstack-definition">
            <h2 class="fullstack-title">🔥 What Full Stack Really Means</h2>
            <p style="text-align: center; font-size: 1.2rem; margin-bottom: 30px; color: #b0b8c5;">
                Full Stack Development isn't just frontend + backend. It's about being a <strong>complete solution architect</strong> who can handle every aspect of modern technology.
            </p>
            <div class="fullstack-grid">
                <div class="fullstack-card">
                    <span class="card-icon">🎨</span>
                    <h3 class="card-title">Frontend Excellence</h3>
                    <p>Modern UI/UX design, responsive interfaces, progressive web apps, and cutting-edge frontend frameworks that deliver exceptional user experiences.</p>
                </div>
                <div class="fullstack-card">
                    <span class="card-icon">⚡</span>
                    <h3 class="card-title">Backend Architecture</h3>
                    <p>Scalable APIs, microservices, database design, server optimization, and robust backend systems that power modern applications.</p>
                </div>
                <div class="fullstack-card">
                    <span class="card-icon">🤖</span>
                    <h3 class="card-title">AI & Machine Learning</h3>
                    <p>Intelligent algorithms, data modeling, machine learning pipelines, and AI integration to create smart, adaptive solutions.</p>
                </div>
                <div class="fullstack-card">
                    <span class="card-icon">🔧</span>
                    <h3 class="card-title">DevOps & Infrastructure</h3>
                    <p>CI/CD pipelines, cloud deployment, containerization, monitoring, and infrastructure as code for seamless development workflows.</p>
                </div>
                <div class="fullstack-card">
                    <span class="card-icon">📱</span>
                    <h3 class="card-title">Mobile Development</h3>
                    <p>Cross-platform mobile apps, native development, and responsive design that works flawlessly across all devices and platforms.</p>
                </div>
                <div class="fullstack-card">
                    <span class="card-icon">🌐</span>
                    <h3 class="card-title">End-to-End Solutions</h3>
                    <p>Complete project lifecycle management from ideation to deployment, ensuring every piece works together harmoniously.</p>
                </div>
            </div>
        </section>

        <!-- Consistency & Performance Section -->
        <section class="stats-section">
            <h2 class="section-title">🔥 Consistency & Performance Analytics</h2>
            <div class="consistency-intro" style="text-align: center; margin-bottom: 50px; background: rgba(255, 255, 255, 0.05); padding: 30px; border-radius: 20px; border: 1px solid rgba(100, 255, 218, 0.2);">
                <h3 style="color: #64ffda; font-size: 1.8rem; margin-bottom: 15px;">⚡ "Consistency Breeds Excellence"</h3>
                <p style="font-size: 1.2rem; color: #b0b8c5; line-height: 1.6;">
                    Success isn't just about talent—it's about showing up every day. My GitHub stats tell the story of dedication, 
                    continuous learning, and unwavering commitment to growth. Here's the proof of my consistency:
                </p>
            </div>

            <!-- Main Stats Grid -->
            <div class="stats-grid">
                <div class="stat-card floating">
                    <h4 style="color: #64ffda; margin-bottom: 15px; text-align: center;">🔥 GitHub Streak</h4>
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=chidupudi&theme=radical&hide_border=true&border_radius=15&date_format=M%20j%5B%2C%20Y%5D" alt="GitHub Streak Stats" />
                    <p style="text-align: center; color: #b0b8c5; margin-top: 10px; font-size: 0.9rem;">
                        <strong>Consistent daily coding</strong> - Building habits that last
                    </p>
                </div>
                <div class="stat-card floating" style="animation-delay: 0.2s;">
                    <h4 style="color: #64ffda; margin-bottom: 15px; text-align: center;">📊 Overall Performance</h4>
                    <img src="https://github-readme-stats.vercel.app/api?username=chidupudi&show_icons=true&theme=radical&hide_border=true&include_all_commits=true&count_private=true&border_radius=15&custom_title=GitHub%20Performance" alt="GitHub Stats" />
                    <p style="text-align: center; color: #b0b8c5; margin-top: 10px; font-size: 0.9rem;">
                        <strong>Quality contributions</strong> with measurable impact
                    </p>
                </div>
                <div class="stat-card floating" style="animation-delay: 0.4s;">
                    <h4 style="color: #64ffda; margin-bottom: 15px; text-align: center;">🎯 Language Mastery</h4>
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=chidupudi&layout=donut&theme=radical&hide_border=true&langs_count=8&border_radius=15&size_weight=0.5&count_weight=0.5" alt="Top Languages" />
                    <p style="text-align: center; color: #b0b8c5; margin-top: 10px; font-size: 0.9rem;">
                        <strong>Diverse tech stack</strong> mastery through practice
                    </p>
                </div>
                <div class="stat-card floating" style="animation-delay: 0.6s;">
                    <h4 style="color: #64ffda; margin-bottom: 15px; text-align: center;">⏰ Peak Productivity</h4>
                    <img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=chidupudi&theme=radical&utcOffset=5.5" alt="Productive Time" />
                    <p style="text-align: center; color: #b0b8c5; margin-top: 10px; font-size: 0.9rem;">
                        <strong>Optimized work schedule</strong> for maximum efficiency
                    </p>
                </div>
            </div>

            <!-- Additional Stats Row -->
            <div class="stats-grid" style="margin-top: 30px;">
                <div class="stat-card floating" style="animation-delay: 0.8s;">
                    <h4 style="color: #64ffda; margin-bottom: 15px; text-align: center;">📈 Contribution Summary</h4>
                    <img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=chidupudi&theme=radical" alt="Contribution Stats" />
                </div>
                <div class="stat-card floating" style="animation-delay: 1.0s;">
                    <h4 style="color: #64ffda; margin-bottom: 15px; text-align: center;">🏆 Commit Distribution</h4>
                    <img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=chidupudi&theme=radical" alt="Commit Language" />
                </div>
                <div class="stat-card floating" style="animation-delay: 1.2s;">
                    <h4 style="color: #64ffda; margin-bottom: 15px; text-align: center;">📊 Repository Analysis</h4>
                    <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=chidupudi&theme=radical" alt="Repos per Language" />
                </div>
                <div class="stat-card floating" style="animation-delay: 1.4s;">
                    <h4 style="color: #64ffda; margin-bottom: 15px; text-align: center;">🎖️ Achievement Gallery</h4>
                    <img src="https://github-profile-trophy.vercel.app/?username=chidupudi&theme=radical&no-frame=true&margin-w=5&column=3&row=2" alt="GitHub Trophies" />
                </div>
            </div>

            <!-- Annual Contribution Graph -->
            <div class="stat-card" style="margin-top: 30px;">
                <h4 style="color: #64ffda; margin-bottom: 15px; text-align: center;">📅 12-Month Consistency Journey</h4>
                <img src="https://github-readme-activity-graph.vercel.app/graph?username=chidupudi&theme=redical&bg_color=0d1117&color=58a6ff&line=58a6ff&point=ffffff&area=true&hide_border=true&custom_title=Daily%20Contributions%20-%20Consistency%20in%20Action" alt="Activity Graph" />
                <p style="text-align: center; color: #b0b8c5; margin-top: 15px; font-size: 1rem;">
                    <strong>365 days of commitment</strong> - Every green square represents dedication, learning, and growth
                </p>
            </div>

            <!-- Consistency Metrics -->
            <div class="consistency-metrics" style="margin-top: 40px;">
                <h3 style="text-align: center; color: #64ffda; margin-bottom: 30px; font-size: 2rem;">🎯 Consistency Metrics</h3>
                <div class="metrics-grid" style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px;">
                    <div class="metric-card" style="background: rgba(100, 255, 218, 0.1); border: 1px solid rgba(100, 255, 218, 0.3); border-radius: 15px; padding: 25px; text-align: center;">
                        <div style="font-size: 2.5rem; color: #64ffda; font-weight: bold;">350+</div>
                        <div style="color: #b0b8c5; font-size: 1rem;">Days of Activity</div>
                        <div style="color: #64ffda; font-size: 0.8rem; margin-top: 5px;">96% Year Coverage</div>
                    </div>
                    <div class="metric-card" style="background: rgba(255, 107, 107, 0.1); border: 1px solid rgba(255, 107, 107, 0.3); border-radius: 15px; padding: 25px; text-align: center;">
                        <div style="font-size: 2.5rem; color: #ff6b6b; font-weight: bold;">1,200+</div>
                        <div style="color: #b0b8c5; font-size: 1rem;">Total Commits</div>
                        <div style="color: #ff6b6b; font-size: 0.8rem; margin-top: 5px;">High Quality Code</div>
                    </div>
                    <div class="metric-card" style="background: rgba(254, 202, 87, 0.1); border: 1px solid rgba(254, 202, 87, 0.3); border-radius: 15px; padding: 25px; text-align: center;">
                        <div style="font-size: 2.5rem; color: #feca57; font-weight: bold;">50+</div>
                        <div style="color: #b0b8c5; font-size: 1rem;">Repositories</div>
                        <div style="color: #feca57; font-size: 0.8rem; margin-top: 5px;">Diverse Projects</div>
                    </div>
                    <div class="metric-card" style="background: rgba(72, 219, 251, 0.1); border: 1px solid rgba(72, 219, 251, 0.3); border-radius: 15px; padding: 25px; text-align: center;">
                        <div style="font-size: 2.5rem; color: #48dbfb; font-weight: bold;">15+</div>
                        <div style="color: #b0b8c5; font-size: 1rem;">Languages Used</div>
                        <div style="color: #48dbfb; font-size: 0.8rem; margin-top: 5px;">Tech Versatility</div>
                    </div>
                </div>
            </div>

            <!-- Consistency Philosophy -->
            <div style="margin-top: 50px; background: rgba(255, 255, 255, 0.05); padding: 40px; border-radius: 20px; border: 1px solid rgba(255, 255, 255, 0.1);">
                <h3 style="color: #64ffda; text-align: center; margin-bottom: 25px; font-size: 1.8rem;">💭 My Consistency Philosophy</h3>
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 30px; text-align: center;">
                    <div>
                        <div style="font-size: 3rem; margin-bottom: 10px;">🌱</div>
                        <h4 style="color: #64ffda; margin-bottom: 10px;">Daily Growth</h4>
                        <p style="color: #b0b8c5; font-size: 0.9rem;">Small, consistent improvements compound into extraordinary results over time.</p>
                    </div>
                    <div>
                        <div style="font-size: 3rem; margin-bottom: 10px;">🎯</div>
                        <h4 style="color: #64ffda; margin-bottom: 10px;">Quality Focus</h4>
                        <p style="color: #b0b8c5; font-size: 0.9rem;">Every commit matters. I prioritize meaningful contributions over quantity.</p>
                    </div>
                    <div>
                        <div style="font-size: 3rem; margin-bottom: 10px;">⚡</div>
                        <h4 style="color: #64ffda; margin-bottom: 10px;">Continuous Learning</h4>
                        <p style="color: #b0b8c5; font-size: 0.9rem;">Technology evolves rapidly. Consistent learning keeps me ahead of the curve.</p>
                    </div>
                    <div>
                        <div style="font-size: 3rem; margin-bottom: 10px;">🚀</div>
                        <h4 style="color: #64ffda; margin-bottom: 10px;">Building Habits</h4>
                        <p style="color: #b0b8c5; font-size: 0.9rem;">Success is a habit. Daily coding builds discipline and expertise.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Tech Stack Section -->
        <section class="tech-section">
            <h2 class="section-title">🛠️ Technology Arsenal</h2>
            <div class="tech-categories">
                <div class="tech-category">
                    <h3>🎨 Frontend Development</h3>
                    <div class="tech-icons">
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React" />
                        </div>
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
                        </div>
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
                        </div>
                    </div>
                </div>
                <div class="tech-category">
                    <h3>⚡ Backend Development</h3>
                    <div class="tech-icons">
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
                        </div>
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js" />
                        </div>
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI" />
                        </div>
                    </div>
                </div>
                <div class="tech-category">
                    <h3>🗄️ Databases & Storage</h3>
                    <div class="tech-icons">
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB" />
                        </div>
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
                        </div>
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/Redis-DD0031?style=for-the-badge&logo=redis&logoColor=white" alt="Redis" />
                        </div>
                    </div>
                </div>
                <div class="tech-category">
                    <h3>☁️ DevOps & Cloud</h3>
                    <div class="tech-icons">
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/Docker-0db7ed?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
                        </div>
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS" />
                        </div>
                        <div class="tech-icon">
                            <img src="https://img.shields.io/badge/Kubernetes-326ce5?style=for-the-badge&logo=kubernetes&logoColor=white" alt="Kubernetes" />
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills Progress Section -->
        <section class="skills-section">
            <h2 class="section-title">💪 Skill Proficiency Matrix</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3 style="color: #64ffda; text-align: center; margin-bottom: 25px;">Frontend Development</h3>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>React.js & Ecosystem</span>
                            <span>95%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="95%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>JavaScript/TypeScript</span>
                            <span>92%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="92%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Modern CSS & Frameworks</span>
                            <span>88%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="88%"></div>
                        </div>
                    </div>
                </div>
                <div class="skill-category">
                    <h3 style="color: #64ffda; text-align: center; margin-bottom: 25px;">Backend & DevOps</h3>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Python & FastAPI</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Node.js & Express</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Docker & Kubernetes</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="75%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section class="projects-section">
            <h2 class="section-title">🚀 Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3 class="project-title">🏢 Enterprise Resource Planning (ERP) System</h3>
                    <p>Comprehensive business management solution with advanced analytics, real-time reporting, and multi-tenant architecture.</p>
                    <div class="project-tech">
                        <span class="tech-tag">React</span>
                        <span class="tech-tag">Node.js</span>
                        <span class="tech-tag">MongoDB</span>
                        <span class="tech-tag">WebSockets</span>
                    </div>
                    <p><strong>Impact:</strong> Increased operational efficiency by 60% for SMEs</p>
                </div>
                <div class="project-card">
                    <h3 class="project-title">🤝 BBCollab - Collaboration Platform</h3>
                    <p>Real-time collaboration platform with advanced features including video conferencing, document sharing, and AI-powered insights.</p>
                    <div class="project-tech">
                        <span class="tech-tag">React</span>
                        <span class="tech-tag">Python</span>
                        <span class="tech-tag">PostgreSQL</span>
                        <span class="tech-tag">WebRTC</span>
                    </div>
                    <p><strong>Impact:</strong> Enhanced team productivity by 40%</p>
                </div>
                <div class="project-card">
                    <h3 class="project-title">🌐 ADP Network Platform</h3>
                    <p>Scalable networking platform with advanced security features, real-time messaging, and analytics dashboard.</p>
                    <div class="project-tech">
                        <span class="tech-tag">Full Stack</span>
                        <span class="tech-tag">Microservices</span>
                        <span class="tech-tag">Redis</span>
                        <span class="tech-tag">Docker</span>
                    </div>
                    <p><strong>Impact:</strong> Serving 10,000+ active users daily</p>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="contact-section">
            <h2 class="section-title">🤝 Let's Build Something Amazing Together</h2>
            <p style="font-size: 1.2rem; margin-bottom: 30px; color: #b0b8c5;">
                Ready to turn your ideas into reality? Let's connect and create innovative solutions that make a difference.
            </p>
            <div class="contact-grid">
                <a href="mailto:chrupesh2425@gmail.com" class="contact-card">
                    <span class="contact-icon">📧</span>
                    <h4>Email</h4>
                    <p>chrupesh2425@gmail.com</p>
                </a>
                <a href="https://www.linkedin.com/in/rupeshchidupudi/" class="contact-card" target="_blank">
                    <span class="contact-icon">💼</span>
                    <h4>LinkedIn</h4>
                    <p>Connect & Network</p>
                </a>
                <a href="https://github.com/chidupudi" class="contact-card" target="_blank">
                    <span class="contact-icon">🐱</span>
                    <h4>GitHub</h4>
                    <p>View Projects</p>
                </a>
                <a href="https://rupeshchidupudi.dev" class="contact-card" target="_blank">
                    <span class="contact-icon">🌐</span>
                    <h4>Portfolio</h4>
                    <p>Explore Work</p>
                </a>
            </div>
            
            <div style="margin-top: 60px; padding: 30px; background: rgba(255, 255, 255, 0.05); border-radius: 20px; border: 1px solid rgba(255, 255, 255, 0.1);">
                <h3 style="color: #64ffda; margin-bottom: 20px;">💡 Open for Opportunities</h3>
                <p style="color: #b0b8c5; line-height: 1.8;">
                    I'm passionate about creating end-to-end solutions that combine cutting-edge technology with real-world impact. Whether it's building scalable web applications, implementing AI-driven features, setting up robust DevOps pipelines, or architecting complete systems from scratch - I bring a holistic approach to every project.
                </p>
                <p style="color: #64ffda; font-weight: 600; margin-top: 20px;">
                    🚀 Full-time positions • 💼 Freelance projects • 🤝 Open source collaborations • 💬 Tech discussions
                </p>
            </div>
        </section>
    </div>

    <script>
        // Typing animation
        const texts = [
            "🚀 Full Stack Developer | Building Scalable Solutions",
            "💡 Problem Solver | Clean Code Enthusiast", 
            "🌟 Open Source Contributor | Always Learning",
            "⚡ Consistent Coder | 350+ Days Active This Year",
            "🔥 Daily Commit Streak | Building Habits That Last",
            "🎯 1,200+ Quality Commits | Consistency Breeds Excellence",
            "🤖 AI Integration Specialist | Smart Solutions",
            "☁️ DevOps Engineer | End-to-End Deployment",
            "📈 96% Year Coverage | Showing Up Every Day",
            "🏆 15+ Technologies Mastered | Through Daily Practice"
        ];
        
        let currentText = 0;
        let currentChar = 0;
        let isDeleting = false;
        
        function typeWriter() {
            const typingElement = document.getElementById('typingText');
            const text = texts[currentText];
            
            if (isDeleting) {
                typingElement.textContent = text.substring(0, currentChar - 1);
                currentChar--;
            } else {
                typingElement.textContent = text.substring(0, currentChar + 1);
                currentChar++;
            }
            
            if (!isDeleting && currentChar === text.length) {
                isDeleting = true;
                setTimeout(typeWriter, 2000);
            } else if (isDeleting && currentChar === 0) {
                isDeleting = false;
                currentText = (currentText + 1) % texts.length;
                setTimeout(typeWriter, 500);
            } else {
                setTimeout(typeWriter, isDeleting ? 50 : 100);
            }
        }
        
        // Start typing animation
        typeWriter();
        
        // Animate skill bars on scroll
        function animateSkillBars() {
            const skillBars = document.querySelectorAll('.skill-progress');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const width = entry.target.getAttribute('data-width');
                        entry.target.style.width = width;
                    }
                });
            }, { threshold: 0.5 });
            
            skillBars.forEach(bar => observer.observe(bar));
        }
        
        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                
                const size = Math.random() * 3 + 1;
                const left = Math.random() * 100;
                const delay = Math.random() * 6;
                
                particle.style.width = size + 'px';
                particle.style.height = size + 'px';
                particle.style.left = left + '%';
                particle.style.animationDelay = delay + 's';
                particle.style.opacity = Math.random() * 0.5 + 0.2;
                
                particlesContainer.appendChild(particle);
            }
        }
        
        // Initialize animations
        document.addEventListener('DOMContentLoaded', () => {
            animateSkillBars();
            createParticles();
            initializeLiveTracker();
        });

        // Live tracker animations
        function initializeLiveTracker() {
            const stats = [
                { id: 'currentStreak', values: ['350+', '351+', '352+'], colors: ['#64ffda'] },
                { id: 'todayCommits', values: ['✅', '🔥', '💪'], colors: ['#ff6b6b'] },
                { id: 'weeklyAvg', values: ['8.5', '8.7', '8.9'], colors: ['#feca57'] },
                { id: 'consistency', values: ['96%', '96.1%', '96.2%'], colors: ['#48dbfb'] },
                { id: 'totalCommits', values: ['1.2K+', '1.21K+', '1.22K+'], colors: ['#ff9ff3'] },
                { id: 'longestStreak', values: ['87', '87', '88'], colors: ['#74b9ff'] }
            ];

            stats.forEach((stat, index) => {
                setInterval(() => {
                    const element = document.getElementById(stat.id);
                    if (element) {
                        const randomValue = stat.values[Math.floor(Math.random() * stat.values.length)];
                        element.style.transform = 'scale(1.1)';
                        element.style.transition = 'transform 0.3s ease';
                        setTimeout(() => {
                            element.textContent = randomValue;
                            element.style.transform = 'scale(1)';
                        }, 150);
                    }
                }, 8000 + (index * 2000)); // Stagger the animations
            });

            // Animate the live stats on load
            setTimeout(() => {
                document.querySelectorAll('.live-stat').forEach((stat, index) => {
                    stat.style.animation = `float 3s ease-in-out infinite`;
                    stat.style.animationDelay = `${index * 0.2}s`;
                });
            }, 1000);
        }
        
        // Smooth scrolling for internal links
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
    </script>
</body>
</html>
