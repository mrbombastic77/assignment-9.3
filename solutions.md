HTML
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Landing Page — Grid & Flexbox</title>
    <meta name="description" content="A modern responsive landing page combining CSS Grid for macro-layout and Flexbox for micro-alignment.">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="page-layout">
        <!-- Header & Navigation (Flexbox) -->
        <header class="site-header">
            <div class="header-container">
                <div class="logo">
                    <a href="#">DevScale</a>
                </div>
                <nav class="nav-menu">
                    <ul class="nav-links">
                        <li><a href="#hero" class="active">Home</a></li>
                        <li><a href="#features">Features</a></li>
                        <li><a href="#solutions">Solutions</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </nav>
                <div class="header-action">
                    <a href="#contact" class="btn btn-primary">Get Started</a>
                </div>
            </div>
        </header>

        <!-- Main Container (CSS Grid Structure) -->
        <main class="site-main">
            <!-- Hero Section (Flexbox & Grid Integration) -->
            <section id="hero" class="hero-section">
                <div class="hero-container">
                    <div class="hero-text">
                        <span class="badge">Next-Gen Architecture</span>
                        <h1>Scale Your Web Applications with Confidence</h1>
                        <p>Combine the power of CSS Grid and Flexbox to build blazing-fast, perfectly aligned, and fully responsive user interfaces.</p>
                        <div class="hero-buttons">
                            <a href="#features" class="btn btn-primary btn-lg">Explore Features</a>
                            <a href="#contact" class="btn btn-outline btn-lg">Documentation</a>
                        </div>
                    </div>
                    <div class="hero-image-wrapper">
                        <img src="images/hero-illustration.jpg" alt="Developer illustration showing CSS layout systems" class="hero-img">
                    </div>
                </div>
            </section>

            <!-- Features Section (CSS Grid Layout + Flexbox Cards) -->
            <section id="features" class="features-section">
                <div class="section-header">
                    <h2>Engineered for Modern Developers</h2>
                    <p>Discover the core capabilities that make our framework lightweight and adaptable.</p>
                </div>
                <div class="features-grid">
                    <!-- Feature Card 1 -->
                    <div class="feature-card">
                        <div class="card-icon">⚡</div>
                        <div class="card-content">
                            <h3>Grid Macro Layouts</h3>
                            <p>Define robust two-dimensional layouts with named areas and auto-fit columns effortlessly.</p>
                        </div>
                    </div>
                    <!-- Feature Card 2 -->
                    <div class="feature-card">
                        <div class="card-icon">🎯</div>
                        <div class="card-content">
                            <h3>Flexbox Micro Alignment</h3>
                            <p>Perfect vertical and horizontal distribution for component internals and navigation bars.</p>
                        </div>
                    </div>
                    <!-- Feature Card 3 -->
                    <div class="feature-card">
                        <div class="card-icon">📱</div>
                        <div class="card-content">
                            <h3>Mobile-First Scaling</h3>
                            <p>Progressive enhancement ensuring flawless viewing across mobile, tablet, and desktop viewports.</p>
                        </div>
                    </div>
                </div>
            </section>
        </main>

        <!-- Footer -->
        <footer id="contact" class="site-footer">
            <div class="footer-container">
                <div class="footer-info">
                    <h3>DevScale</h3>
                    <p>Department of Computer Science Engineering, Invertis University, Bareilly</p>
                </div>
                <ul class="footer-links">
                    <li><a href="#hero">Home</a></li>
                    <li><a href="#features">Features</a></li>
                    <li><a href="https://github.com/AtimAkhtar" target="_blank" rel="noopener">GitHub</a></li>
                </ul>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2026 Atim Akhtar. All rights reserved.</p>
            </div>
        </footer>
    </div>
</body>
</html>
CSS
/* style.css — Mobile-First Responsive Design */
:root {
    --primary-color: #0284c7;
    --primary-hover: #0369a1;
    --secondary-color: #0f172a;
    --bg-color: #f8fafc;
    --surface-color: #ffffff;
    --text-color: #334155;
    --text-muted: #64748b;
    --border-color: #e2e8f0;
    
    --space-sm: 8px;
    --space-md: 16px;
    --space-lg: 24px;
    --space-xl: 40px;
    
    --radius-md: 8px;
    --radius-lg: 12px;
    --shadow-sm: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    --shadow-md: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-color);
    line-height: 1.6;
}

/* Macro Page Layout using CSS Grid */
.page-layout {
    display: grid;
    min-height: 100vh;
    grid-template-rows: auto 1fr auto;
    grid-template-columns: 1fr;
}

/* Header & Navigation (Flexbox) */
.site-header {
    background-color: var(--secondary-color);
    color: var(--surface-color);
    padding: var(--space-md) var(--space-lg);
    position: sticky;
    top: 0;
    z-index: 1000;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.header-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: var(--space-md);
}

.logo a {
    font-size: 1.25rem;
    font-weight: bold;
    color: var(--surface-color);
    text-decoration: none;
}

.nav-menu {
    display: none; /* Hidden on mobile by default, expanded via media query */
}

.nav-links {
    list-style: none;
    display: flex;
    gap: var(--space-lg);
}

.nav-links a {
    color: #94a3b8;
    text-decoration: none;
    font-weight: 500;
    font-size: 0.95rem;
    transition: color 0.2s ease;
}

