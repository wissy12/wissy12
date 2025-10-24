<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tomás Andrade - Ingeniero en Informática</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --success: #2ecc71;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f9f9f9;
            color: #333;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header y Navegación */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: var(--shadow);
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            display: flex;
            align-items: center;
        }

        .logo i {
            margin-right: 10px;
            animation: rotate 10s linear infinite;
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        .nav-links a:hover {
            color: var(--light);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: var(--light);
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(44, 62, 80, 0.8), rgba(52, 152, 219, 0.8)), url('https://images.unsplash.com/photo-1517077304055-6e89abbf09b0?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            height: 100vh;
            display: flex;
            align-items: center;
            color: white;
            text-align: center;
            padding-top: 60px;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            animation: fadeIn 1.5s ease;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
        }

        .btn {
            display: inline-block;
            background-color: var(--accent);
            color: white;
            padding: 0.8rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            box-shadow: var(--shadow);
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            background-color: #c0392b;
        }

        /* Secciones generales */
        section {
            padding: 5rem 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary);
            display: inline-block;
            position: relative;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            width: 70%;
            height: 4px;
            background: linear-gradient(to right, var(--secondary), var(--accent));
            bottom: -10px;
            left: 15%;
            border-radius: 2px;
        }

        /* Sobre Mí */
        .about {
            background-color: white;
        }

        .about-content {
            display: flex;
            align-items: center;
            gap: 3rem;
        }

        .about-img {
            flex: 1;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            animation: float 3s ease-in-out infinite;
        }

        .about-img img {
            width: 100%;
            height: auto;
            display: block;
            transition: var(--transition);
        }

        .about-img:hover img {
            transform: scale(1.05);
        }

        .about-text {
            flex: 2;
        }

        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        .highlight {
            color: var(--secondary);
            font-weight: 600;
        }

        /* Habilidades */
        .skills {
            background-color: var(--light);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-card {
            background-color: white;
            border-radius: 10px;
            padding: 2rem;
            text-align: center;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to right, var(--secondary), var(--accent));
        }

        .skill-icon {
            font-size: 3rem;
            color: var(--secondary);
            margin-bottom: 1rem;
        }

        .skill-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        /* Proyectos */
        .projects {
            background-color: white;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .project-img {
            height: 200px;
            overflow: hidden;
        }

        .project-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .project-card:hover .project-img img {
            transform: scale(1.1);
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-content h3 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: var(--primary);
        }

        .project-content p {
            margin-bottom: 1rem;
            color: #666;
        }

        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .tech-tag {
            background-color: var(--light);
            color: var(--primary);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        /* Contacto */
        .contact {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            text-align: center;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            transition: var(--transition);
        }

        .contact-item:hover {
            transform: translateY(-5px);
        }

        .contact-icon {
            font-size: 2rem;
            color: var(--light);
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
            text-align: left;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 0.8rem 1rem;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
            box-shadow: var(--shadow);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 2rem 0;
            text-align: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            font-size: 1.5rem;
            transition: var(--transition);
        }

        .social-link:hover {
            background-color: var(--secondary);
            transform: translateY(-5px);
        }

        /* Animaciones */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .about-content {
                flex-direction: column;
            }

            .skills-grid, .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header y Navegación -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">
                    <i class="fas fa-code"></i>
                    <span>Tomás Andrade</span>
                </div>
                <ul class="nav-links">
                    <li><a href="#about">Sobre Mí</a></li>
                    <li><a href="#skills">Habilidades</a></li>
                    <li><a href="#projects">Proyectos</a></li>
                    <li><a href="#contact">Contacto</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Tomás Andrade Pérez</h1>
                <p>Ingeniero en Informática | Desarrollador Full Stack</p>
                <p>Búsqueda de Práctica Profesional</p>
                <a href="#contact" class="btn">Contáctame</a>
            </div>
        </div>
    </section>

    <!-- Sobre Mí -->
    <section id="about" class="about">
        <div class="container">
            <div class="section-title">
                <h2>Sobre Mí</h2>
            </div>
            <div class="about-content">
                <div class="about-img">
                    <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=634&q=80" alt="Tomás Andrade">
                </div>
                <div class="about-text">
                    <h3>Ingeniero en Informática en formación</h3>
                    <p>Soy un profesional <span class="highlight">responsable, ordenado, autodidacta</span> y entusiasta por las nuevas tecnologías, con fuerte motivación por aprender continuamente. Me destaco en el trabajo colaborativo y el desarrollo de soluciones digitales aplicadas a necesidades reales, combinando conocimientos técnicos con habilidades prácticas en proyectos informáticos.</p>
                    <p>Mi objetivo es integrarme a un equipo de trabajo en el área de tecnologías de la información donde pueda aplicar y fortalecer mis conocimientos en informática, adquirir más experiencia, colaborar activamente en proyectos tecnológicos y desarrollarme tanto profesional como personalmente.</p>
                    <p><span class="highlight">Disponibilidad inmediata</span> para prácticas profesionales en cualquier modalidad.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Habilidades -->
    <section id="skills" class="skills">
        <div class="container">
            <div class="section-title">
                <h2>Habilidades Técnicas</h2>
            </div>
            <div class="skills-grid">
                <div class="skill-card fade-in">
                    <div class="skill-icon">
                        <i class="fab fa-python"></i>
                    </div>
                    <h3>Python</h3>
                    <p>Desarrollo backend, análisis de datos y automatización</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">
                        <i class="fab fa-js"></i>
                    </div>
                    <h3>JavaScript</h3>
                    <p>Desarrollo frontend y backend con Node.js</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">
                        <i class="fas fa-database"></i>
                    </div>
                    <h3>MySQL & SQL</h3>
                    <p>Diseño y gestión de bases de datos</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">
                        <i class="fab fa-php"></i>
                    </div>
                    <h3>PHP</h3>
                    <p>Desarrollo web backend con Laravel</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">
                        <i class="fab fa-java"></i>
                    </div>
                    <h3>Java</h3>
                    <p>Desarrollo de aplicaciones empresariales</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">
                        <i class="fab fa-react"></i>
                    </div>
                    <h3>React & Vue.js</h3>
                    <p>Frameworks modernos para desarrollo frontend</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">
                        <i class="fab fa-microsoft"></i>
                    </div>
                    <h3>.NET & C#</h3>
                    <p>Desarrollo de aplicaciones Windows</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">
                        <i class="fas fa-network-wired"></i>
                    </div>
                    <h3>Redes</h3>
                    <p>Cisco Packet Tracer, configuración de redes</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Proyectos -->
    <section id="projects" class="projects">
        <div class="container">
            <div class="section-title">
                <h2>Proyectos Destacados</h2>
            </div>
            <div class="projects-grid">
                <div class="project-card fade-in">
                    <div class="project-img">
                        <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80" alt="App Web de Inventario">
                    </div>
                    <div class="project-content">
                        <h3>App Web de Inventario - Empresa Apeco</h3>
                        <p>Creación de un sistema web para gestión de inventario y análisis de datos con diseño de interfaz, conexión con base de datos y funcionalidades CRUD.</p>
                        <div class="tech-tags">
                            <span class="tech-tag">HTML</span>
                            <span class="tech-tag">CSS</span>
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">MySQL</span>
                            <span class="tech-tag">Python</span>
                        </div>
                    </div>
                </div>
                <div class="project-card fade-in">
                    <div class="project-img">
                        <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80" alt="App Web Líneas Adentu">
                    </div>
                    <div class="project-content">
                        <h3>App Web Líneas - Empresa ADENTU</h3>
                        <p>Plataforma tecnológica para mejorar la gestión de fallas y priorizar intervenciones en líneas de transmisión eléctrica.</p>
                        <div class="tech-tags">
                            <span class="tech-tag">HTML</span>
                            <span class="tech-tag">CSS</span>
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">PHP</span>
                            <span class="tech-tag">MySQL</span>
                            <span class="tech-tag">Azure</span>
                        </div>
                        <a href="https://lineas.adentu.cloud/" class="btn" target="_blank">Ver Proyecto</a>
                    </div>
                </div>
                <div class="project-card fade-in">
                    <div class="project-img">
                        <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80" alt="App Web Fondeo">
                    </div>
                    <div class="project-content">
                        <h3>App Web Fondeo - Empresa ADENTU</h3>
                        <p>App Web para inspecciones con ROV Submarinos a embarcaciones, líneas de fondeo, muertos, centros de cultivos, etc.</p>
                        <div class="tech-tags">
                            <span class="tech-tag">HTML</span>
                            <span class="tech-tag">CSS</span>
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">PHP</span>
                            <span class="tech-tag">MySQL</span>
                            <span class="tech-tag">Azure</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contacto -->
    <section id="contact" class="contact">
        <div class="container">
            <div class="section-title">
                <h2>Contacto</h2>
            </div>
            <div class="contact-info">
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fas fa-map-marker-alt"></i>
                    </div>
                    <div>
                        <h3>Dirección</h3>
                        <p>Chinquihue, Puerto Montt</p>
                        <p>"Disponible para trasladarme"</p>
                    </div>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fas fa-phone"></i>
                    </div>
                    <div>
                        <h3>Teléfono</h3>
                        <p>+56 9 9992 5688</p>
                    </div>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fas fa-envelope"></i>
                    </div>
                    <div>
                        <h3>Email</h3>
                        <p>toomas.andrade09@gmail.com</p>
                    </div>
                </div>
            </div>
            <div class="contact-form">
                <form id="contactForm">
                    <div class="form-group">
                        <label for="name">Nombre</label>
                        <input type="text" id="name" class="form-control" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" class="form-control" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Mensaje</label>
                        <textarea id="message" class="form-control" required></textarea>
                    </div>
                    <button type="submit" class="btn">Enviar Mensaje</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="social-links">
                <a href="#" class="social-link">
                    <i class="fab fa-github"></i>
                </a>
                <a href="#" class="social-link">
                    <i class="fab fa-linkedin"></i>
                </a>
                <a href="#" class="social-link">
                    <i class="fab fa-twitter"></i>
                </a>
            </div>
            <p>&copy; 2023 Tomás Andrade Pérez. Todos los derechos reservados.</p>
        </div>
    </footer>

    <script>
        // Animación de scroll para elementos con clase fade-in
        const fadeElements = document.querySelectorAll('.fade-in');
        
        const fadeInOnScroll = () => {
            fadeElements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                
                if (elementTop < windowHeight - 100) {
                    element.classList.add('visible');
                }
            });
        };

        // Ejecutar al cargar y al hacer scroll
        window.addEventListener('scroll', fadeInOnScroll);
        window.addEventListener('load', fadeInOnScroll);

        // Smooth scroll para enlaces de navegación
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Manejo del formulario de contacto
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('¡Gracias por tu mensaje! Me pondré en contacto contigo pronto.');
            this.reset();
        });
    </script>
</body>
</html>
