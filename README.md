# Task4
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Muqaddas Imtiaz - Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">

    <style>
        /* General Body & Root Styles */
        :root {
            --primary-color: #BB86FC; /* A light purple for accents */
            --secondary-color: #03DAC6; /* A teal for secondary accents */
            --background-dark: #121212; /* Very dark grey for background */
            --surface-dark: #1F1F1F; /* Slightly lighter dark grey for cards/surfaces */
            --text-light: #E0E0E0; /* Light grey for main text */
            --text-medium: #A0A0A0; /* Medium grey for secondary text */
            --text-heading: #FFFFFF; /* White for main headings */
            --gradient-start: rgba(0, 0, 0, 0.7);
            --gradient-end: rgba(0, 0, 0, 0.9);
            --shadow-color: rgba(0, 0, 0, 0.3);
            --border-color: #333333;
        }

        body {
            font-family: 'Roboto', sans-serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            line-height: 1.6;
            color: var(--text-light);
            background-color: var(--background-dark);
            scroll-behavior: smooth; /* Smooth scrolling for nav links */
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        section {
            padding: 100px 0; /* More padding for distinct sections */
            overflow: hidden;
            position: relative; /* For background effects */
        }

        /* Reusable Components */
        .card {
            background-color: var(--surface-dark);
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 8px 16px var(--shadow-color);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            text-align: center;
            border: 1px solid var(--border-color);
        }

        .card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 24px rgba(0, 0, 0, 0.5);
        }

        .section-heading {
            font-size: 3em;
            color: var(--text-heading);
            margin-bottom: 20px;
            text-align: center;
            position: relative;
            padding-bottom: 10px;
            font-weight: 700;
        }

        .section-heading::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: var(--primary-color);
            margin: 15px auto 0;
            border-radius: 2px;
        }

        /* Header Styles */
        .header {
            background-color: rgba(18, 18, 18, 0.9); /* Slightly transparent dark */
            padding: 15px 0; /* Adjusted padding for header */
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px var(--shadow-color);
            backdrop-filter: blur(5px); /* Blurred effect */
        }

        .header .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo {
            display: flex; /* For aligning image and potential text */
            align-items: center;
            text-decoration: none;
            color: var(--primary-color); /* Fallback color for text if no image */
            font-size: 1.8em;
            font-weight: 700;
        }

        .logo img {
            height: 45px; /* Adjust height as needed for your logo */
            margin-right: 10px;
            vertical-align: middle;
        }
        /* If you want text next to the logo, uncomment the span in HTML and add style here */
        /* .logo span {
            color: var(--text-heading);
        } */


        .main-nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
            flex-wrap: wrap;
            justify-content: center; /* Center nav items on smaller screens */
        }

        .main-nav ul li {
            margin: 0 15px;
        }

        .main-nav ul li a {
            text-decoration: none;
            color: var(--text-light);
            font-weight: 500;
            transition: color 0.3s ease, border-bottom 0.3s ease;
            padding: 5px 0;
        }

        .main-nav ul li a:hover {
            color: var(--primary-color);
            border-bottom: 2px solid var(--primary-color);
        }

        /* Home Section */
        .home-section {
            /* Replace 'placeholder-bg.jpg' with your actual background image */
            background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.9)), url('placeholder-bg.jpg') center/cover no-repeat;
            background-blend-mode: multiply; /* Darkens the image */
            min-height: 100vh; /* Full viewport height */
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--text-heading);
            position: relative;
        }

        .home-content h1 {
            font-size: 4.5em;
            margin-bottom: 10px;
            font-weight: 700;
            letter-spacing: 2px;
            background: -webkit-linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: textGlow 1.5s infinite alternate;
        }

        @keyframes textGlow {
            from { text-shadow: 0 0 5px var(--primary-color); }
            to { text-shadow: 0 0 15px var(--primary-color), 0 0 20px var(--secondary-color); }
        }

        .home-content p {
            font-size: 1.8em;
            font-weight: 300;
            color: var(--text-medium);
        }

        /* About Me Section */
        .about-section {
            background-color: var(--background-dark);
            text-align: center;
        }

        .about-content p {
            font-size: 1.15em;
            max-width: 800px;
            margin: 0 auto;
            color: var(--text-light);
            line-height: 1.8;
            text-align: justify;
        }
        .about-content p strong {
            color: var(--primary-color);
        }

        /* Education Section */
        .education-section {
            background-color: var(--surface-dark);
        }

        .education-content {
            max-width: 800px;
            margin: 0 auto;
            color: var(--text-light);
        }

        .education-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 30px;
            padding: 20px;
            border-left: 5px solid var(--primary-color);
            background-color: var(--background-dark);
            border-radius: 8px;
            box-shadow: 0 4px 8px var(--shadow-color);
        }

        .education-item:last-child {
            margin-bottom: 0;
        }

        .education-icon {
            font-size: 2.5em;
            color: var(--secondary-color);
            margin-right: 25px;
            margin-top: 5px; /* Align icon better with text */
        }

        .education-details h3 {
            font-size: 1.8em;
            color: var(--primary-color);
            margin-top: 0;
            margin-bottom: 10px;
            font-weight: 500;
        }

        .education-details p {
            margin: 0 0 8px 0;
            font-size: 1.05em;
            color: var(--text-light);
        }
        .education-details p strong {
            color: var(--text-heading);
        }

        /* Skills Section */
        .skills-section {
            background-color: var(--background-dark);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .skill-category h3 {
            font-size: 2em;
            color: var(--text-heading);
            margin-bottom: 25px;
            border-bottom: 2px solid var(--secondary-color);
            padding-bottom: 10px;
            display: inline-block; /* Make underline fit text */
        }

        .skill-list {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .skill-list li {
            background-color: var(--background-dark);
            padding: 15px 20px;
            margin-bottom: 15px;
            border-radius: 8px;
            text-align: left;
            display: flex;
            align-items: center;
            font-size: 1.1em;
            color: var(--text-light);
            border: 1px solid var(--border-color);
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            transition: background-color 0.3s ease, color 0.3s ease;
        }

        .skill-list li:hover {
            background-color: var(--primary-color);
            color: var(--text-heading);
            border-color: var(--primary-color);
        }

        .skill-list li i {
            margin-right: 15px;
            color: var(--secondary-color);
            font-size: 1.3em;
        }
        .skill-list li:hover i {
             color: var(--text-heading);
        }
        
        .soft-skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 20px;
        }

        .soft-skill-card {
            background-color: var(--surface-dark);
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 4px 8px var(--shadow-color);
            text-align: center;
            border: 1px solid var(--border-color);
            transition: background-color 0.3s ease, color 0.3s ease, transform 0.3s ease;
        }

        .soft-skill-card:hover {
            background-color: var(--secondary-color);
            color: var(--background-dark);
            transform: translateY(-5px);
        }

        .soft-skill-card i {
            font-size: 2.5em;
            color: var(--primary-color);
            margin-bottom: 15px;
        }
        .soft-skill-card:hover i {
            color: var(--background-dark);
        }

        .soft-skill-card h4 {
            font-size: 1.3em;
            color: var(--text-heading);
            margin: 0;
        }
        .soft-skill-card:hover h4 {
            color: var(--background-dark);
        }

        /* Projects Section */
        .projects-section {
            background-color: var(--surface-dark);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            margin-top: 50px;
        }

        .project-card {
            background-color: var(--background-dark);
            border-radius: 12px;
            padding: 30px;
            box-shadow: 0 8px 20px var(--shadow-color);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            border: 1px solid var(--border-color);
            text-align: left; /* Align text within card to left */
        }
        
        .project-card .project-image {
            width: 100%;
            height: 200px; /* Fixed height for consistency */
            overflow: hidden;
            border-radius: 8px;
            margin-bottom: 20px;
            border: 1px solid var(--border-color);
        }

        .project-card .project-image img {
            width: 100%;
            height: 100%;
            object-fit: cover; /* Cover the area, crop if needed */
            display: block;
            transition: transform 0.3s ease;
        }

        .project-card:hover .project-image img {
            transform: scale(1.05); /* Slight zoom on hover */
        }

        .project-card h3 {
            font-size: 2em;
            color: var(--primary-color);
            margin-top: 0;
            margin-bottom: 15px;
        }

        .project-card p {
            font-size: 1em;
            color: var(--text-light);
            margin-bottom: 20px;
            flex-grow: 1; /* Allows description to take available space */
        }

        .project-tech {
            font-size: 0.9em;
            color: var(--text-medium);
            font-style: italic;
            margin-top: 15px;
            border-top: 1px solid var(--border-color);
            padding-top: 15px;
        }

        /* Contact Section */
        .contact-section {
            background-color: var(--background-dark);
            text-align: center;
        }

        .contact-info {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 40px;
            margin-bottom: 60px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            color: var(--text-light);
            font-size: 1.1em;
        }

        .contact-item i {
            font-size: 1.8em;
            color: var(--primary-color);
            margin-right: 15px;
        }
        
        .social-icons {
            margin-top: 30px;
        }

        .social-icons a {
            color: var(--text-light);
            font-size: 2em;
            margin: 0 15px;
            transition: color 0.3s ease;
        }

        .social-icons a:hover {
            color: var(--primary-color);
        }

        .contact-form-container {
            max-width: 700px;
            margin: 0 auto;
            background-color: var(--surface-dark);
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 8px 16px var(--shadow-color);
            border: 1px solid var(--border-color);
        }

        .contact-form label {
            display: block;
            text-align: left;
            margin-bottom: 8px;
            color: var(--text-light);
            font-weight: 500;
        }

        .contact-form input[type="text"],
        .contact-form input[type="email"],
        .contact-form textarea {
            width: calc(100% - 20px); /* Account for padding */
            padding: 12px 10px;
            margin-bottom: 20px;
            border: 1px solid var(--border-color);
            border-radius: 5px;
            background-color: var(--background-dark);
            color: var(--text-light);
            font-size: 1em;
            box-sizing: border-box; /* Include padding in width */
        }
        
        .contact-form input[type="text"]:focus,
        .contact-form input[type="email"]:focus,
        .contact-form textarea:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 2px rgba(187, 134, 252, 0.3);
        }

        .contact-form textarea {
            resize: vertical;
            min-height: 120px;
        }

        .contact-form button {
            background-color: var(--primary-color);
            color: var(--background-dark);
            border: none;
            padding: 15px 30px;
            border-radius: 5px;
            font-size: 1.1em;
            font-weight: 700;
            cursor: pointer;
            transition: background-color 0.3s ease, color 0.3s ease;
        }

        .contact-form button:hover {
            background-color: var(--secondary-color);
            color: var(--background-dark);
        }

        /* Testimonials/Comments Section (Optional) */
        .testimonials-section {
            background-color: var(--surface-dark);
            text-align: center;
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            margin-top: 50px;
        }

        .testimonial-card {
            background-color: var(--background-dark);
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 4px 8px var(--shadow-color);
            text-align: left;
            font-style: italic;
            color: var(--text-light);
            border: 1px solid var(--border-color);
        }

        .testimonial-card p {
            margin-bottom: 15px;
            line-height: 1.7;
        }

        .testimonial-author {
            font-weight: 700;
            color: var(--primary-color);
            font-style: normal;
        }

        /* Footer */
        .footer {
            background-color: var(--background-dark);
            color: var(--text-medium);
            text-align: center;
            padding: 30px 20px;
            font-size: 0.9em;
            border-top: 1px solid var(--border-color);
        }
        
        .footer .contact-details {
            margin-top: 20px;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px 30px; /* Row gap and column gap */
            margin-bottom: 20px;
        }

        .footer .contact-details div {
            display: flex;
            align-items: center;
            color: var(--text-light);
        }

        .footer .contact-details i {
            margin-right: 8px;
            color: var(--primary-color);
            font-size: 1.1em;
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .header .container {
                flex-direction: column;
                align-items: center;
            }
            .main-nav {
                margin-top: 20px;
                width: 100%;
            }
            .main-nav ul {
                flex-direction: column;
                align-items: center;
            }
            .main-nav ul li {
                margin: 8px 0;
            }

            .home-content h1 {
                font-size: 3.5em;
            }
            .home-content p {
                font-size: 1.5em;
            }
            
            .section-heading {
                font-size: 2.5em;
            }

            .about-content p {
                font-size: 1em;
            }

            .education-item {
                flex-direction: column;
                align-items: center;
                text-align: center;
            }
            .education-icon {
                margin-right: 0;
                margin-bottom: 15px;
            }
            .education-details h3, .education-details p {
                text-align: center;
            }
            .education-item {
                border-left: none;
                border-top: 5px solid var(--primary-color);
            }

            .skills-grid, .projects-grid, .testimonials-grid {
                grid-template-columns: 1fr; /* Stack columns on smaller screens */
            }

            .skill-category h3 {
                text-align: center;
                display: block;
            }
            .skill-list li {
                justify-content: center; /* Center content in skill list items */
            }
            
            .soft-skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            }

            .contact-info {
                flex-direction: column;
                align-items: center;
                gap: 25px;
            }
            .contact-item {
                font-size: 1em;
            }
            .contact-item i {
                font-size: 1.5em;
            }
        }

        @media (max-width: 600px) {
            section {
                padding: 60px 0;
            }
            .section-heading {
                font-size: 2em;
            }
            .home-content h1 {
                font-size: 2.8em;
            }
            .home-content p {
                font-size: 1.2em;
            }

            .card {
                padding: 20px;
            }

            .skill-list li {
                font-size: 1em;
                padding: 12px 15px;
            }
            .skill-list li i {
                font-size: 1.1em;
                margin-right: 10px;
            }

            .contact-form-container {
                padding: 25px;
            }
            .contact-form input, .contact-form textarea {
                padding: 10px;
                font-size: 0.9em;
            }

            .project-card .project-image {
                height: 180px; /* Slightly smaller height on very small screens */
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <div class="container">
            <a href="#home" class="logo">
                <img src="companylogo.jpeg" alt="CoreTech Innovations Logo"> 
                </a>
            <nav class="main-nav">
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#about">About Me</a></li>
                    <li><a href="#education">Education</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <main>
        <section id="home" class="home-section">
            <div class="container home-content">
                <h1>Muqaddas Imtiaz</h1>
                <p>Aspiring Data Scientist & Programmer</p>
            </div>
        </section>

        <section id="about" class="about-section">
            <div class="container">
                <h2 class="section-heading">About Me</h2>
                <div class="about-content">
                    <p>
                        Hi! I'm <strong>Muqaddas Imtiaz</strong>, a passionate and hardworking student of BS Data Science at a reputable university in Pakistan. I love learning new technologies and improving my skills every day. I am exploring the world of web development, programming, and data science to build a strong career. My goal is to become self-independent, support my family, and contribute to the tech world as a confident, hijabi woman in STEM. I am currently 19 years old.
                    </p>
                </div>
            </div>
        </section>

        <section id="education" class="education-section">
            <div class="container">
                <h2 class="section-heading">Education</h2>
                <div class="education-content">
                    <div class="education-item">
                        <div class="education-icon"><i class="fas fa-graduation-cap"></i></div>
                        <div class="education-details">
                            <h3>Bachelor of Science in Data Science</h3>
                            <p><strong>University:</strong> Currently enrolled</p>
                            <p><strong>Year:</strong> Ongoing</p>
                            <p>Also selected for Python and Video Editing internships with <strong>Digital Empowerment Pakistan</strong>.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="skills" class="skills-section">
            <div class="container">
                <h2 class="section-heading">Skills</h2>
                <div class="skills-grid">
                    <div class="card skill-category">
                        <h3><i class="fas fa-code"></i> Programming Languages</h3>
                        <ul class="skill-list">
                            <li><i class="fab fa-python"></i> Python</li>
                            <li><i class="fab fa-java"></i> Java</li>
                            <li><i class="fas fa-c"></i> C</li>
                            <li><i class="fab fa-html5"></i> HTML</li>
                            <li><i class="fab fa-css3-alt"></i> CSS</li>
                            <li><i class="fab fa-js-square"></i> JavaScript (Basic)</li>
                            <li><i class="fas fa-database"></i> MySQL</li>
                        </ul>
                    </div>

                    <div class="card skill-category">
                        <h3><i class="fas fa-toolbox"></i> Tools & Technologies</h3>
                        <ul class="skill-list">
                            <li><i class="fab fa-git-alt"></i> Git & GitHub</li>
                            <li><i class="fas fa-laptop-code"></i> Visual Studio Code</li>
                            <li><i class="fas fa-paint-brush"></i> Canva</li>
                            <li><i class="fas fa-file-word"></i> Microsoft Word / PowerPoint</li>
                            <li><i class="fas fa-crop-alt"></i> Screenshot Editing & PDF Tools</li>
                            <li><i class="fas fa-file-alt"></i> Google Forms (Basic use)</li>
                        </ul>
                    </div>
                    
                    <div class="card skill-category">
                        <h3><i class="fas fa-handshake"></i> Soft Skills</h3>
                        <div class="soft-skills-grid">
                            <div class="soft-skill-card">
                                <i class="fas fa-bolt"></i>
                                <h4>Hardworking</h4>
                            </div>
                            <div class="soft-skill-card">
                                <i class="fas fa-brain"></i>
                                <h4>Fast Learner</h4>
                            </div>
                            <div class="soft-skill-card">
                                <i class="fas fa-clock"></i>
                                <h4>Time Management</h4>
                            </div>
                            <div class="soft-skill-card">
                                <i class="fas fa-people-group"></i>
                                <h4>Team Collaboration</h4>
                            </div>
                            <div class="soft-skill-card">
                                <i class="fas fa-search"></i>
                                <h4>Detail-Oriented</h4>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="projects" class="projects-section">
            <div class="container">
                <h2 class="section-heading">Projects</h2>
                <div class="projects-grid">
                    <div class="card project-card">
                        <div class="project-image">
                            <img src="ecommerce.jpeg" alt="Glamour Wardrobe Project Screenshot"> 
                        </div>
                        <h3>Glamour Wardrobe</h3>
                        <p>An e-commerce style website using HTML and CSS. Contains Home, Shop, About, and Contact sections. Designed for an online clothing store with product cards and a clean layout.</p>
                        <p class="project-tech">Tech Used: HTML, CSS</p>
                    </div>
                    <div class="card project-card">
                        <div class="project-image">
                            <img src="portfolio.jpeg" alt="Muqaddas Portfolio Website Screenshot"> 
                        </div>
                        <h3>Muqaddas Portfolio Website</h3>
                        <p>A personal portfolio built using HTML and CSS. Sections include About, Skills, Projects, and Contact. Uses dark theme and background blur for a modern look.</p>
                        <p class="project-tech">Tech Used: HTML, CSS</p>
                    </div>
                    <div class="card project-card">
                        <div class="project-image">
                            <img src="Redbluenimgame.jpeg" alt="Red Blue Nim Game Screenshot"> 
                        </div>
                        <h3>Red Blue Nim Game</h3>
                        <p>A Python terminal game created as part of an internship. Features player input and random pile generation. Part of Digital Empowerment Pakistan’s programming task.</p>
                        <p class="project-tech">Tech Used: Python</p>
                    </div>
                    <div class="card project-card">
                        <div class="project-image">
                            <img src="task2.jpeg" alt="Two-Page Responsive Task Screenshot"> 
                        </div>
                        <h3>Two-Page Responsive Task</h3>
                        <p>A web engineering task with an “Introduction” and “Skills” page. Responsive layout for desktop and mobile. Custom styles and clear sectioning.</p>
                        <p class="project-tech">Tech Used: HTML, CSS</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact" class="contact-section">
            <div class="container">
                <h2 class="section-heading">Contact</h2>
                <div class="contact-info">
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i> imtiazmuskan525@gmail.com
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i> Pakistan
                    </div>
                </div>
                <div class="social-icons">
                    <a href="https://github.com/Muqadas-g" target="_blank" aria-label="GitHub Profile"><i class="fab fa-github"></i></a>
                    <a href="https://www.linkedin.com/in/muqaddas-imtiaz-5635b0301?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app" target="_blank" aria-label="LinkedIn Profile"><i class="fab fa-linkedin-in"></i></a>
                </div>

                <div class="contact-form-container">
                    <h3 style="color: var(--text-heading); margin-bottom: 30px; font-size: 1.8em;">Send Me a Message</h3>
                    <form class="contact-form">
                        <label for="name">Name:</label>
                        <input type="text" id="name" name="name" required>

                        <label for="email">Email:</label>
                        <input type="email" id="email" name="email" required>

                        <label for="message">Message:</label>
                        <textarea id="message" name="message" required></textarea>

                        <button type="submit">Send Message</button>
                    </form>
                </div>
            </div>
        </section>

        <section id="testimonials" class="testimonials-section">
            <div class="container">
                <h2 class="section-heading">Testimonials / Comments</h2>
                <p style="text-align: center; color: var(--text-medium); margin-bottom: 40px;">(This section is for future comments and feedback)</p>
                <div class="testimonials-grid">
                    <div class="card testimonial-card">
                        <p>"Muqaddas is a highly dedicated and quick learner. Her passion for technology is truly inspiring!"</p>
                        <div class="testimonial-author">- Mentor's Name</div>
                    </div>
                    <div class="card testimonial-card">
                        <p>"A very detail-oriented and collaborative team member. Excited to see her grow in the tech industry."</p>
                        <div class="testimonial-author">- Colleague's Name</div>
                    </div>
                    <div class="card testimonial-card">
                        <p>"Her commitment to learning new skills is commendable. Muqaddas has a bright future ahead!"</p>
                        <div class="testimonial-author">- Professor's Name</div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer class="footer">
        <div class="container">
            <p>&copy; 2023 Muqaddas Imtiaz. All rights reserved.</p>
            <div class="contact-details">
                <div><i class="fas fa-envelope"></i> <strong>My Email:</strong> imtiazmuskan525@gmail.com</div>
                <div><i class="fas fa-phone-alt"></i> <strong>My Contact:</strong> 03313014709</div>
                <div><i class="fas fa-envelope"></i> <strong>CoreTech Innovations Email:</strong> hr@coretechio.com</div>
                <div><i class="fas fa-phone-alt"></i> <strong>CoreTech Innovations Contact:</strong> 03091800187</div>
            </div>
        </div>
    </footer>
</body>
</html>