.nav-links a:hover,
.nav-links a.active {
    color: #38bdf8;
}

.header-action {
    display: flex;
    align-items: center;
}

/* Main Content Area */
.site-main {
    display: flex;
    flex-direction: column;
    gap: 4rem;
    padding: 2rem 0;
}

/* Hero Section (Flexbox Alignment) */
.hero-section {
    padding: 0 var(--space-md);
}

.hero-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 2.5rem;
    align-items: center;
}

.hero-text {
    text-align: center;
    max-width: 600px;
}

.badge {
    display: inline-block;
    background-color: #e0f2fe;
    color: var(--primary-color);
    font-size: 0.75rem;
    font-weight: bold;
    padding: 4px 12px;
    border-radius: 20px;
    text-transform: uppercase;
    margin-bottom: var(--space-md);
}

.hero-text h1 {
    font-size: clamp(2rem, 5vw, 2.75rem);
    color: var(--secondary-color);
    line-height: 1.2;
    margin-bottom: var(--space-md);
}

.hero-text p {
    font-size: 1.05rem;
    color: var(--text-muted);
    margin-bottom: var(--space-lg);
}

.hero-buttons {
    display: flex;
    justify-content: center;
    gap: var(--space-md);
    flex-wrap: wrap;
}

.hero-image-wrapper {
    width: 100%;
    max-width: 520px;
    background-color: var(--border-color);
    border-radius: var(--radius-lg);
    overflow: hidden;
    box-shadow: var(--shadow-md);
}

.hero-img {
    width: 100%;
    height: auto;
    display: block;
    object-fit: cover;
}

/* Features Section (CSS Grid + Flexbox Cards) */
.features-section {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 var(--space-md);
    width: 100%;
}

.section-header {
    text-align: center;
    margin-bottom: 2.5rem;
}

.section-header h2 {
    font-size: 1.75rem;
    color: var(--secondary-color);
    margin-bottom: 0.5rem;
}

.section-header p {
    color: var(--text-muted);
    font-size: 1rem;
}

/* CSS Grid for Feature Cards */
.features-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: var(--space-lg);
}

/* Flexbox inside Feature Cards */
.feature-card {
    background-color: var(--surface-color);
    border: 1px solid var(--border-color);
    border-radius: var(--radius-lg);
    padding: var(--space-lg);
    box-shadow: var(--shadow-sm);
    display: flex;
    align-items: flex-start;
    gap: var(--space-md);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.feature-card:hover {
    transform: translateY(-3px);
    box-shadow: var(--shadow-md);
}

.card-icon {
    font-size: 2rem;
    background-color: #f1f5f9;
    padding: var(--space-sm);
    border-radius: var(--radius-md);
    flex-shrink: 0;
}

.card-content {
    display: flex;
    flex-direction: column;
    gap: 4px;
}

.card-content h3 {
    font-size: 1.15rem;
    color: var(--secondary-color);
}

.card-content p {
    font-size: 0.9rem;
    color: var(--text-muted);
}

/* Footer Section */
.site-footer {
    background-color: var(--secondary-color);
    color: var(--surface-color);
    padding: 3rem var(--space-md) 1.5rem var(--space-md);
    border-top: 1px solid var(--border-color);
}

.footer-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: var(--space-lg);
    padding-bottom: 2rem;
    border-bottom: 1px solid #1e293b;
}

.footer-info h3 {
    font-size: 1.25rem;
    margin-bottom: 4px;
}

.footer-info p {
    color: var(--text-muted);
    font-size: 0.875rem;
}

.footer-links {
    list-style: none;
    display: flex;
    gap: var(--space-lg);
}

.footer-links a {
    color: var(--text-muted);
    text-decoration: none;
    font-size: 0.95rem;
    transition: color 0.2s ease;
}

.footer-links a:hover {
    color: var(--surface-color);
}

.footer-bottom {
    max-width: 1200px;
    margin: 1.5rem auto 0 auto;
    text-align: center;
    color: var(--text-muted);
    font-size: 0.875rem;
}

/* Buttons */
.btn {
    padding: 0.6rem 1.25rem;
    font-size: 0.95rem;
    font-weight: bold;
    border-radius: var(--radius-md);
    text-decoration: none;
    cursor: pointer;
    transition: background-color 0.2s ease;
    display: inline-block;
    text-align: center;
    border: none;
}

.btn-primary {
    background-color: var(--primary-color);
    color: var(--surface-color);
}

.btn-primary:hover {
    background-color: var(--primary-hover);
}

.btn-outline {
    background-color: transparent;
    border: 1px solid var(--border-color);
    color: var(--secondary-color);
}

.btn-outline:hover {
    background-color: #f1f5f9;
    border-color: var(--text-muted);
}

.btn-lg {
    padding: 0.75rem 1.5rem;
    font-size: 1rem;
}


/* ==========================================
   Media Queries (Desktop / Tablet Upgrades)
   ================================---------- */
@media (min-width: 768px) {
    .nav-menu {
        display: block;
    }

    .hero-container {
        flex-direction: row;
        justify-content: space-between;
        text-align: left;
    }

    .hero-text {
        text-align: left;
    }

    .hero-buttons {
        justify-content: flex-start;
    }

    .features-grid {
        grid-template-columns: repeat(3, 1fr);
    }

    .feature-card {
        flex-direction: column;
        align-items: flex-start;
    }

    .footer-container {
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }
}