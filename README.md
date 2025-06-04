# Personal-Portfolio-Website_FS
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #3498db;
            --secondary-color: #2c3e50;
            --text-color: #333;
            --bg-color: #f9f9f9;
            --card-bg: #fff;
            --highlight-color: #3498db;
            --shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            --nav-bg: rgba(255, 255, 255, 0.9);
            --transition: all 0.3s ease;
        }

        .dark-mode {
            --primary-color: #3498db;
            --secondary-color: #f8f9fa;
            --text-color: #f8f9fa;
            --bg-color: #121212;
            --card-bg: #1e1e1e;
            --highlight-color: #3498db;
            --shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            --nav-bg: rgba(30, 30, 30, 0.9);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            transition: var(--transition);
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background-color: var(--nav-bg);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary-color);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 500;
            transition: var(--transition);
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
            background: var(--primary-color);
            bottom: -5px;
            left: 0;
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .theme-toggle {
            background: none;
            border: none;
            color: var(--text-color);
            font-size: 20px;
            cursor: pointer;
            margin-left: 20px;
            transition: var(--transition);
        }

        .theme-toggle:hover {
            color: var(--primary-color);
        }

        section {
            padding: 100px 0;
        }

        .home {
            display: flex;
            align-items: left;
            min-height: 100vh;
            padding-top: 80px;
        }

        .home-content {
            flex: 1;
            padding-right: 40px;
        }

        .home-image {
            flex: 1;
            display: flex;
            justify-content: flex-end; /* Align image to the right */
            align-items: center;
        }

        .home-image img {
            max-width: 350px;
            width: 100%;
            height: auto;
            border-radius: 20px;
            box-shadow: var(--shadow);
            object-fit: cover;
            aspect-ratio: 1/1;
        }

        h1 {
            font-size: 40px;
            margin-bottom: 20px;
            color: var(--text-color);
        }

        .highlight {
            color: var(--highlight-color);
            font-weight: 600;
        }

        p {
            margin-bottom: 30px;
            font-size: 18px;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            margin-right: 15px;
            cursor: pointer;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--primary-color);
            color: var(--primary-color);
        }

        .btn-outline:hover {
            background-color: var(--primary-color);
            color: white;
        }

        .about {
            background-color: var(--card-bg);
            border-radius: 20px;
            padding: 60px;
            box-shadow: var(--shadow);
        }

        .about-content {
            display: flex;
            align-items: center;
        }

        .about-text {
            flex: 1;
            padding-left: 40px;
        }

        .about-image {
            flex: 1;
            text-align: center;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .about-image img {
            max-width: 350px;
            width: 100%;
            height: auto;
            border-radius: 20px;
            box-shadow: var(--shadow);
            object-fit: cover;
            aspect-ratio: 1/1;
        }

        .skills {
            text-align: center;
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .skill-category {
            background-color: var(--card-bg);
            padding: 30px;
            border-radius: 15px;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .skill-category:hover {
            transform: translateY(-10px);
        }

        .skill-category h3 {
            margin-bottom: 20px;
            color: var(--primary-color);
        }

        .skill-list {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
        }

        .skill-item {
            background-color: var(--primary-color);
            color: white;
            padding: 8px 15px;
            border-radius: 50px;
            font-size: 14px;
        }

        .contact {
            background-color: var(--card-bg);
            border-radius: 20px;
            padding: 60px;
            box-shadow: var(--shadow);
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 25px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            background-color: var(--card-bg);
            color: var(--text-color);
            transition: var(--transition);
        }

        .form-group input:focus,
        .form-group textarea:focus {
            border-color: var(--primary-color);
            outline: none;
        }

        .form-group textarea {
            resize: vertical;
            min-height: 150px;
        }

        .submit-btn {
            width: 100%;
            padding: 15px;
            font-size: 16px;
        }

        footer {
            text-align: center;
            padding: 30px 0;
            background-color: var(--card-bg);
            margin-top: 50px;
        }

        .social-links {
            margin-bottom: 20px;
        }

        .social-links a {
            display: inline-block;
            margin: 0 10px;
            color: var(--text-color);
            font-size: 20px;
            transition: var(--transition);
        }

        .social-links a:hover {
            color: var(--primary-color);
            transform: translateY(-3px);
        }

        @media (max-width: 768px) {
            .home {
                flex-direction: column;
            }
            
            .home-content,
            .about-text {
                padding-right: 0;
                padding-left: 0;
                margin-bottom: 40px;
            }

            .home,
            .about-content {
                flex-direction: column;
            }

            .nav-links {
                display: none;
            }

            h1 {
                font-size: 36px;
            }

            section {
                padding: 60px 0;
            }

            .about,
            .contact {
                padding: 30px;
            }

            .home-image {
                justify-content: center;
            }

            .home-image img,
            .about-image img {
                max-width: 280px;
            }
        }

        @media (max-width: 480px) {
            .home-image img,
            .about-image img {
                max-width: 220px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <nav>
                <div class="logo">Keerthi Bandaru</div>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <button class="theme-toggle" id="themeToggle">
                    <i class="fas fa-moon"></i>
                </button>
            </nav>
        </div>
    </header>

    <section id="home" class="home">
        <div class="container">
            <div class="home-content">
                <h1>Hi, I'm <span class="highlight">Keerthi</span><br>I'm Web Developer</h1>
                <p>Welcome to my web developer portfolio! I'm Keerthi, a skilled and creative web developer with a passion for creating beautiful, responsive, and user-friendly websites.</p>
                <div class="buttons">
                    <a href="#contact" class="btn">Hire Me</a>
                    <a href="#contact" class="btn btn-outline">Contact</a>
                </div>
            </div>
            <div class="home-image">
                <img src="profile.jpg" alt="Keerthi's Photo">
            </div>
        </div>
    </section>

    <section id="about" class="section">
        <div class="container">
            <div class="about">
                <div class="about-content">
                    <div class="about-image">
                        <img src="profile.jpg" alt="Keerthi's Photo">
                    </div>
                    <div class="about-text">
                        <h2>About <span class="highlight">Me</span></h2>
                        <p>I'm a passionate <span class="highlight">Web Developer</span> with a strong interest in creating dynamic and responsive websites. With experience in frontend development, I specialize in building modern user interfaces that are both functional and visually appealing. I love transforming ideas into real-world digital experiences.</p>
                        <p>Currently pursuing B.Tech and constantly learning new tools and technologies to grow as a full-stack developer.</p>
                        <p>Skilled in <span class="highlight">HTML, CSS, JavaScript, and React</span>. Currently pursuing my B.Tech and actively enhancing my skills to become a full-stack developer.</p>
                        <a href="#contact" class="btn">Contact Me</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="skills" class="skills section">
        <div class="container">
            <h2>My <span class="highlight">Skills</span></h2>
            <div class="skills-container">
                <div class="skill-category">
                    <h3>Programming Languages</h3>
                    <div class="skill-list">
                        <span class="skill-item">C/C++</span>
                        <span class="skill-item">Java</span>
                        <span class="skill-item">Python</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3>Web Development</h3>
                    <div class="skill-list">
                        <span class="skill-item">HTML</span>
                        <span class="skill-item">CSS</span>
                        <span class="skill-item">JavaScript</span>
                        <span class="skill-item">React</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3>Languages</h3>
                    <div class="skill-list">
                        <span class="skill-item">Telugu</span>
                        <span class="skill-item">Hindi</span>
                        <span class="skill-item">English</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3>Soft Skills</h3>
                    <div class="skill-list">
                        <span class="skill-item">Creativity</span>
                        <span class="skill-item">Leadership</span>
                        <span class="skill-item">Problem Solving</span>
                        <span class="skill-item">Teamwork</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="section">
        <div class="container">
            <div class="contact">
                <h2>Contact <span class="highlight">Me</span></h2>
                <form class="contact-form" id="contactForm">
                    <div class="form-group">
                        <label for="name">Full Name</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="phone">Phone Number</label>
                        <input type="tel" id="phone" name="phone" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Your Message</label>
                        <textarea id="message" name="message" required></textarea>
                    </div>
                    <button type="submit" class="btn submit-btn">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="social-links">
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-linkedin"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
            </div>
            <p>&copy; 2023-2027</p>
        </div>
    </footer>

    <script>
        // Theme Toggle
        const themeToggle = document.getElementById('themeToggle');
        const body = document.body;
        const icon = themeToggle.querySelector('i');

        // Check for saved user preference, if any
        const currentTheme = localStorage.getItem('theme');
        if (currentTheme) {
            body.classList.add(currentTheme);
            if (currentTheme === 'dark-mode') {
                icon.classList.remove('fa-moon');
                icon.classList.add('fa-sun');
            }
        }

        themeToggle.addEventListener('click', () => {
            body.classList.toggle('dark-mode');
            
            if (body.classList.contains('dark-mode')) {
                icon.classList.remove('fa-moon');
                icon.classList.add('fa-sun');
                localStorage.setItem('theme', 'dark-mode');
            } else {
                icon.classList.remove('fa-sun');
                icon.classList.add('fa-moon');
                localStorage.setItem('theme', '');
            }
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

        // Form submission
        const contactForm = document.getElementById('contactForm');
        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form values
            const name = document.getElementById('name').value;
            const phone = document.getElementById('phone').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;
            
            // Here you would typically send the data to a server
            console.log({ name, phone, email, message });
            
            // Show success message
            alert('Thank you for your message! I will get back to you soon.');
            
            // Reset form
            contactForm.reset();
        });
    </script>
</body>
</html>
