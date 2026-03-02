<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Velvet Bean Cafe | Aesthetic Coffee Experience</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Lato:wght@300;400;500&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #8B7355;
            --secondary: #D4C4B7;
            --accent: #C9A86C;
            --dark: #2C2C2C;
            --light: #FAF8F5;
            --cream: #F5F0EB;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Lato', sans-serif;
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(250, 248, 245, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            padding: 1rem 5%;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
            letter-spacing: 2px;
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 400;
            font-size: 0.95rem;
            letter-spacing: 1px;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 1px;
            background: var(--primary);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(rgba(0,0,0,0.3), rgba(0,0,0,0.3)),
                        url('https://images.unsplash.com/photo-1509042239860-f550ce710b93?w=1920') center/cover;
            position: relative;
        }

        .hero-content {
            color: white;
            max-width: 800px;
            padding: 2rem;
            animation: fadeInUp 1s ease;
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

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 4.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            letter-spacing: 3px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            font-weight: 300;
            letter-spacing: 2px;
        }

        .btn {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: var(--primary);
            color: white;
            text-decoration: none;
            font-size: 0.9rem;
            letter-spacing: 2px;
            transition: all 0.3s ease;
            border: 2px solid var(--primary);
        }

        .btn:hover {
            background: transparent;
            color: white;
            border-color: white;
        }

        .btn-outline {
            background: transparent;
            color: var(--primary);
            border-color: var(--primary);
            margin-left: 1rem;
        }

        .btn-outline:hover {
            background: var(--primary);
            color: white;
        }

        /* About Section */
        .about {
            padding: 8rem 5%;
            background: var(--cream);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .about-image {
            position: relative;
        }

        .about-image img {
            width: 100%;
            height: 600px;
            object-fit: cover;
            border-radius: 10px;
        }

        .about-image::before {
            content: '';
            position: absolute;
            top: -20px;
            left: -20px;
            width: 100%;
            height: 100%;
            border: 3px solid var(--primary);
            border-radius: 10px;
            z-index: -1;
        }

        .about-text h2 {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 1.5rem;
        }

        .about-text p {
            margin-bottom: 1.5rem;
            color: #666;
            font-size: 1.1rem;
        }

        .signature {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            color: var(--primary);
            margin-top: 2rem;
        }

        /* Menu Section */
        .menu {
            padding: 8rem 5%;
            background: var(--light);
        }

        .section-title {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-title h2 {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 1rem;
        }

        .section-title p {
            color: #888;
            font-style: italic;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .menu-item {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            transition: transform 0.3s ease;
        }

        .menu-item:hover {
            transform: translateY(-10px);
        }

        .menu-item-image {
            height: 250px;
            background-size: cover;
            background-position: center;
        }

        .menu-item-content {
            padding: 2rem;
        }

        .menu-item h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.5rem;
            color: var(--dark);
            margin-bottom: 0.5rem;
        }

        .menu-item p {
            color: #888;
            margin-bottom: 1rem;
            font-size: 0.95rem;
        }

        .menu-item .price {
            font-size: 1.3rem;
            color: var(--primary);
            font-weight: 600;
        }

        /* Gallery Section */
        .gallery {
            padding: 8rem 5%;
            background: var(--dark);
        }

        .gallery .section-title h2,
        .gallery .section-title p {
            color: var(--light);
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .gallery-item {
            height: 300px;
            background-size: cover;
            background-position: center;
            border-radius: 10px;
            transition: transform 0.3s ease;
            cursor: pointer;
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        /* Testimonials */
        .testimonials {
            padding: 8rem 5%;
            background: var(--cream);
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .testimonial-card {
            background: white;
            padding: 2.5rem;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
        }

        .testimonial-card .stars {
            color: var(--accent);
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }

        .testimonial-card p {
            font-style: italic;
            color: #666;
            margin-bottom: 1.5rem;
        }

        .testimonial-card h4 {
            color: var(--primary);
            font-family: 'Playfair Display', serif;
        }

        /* Contact Section */
        .contact {
            padding: 8rem 5%;
            background: var(--light);
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .contact-info h2 {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 2rem;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .contact-item i {
            color: var(--primary);
            font-size: 1.5rem;
            margin-top: 0.3rem;
        }

        .contact-item h4 {
            color: var(--dark);
            margin-bottom: 0.3rem;
        }

        .contact-item p {
            color: #888;
        }

        .contact-form {
            background: white;
            padding: 3rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
        }

        .contact-form h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            color: var(--dark);
            margin-bottom: 2rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--dark);
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: 'Lato', sans-serif;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
        }

        .contact-form .btn {
            width: 100%;
            cursor: pointer;
            border: none;
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 4rem 5% 2rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            max-width: 1400px;
            margin: 0 auto;
            margin-bottom: 3rem;
        }

        .footer-section h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: var(--secondary);
        }

        .footer-section p,
        .footer-section a {
            color: #aaa;
            margin-bottom: 0.8rem;
            display: block;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-section a:hover {
            color: var(--primary);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            border: 1px solid #555;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            background: var(--primary);
            border-color: var(--primary);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid #444;
            color: #888;
        }

        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Responsive */
        @media (max-width: 968px) {
            .hero h1 {
                font-size: 3rem;
            }

            .about-content,
            .contact-content {
                grid-template-columns: 1fr;
            }

            .about-image::before {
                display: none;
            }

            .gallery-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .mobile-menu-btn {
                display: block;
            }

            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: var(--light);
                flex-direction: column;
                padding: 2rem;
                gap: 1.5rem;
            }

            .nav-links.active {
                display: flex;
            }
        }

        @media (max-width: 600px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .gallery-grid {
                grid-template-columns: 1fr;
            }

            .btn {
                display: block;
                margin: 0.5rem 0;
            }

            .btn-outline {
                margin-left: 0;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <a href="#" class="logo">VELVET BEAN</a>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#menu">Menu</a></li>
            <li><a href="#gallery">Gallery</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
        <div class="mobile-menu-btn">
            <i class="fas fa-bars"></i>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>VELVET BEAN CAFE</h1>
            <p>Where Every Cup Tells a Story</p>
            <a href="#menu" class="btn">Explore Menu</a>
            <a href="#contact" class="btn btn-outline">Visit Us</a>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="about-content">
            <div class="about-image">
                <img src="https://images.unsplash.com/photo-1554118811-1e0d58224f24?w=800" alt="Cozy Cafe Interior">
            </div>
            <div class="about-text">
                <h2>Our Story</h2>
                <p>Welcome to Velvet Bean Cafe, where passion meets perfection in every cup. Founded in 2018, we've been serving the finest artisanal coffee in a warm, inviting atmosphere that feels like home.</p>
                <p>Our beans are ethically sourced from sustainable farms around the world, roasted to perfection in-house, and crafted by our skilled baristas who pour their hearts into every beverage.</p>
                <p>More than just a coffee shop, we're a community space where friends gather, ideas flow, and memories are made over the aroma of freshly brewed coffee.</p>
                <div class="signature">Maria Chen</div>
                <p style="font-size: 0.9rem; color: #888;">Founder & Coffee Enthusiast</p>
