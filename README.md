<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cytruszek84 | Photography</title>

    <meta name="description" content="Cytruszek84 Photography – fotografia krajobrazowa, natura, góry, miasta, mgły, światło i wyjątkowe chwile.">
    <meta name="theme-color" content="#f7f5f0">

    <!-- Google Analytics -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-83HTNWWCL"></script>
    <script>
        window.dataLayer = window.dataLayer || [];
        function gtag() { dataLayer.push(arguments); }
        gtag("js", new Date());
        gtag("config", "G-83HTNWWCL");
    </script>

    <!-- Firebase -->
    <script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-firestore-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-analytics-compat.js"></script>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background: #f7f5f0;
            color: #1f2933;
            font-family: Inter, "Segoe UI", Arial, sans-serif;
            min-height: 100vh;
            overflow-x: hidden;
        }

        button, a {
            font-family: inherit;
        }

        img {
            max-width: 100%;
        }

        :root {
            --cream: #f7f5f0;
            --white: #ffffff;
            --dark: #20252b;
            --text: #30363d;
            --muted: #747b83;
            --gold: #b8893d;
            --green: #657765;
            --border: rgba(32, 37, 43, .10);
            --shadow: 0 15px 50px rgba(31, 35, 40, .09);
            --shadow-hover: 0 25px 70px rgba(31, 35, 40, .16);
            --radius: 20px;
        }

        /* =========================
           HEADER
        ========================= */
        header {
            position: sticky;
            top: 0;
            z-index: 100;
            background: rgba(247, 245, 240, .94);
            backdrop-filter: blur(18px);
            -webkit-backdrop-filter: blur(18px);
            border-bottom: 1px solid var(--border);
        }

        .nav {
            max-width: 1250px;
            margin: auto;
            min-height: 78px;
            padding: 0 25px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 30px;
        }

        .brand {
            border: none;
            background: transparent;
            cursor: pointer;
            text-align: left;
        }

        .brand-name {
            display: block;
            color: var(--dark);
            font-family: Georgia, serif;
            font-size: 1.55rem;
            letter-spacing: .08em;
            font-weight: 700;
        }

        .brand-sub {
            display: block;
            margin-top: 2px;
            color: var(--gold);
            font-size: .67rem;
            letter-spacing: .25em;
            text-transform: uppercase;
        }

        .main-menu {
            display: flex;
            align-items: center;
            gap: 7px;
        }

        .nav-btn {
            border: none;
            background: transparent;
            color: #555d64;
            padding: 10px 14px;
            border-radius: 10px;
            cursor: pointer;
            font-size: .9rem;
            font-weight: 600;
            transition: .25s ease;
        }

        .nav-btn:hover,
        .nav-btn.active {
            background: #ebe7df;
            color: var(--dark);
        }

        .languages {
            display: flex;
            gap: 5px;
            border-left: 1px solid var(--border);
            padding-left: 15px;
        }

        .lang-btn {
            border: none;
            background: transparent;
            color: #777;
            cursor: pointer;
            padding: 7px 8px;
            border-radius: 8px;
            font-size: .75rem;
            font-weight: 700;
            transition: .2s;
        }

        .lang-btn:hover,
        .lang-btn.active {
            background: var(--dark);
            color: white;
        }

        /* =========================
           HERO
        ========================= */
        .hero {
            max-width: 1250px;
            margin: 0 auto;
            padding: 80px 25px 65px;
            display: grid;
            grid-template-columns: minmax(0, 1.1fr) minmax(350px, .9fr);
            align-items: center;
            gap: 70px;
        }

        .hero-label {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            color: var(--gold);
            text-transform: uppercase;
            font-size: .72rem;
            letter-spacing: .25em;
            font-weight: 800;
            margin-bottom: 20px;
        }

        .hero-label::before {
            content: "";
            width: 35px;
            height: 1px;
            background: var(--gold);
        }

        .hero h1 {
            font-family: Georgia, serif;
            font-size: clamp(3rem, 6vw, 5.5rem);
            line-height: .98;
            font-weight: 500;
            color: var(--dark);
            margin-bottom: 28px;
        }

        .hero h1 span {
            color: var(--gold);
            font-style: italic;
        }

        .hero-text {
            max-width: 650px;
            color: var(--muted);
            font-size: 1.05rem;
            line-height: 1.8;
            margin-bottom: 30px;
        }

        .hero-actions {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .primary-btn,
        .secondary-btn {
            border-radius: 50px;
            padding: 14px 24px;
            cursor: pointer;
            font-weight: 700;
            transition: .25s ease;
        }

        .primary-btn {
            border: 1px solid var(--dark);
            background: var(--dark);
            color: white;
        }

        .primary-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 30px rgba(32, 37, 43, .2);
        }

        .secondary-btn {
            border: 1px solid #d7d2c9;
            background: transparent;
            color: var(--dark);
        }

        .secondary-btn:hover {
            background: white;
            transform: translateY(-2px);
        }

        .hero-visual {
            position: relative;
        }

        .hero-frame {
            position: relative;
            aspect-ratio: 4 / 5;
            overflow: hidden;
            border-radius: 30px;
            background: #d9d6cf;
            box-shadow: var(--shadow);
            transform: rotate(2deg);
        }

        .hero-frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .hero-frame::after {
            content: "";
            position: absolute;
            inset: 0;
            background: linear-gradient(180deg, transparent 55%, rgba(0,0,0,.25));
            pointer-events: none;
        }

        .hero-badge {
            position: absolute;
            z-index: 5;
            left: -25px;
            bottom: 35px;
            background: white;
            padding: 18px 22px;
            border-radius: 15px;
            box-shadow: var(--shadow);
            transform: rotate(-3deg);
        }

        .hero-badge strong {
            display: block;
            font-family: Georgia, serif;
            font-size: 1.2rem;
            color: var(--dark);
        }

        .hero-badge span {
            color: var(--muted);
            font-size: .75rem;
        }

        /* =========================
           SECTIONS & FOLDERS
        ========================= */
        .section {
            max-width: 1250px;
            margin: 0 auto;
            padding: 65px 25px;
        }

        .section-heading {
            margin-bottom: 35px;
        }

        .section-label {
            color: var(--gold);
            text-transform: uppercase;
            letter-spacing: .22em;
            font-size: .7rem;
            font-weight: 800;
            margin-bottom: 10px;
        }

        .section-heading h2 {
            color: var(--dark);
            font-family: Georgia, serif;
            font-size: clamp(2rem, 4vw, 3rem);
            font-weight: 500;
        }

        .section-heading p {
            max-width: 650px;
            margin-top: 12px;
            color: var(--muted);
            line-height: 1.7;
        }

        .folders-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 22px;
        }

        .folder-card {
            position: relative;
            min-height: 225px;
            border-radius: var(--radius);
            background: white;
            border: 1px solid var(--border);
            cursor: pointer;
            overflow: hidden;
            box-shadow: 0 8px 25px rgba(31,35,40,.05);
            transition: transform .35s ease, box-shadow .35s ease;
        }

        .folder-card:hover {
            transform: translateY(-7px);
            box-shadow: var(--shadow-hover);
        }

        .folder-art {
            position: absolute;
            inset: 0;
            opacity: .9;
        }

        .folder-art::after {
            content: "";
            position: absolute;
            inset: 0;
            background: linear-gradient(180deg, transparent 25%, rgba(255,255,255,.8));
        }

        .folder-number {
            position: absolute;
            top: 20px;
            right: 20px;
            width: 38px;
            height: 38px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            background: rgba(255,255,255,.85);
            color: var(--dark);
            font-size: .75rem;
            font-weight: 800;
            z-index: 3;
        }

        .folder-info {
            position: absolute;
            left: 23px;
            right: 23px;
            bottom: 21px;
            z-index: 4;
        }

        .folder-title {
            color: var(--dark);
            font-family: Georgia, serif;
            font-size: 1.45rem;
            margin-bottom: 5px;
        }

        .folder-count {
            color: #70777e;
            font-size: .8rem;
        }

        .art-1 { background: linear-gradient(135deg, #dfe9ed, #9fb9bf); }
        .art-2 { background: linear-gradient(135deg, #d9d6ce, #b99f83); }
        .art-3 { background: linear-gradient(135deg, #dce7df, #9db5a4); }
        .art-4 { background: linear-gradient(135deg, #ded9d3, #aa9990); }
        .art-5 { background: linear-gradient(135deg, #e8dfce, #c89d66); }
        .art-6 { background: linear-gradient(135deg, #dedee8, #8e95a9); }

        /* =========================
           VIEWS & GALLERY GRID
        ========================= */
        #gallery-view,
        #about-view {
            display: none;
        }

        .gallery-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 20px;
            margin-bottom: 30px;
        }

        .back-btn {
            border: 1px solid #d7d2c9;
            background: white;
            color: var(--dark);
            padding: 11px 18px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 700;
            transition: .25s;
        }

        .back-btn:hover {
            background: var(--dark);
            color: white;
        }

        .gallery-title {
            font-family: Georgia, serif;
            font-size: 2rem;
            color: var(--dark);
        }

        .photo-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(270px, 1fr));
            gap: 18px;
        }

        .photo-card {
            position: relative;
            aspect-ratio: 4 / 3;
            overflow: hidden;
            border-radius: 15px;
            background: #e5e1da;
            cursor: pointer;
            box-shadow: 0 7px 22px rgba(31,35,40,.07);
            transition: transform .35s ease, box-shadow .35s ease;
        }

        .photo-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-hover);
        }

        .photo-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            transition: transform .6s ease;
        }

        .photo-card:hover img {
            transform: scale(1.035);
        }

        .photo-card::after {
            content: "© Cytruszek84";
            position: absolute;
            z-index: 4;
            right: 12px;
            bottom: 10px;
            color: rgba(255,255,255,.8);
            font-size: .65rem;
            letter-spacing: .08em;
            text-shadow: 0 1px 4px rgba(0,0,0,.7);
            pointer-events: none;
        }

        .photo-error {
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
            text-align: center;
            color: var(--muted);
            background: #e9e5de;
            aspect-ratio: 4 / 3;
            border-radius: 15px;
        }

        /* =========================
           ABOUT STYLES
        ========================= */
        .about-layout {
            display: grid;
            grid-template-columns: minmax(300px, .8fr) minmax(0, 1.2fr);
            gap: 70px;
            align-items: center;
        }

        .about-photo {
            position: relative;
            max-width: 450px;
            margin: auto;
            border-radius: 25px;
            overflow: hidden;
            background: #ddd;
            box-shadow: var(--shadow);
            transform: rotate(-1deg);
        }

        .about-photo img {
            width: 100%;
            aspect-ratio: 4 / 5;
            object-fit: cover;
            display: block;
        }

        .about-photo-label {
            position: absolute;
            bottom: 18px;
            left: 18px;
            background: rgba(255,255,255,.93);
            padding: 10px 16px;
            border-radius: 10px;
            font-size: .75rem;
            font-weight: 700;
            color: var(--dark);
        }

        .about-content h2 {
            font-family: Georgia, serif;
            color: var(--dark);
            font-size: 2.8rem;
            font-weight: 500;
            margin-bottom: 22px;
        }

        .about-content p {
            color: var(--muted);
            line-height: 1.85;
            margin-bottom: 16px;
            font-size: 1rem;
        }

        .about-signature {
            font-family: "Brush Script MT", cursive, sans-serif;
            font-size: 2rem;
            color: var(--gold);
            margin-top: 25px;
        }

        /* =========================
           MULTI-LANGUAGE CSS RULESETS
        ========================= */
        /* Default Language (PL) hides EN and DE blocks */
        [data-lang="en"],
        [data-lang="de"] {
            display: none;
        }

        /* When body class is 'lang-en' -> Hide PL and DE, show EN */
        body.lang-en [data-lang="pl"],
        body.lang-en [data-lang="de"] {
            display: none !important;
        }
        body.lang-en [data-lang="en"] {
            display: block !important;
        }
        body.lang-en inline[data-lang="en"],
        body.lang-en span[data-lang="en"],
        body.lang-en div.about-photo-label[data-lang="en"],
        body.lang-en h2[data-lang="en"] {
            display: block !important;
        }

        /* When body class is 'lang-de' -> Hide PL and EN, show DE */
        body.lang-de [data-lang="pl"],
        body.lang-de [data-lang="en"] {
            display: none !important;
        }
        body.lang-de [data-lang="de"] {
            display: block !important;
        }
        body.lang-de inline[data-lang="de"],
        body.lang-de span[data-lang="de"],
        body.lang-de div.about-photo-label[data-lang="de"],
        body.lang-de h2[data-lang="de"] {
            display: block !important;
        }

        /* =========================
           SOCIAL & FOOTER
        ========================= */
        .social-section {
            background: #ebe7df;
            border-top: 1px solid var(--border);
            border-bottom: 1px solid var(--border);
        }

        .social-box {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 30px;
        }

        .social-box h2 {
            font-family: Georgia, serif;
            font-weight: 500;
            font-size: 2rem;
            color: var(--dark);
        }

        .social-box p {
            color: var(--muted);
            margin-top: 7px;
        }

        .social-links {
            display: flex;
            gap: 10px;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            min-width: 135px;
            padding: 13px 18px;
            border-radius: 50px;
            background: var(--dark);
            color: white;
            text-decoration: none;
            font-size: .85rem;
            font-weight: 700;
            transition: .25s;
        }

        .social-link:hover {
            background: var(--gold);
            transform: translateY(-3px);
        }

        footer {
            background: #20252b;
            color: #aeb4b8;
            padding: 35px 25px;
            text-align: center;
        }

        .footer-brand {
            color: white;
            font-family: Georgia, serif;
            font-size: 1.35rem;
            margin-bottom: 8px;
        }

        .footer-copy {
            font-size: .8rem;
            margin-bottom: 7px;
        }

        .copyright {
            color: #d8a866;
            font-size: .75rem;
            margin-top: 12px;
        }

        /* =========================
           LIGHTBOX
        ========================= */
        #lightbox {
            display: none;
            position: fixed;
            inset: 0;
            z-index: 1000;
            background: rgba(17,19,21,.96);
            align-items: center;
            justify-content: center;
            padding: 30px;
        }

        #lightbox.show {
            display: flex;
        }

        #lightbox-img {
            max-width: 94vw;
            max-height: 88vh;
            object-fit: contain;
            border-radius: 8px;
            box-shadow: 0 30px 100px rgba(0,0,0,.5);
        }

        .lightbox-close {
            position: absolute;
            top: 20px;
            right: 25px;
            width: 45px;
            height: 45px;
            border: none;
            border-radius: 50%;
            background: rgba(255,255,255,.12);
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* =========================
           RESPONSIVE
        ========================= */
        @media (max-width: 900px) {
            .hero {
                grid-template-columns: 1fr;
                gap: 45px;
                padding-top: 55px;
            }

            .hero-visual {
                max-width: 500px;
                width: 90%;
                margin: auto;
            }

            .about-layout {
                grid-template-columns: 1fr;
                gap: 45px;
            }

            .about-photo {
                width: 90%;
            }

            .social-box {
                flex-direction: column;
                align-items: flex-start;
            }
        }

        @media (max-width: 700px) {
            .nav {
                flex-wrap: wrap;
                padding-top: 13px;
                padding-bottom: 13px;
                gap: 12px;
            }

            .main-menu {
                order: 3;
                width: 100%;
                justify-content: center;
            }

            .languages {
                margin-left: auto;
            }

            .hero {
                padding-left: 20px;
                padding-right: 20px;
            }

            .hero h1 {
                font-size: 3.2rem;
            }

            .hero-frame {
                transform: none;
            }

            .hero-badge {
                left: 15px;
            }

            .section {
                padding: 45px 20px;
            }

            .gallery-header {
                align-items: flex-start;
                flex-direction: column;
            }

            .photo-grid {
                grid-template-columns: repeat(2, minmax(0, 1fr));
                gap: 10px;
            }

            .social-links {
                width: 100%;
                flex-direction: column;
            }

            .social-link {
                width: 100%;
            }
        }

        @media (max-width: 430px) {
            .photo-grid {
                grid-template-columns: 1fr;
            }

            .folders-grid {
                grid-template-columns: 1fr;
            }

            .hero h1 {
                font-size: 2.8rem;
            }

            .brand-name {
                font-size: 1.25rem;
            }
        }
    </style>
</head>
<body class="lang-pl">

    <!-- HEADER -->
    <header>
        <div class="nav">
            <button class="brand" onclick="showView('home')">
                <span class="brand-name">CYTRUSZEK84</span>
                <span class="brand-sub" data-lang="pl">FOTOGRAFIA KRAJOBRAZOWA</span>
                <span class="brand-sub" data-lang="en">LANDSCAPE PHOTOGRAPHY</span>
                <span class="brand-sub" data-lang="de">LANDSCHAFTSFOTOGRAFIE</span>
            </button>

            <nav class="main-menu">
                <button class="nav-btn active" id="nav-home" onclick="showView('home')">
                    <span data-lang="pl">Główna</span>
                    <span data-lang="en">Home</span>
                    <span data-lang="de">Startseite</span>
                </button>
                <button class="nav-btn" id="nav-portfolio" onclick="showView('home'); document.getElementById('portfolio-sec').scrollIntoView({behavior:'smooth'});">
                    <span data-lang="pl">Portfolio</span>
                    <span data-lang="en">Portfolio</span>
                    <span data-lang="de">Portfolio</span>
                </button>
                <button class="nav-btn" id="nav-about" onclick="showView('about')">
                    <span data-lang="pl">O mnie</span>
                    <span data-lang="en">About Me</span>
                    <span data-lang="de">Über mich</span>
                </button>
            </nav>

            <div class="languages">
                <button class="lang-btn active" id="btn-pl" onclick="setLanguage('pl')">PL</button>
                <button class="lang-btn" id="btn-en" onclick="setLanguage('en')">EN</button>
                <button class="lang-btn" id="btn-de" onclick="setLanguage('de')">DE</button>
            </div>
        </div>
    </header>

    <!-- MAIN HOME VIEW -->
    <main id="home-view" class="view-section">
        <!-- HERO -->
        <section class="hero">
            <div class="hero-content">
                <div class="hero-label">
                    <span data-lang="pl">Fotografia Krajobrazowa</span>
                    <span data-lang="en">Landscape Photography</span>
                    <span data-lang="de">Landschaftsfotografie</span>
                </div>
                
                <h1 data-lang="pl">Chwytając <span>światło</span> i ulotne chwile.</h1>
                <h1 data-lang="en">Capturing <span>light</span> and fleeting moments.</h1>
                <h1 data-lang="de">Licht und <span>flüchtige</span> Momente einfangen.</h1>

                <p class="hero-text" data-lang="pl">Odkrywaj naturę, poranne mgły, górskie szczyty i miejskie pejzaże uchwycone w wyjątkowych kadrach.</p>
                <p class="hero-text" data-lang="en">Discover nature, morning mists, mountain peaks, and urban landscapes captured in unique frames.</p>
                <p class="hero-text" data-lang="de">Entdecken Sie die Natur, Morgennebel, Berggipfel und Stadtlandschaften in einzigartigen Bildern.</p>

                <div class="hero-actions">
                    <button class="primary-btn" onclick="document.getElementById('portfolio-sec').scrollIntoView({behavior: 'smooth'})">
                        <span data-lang="pl">Zobacz Galerię</span>
                        <span data-lang="en">View Gallery</span>
                        <span data-lang="de">Galerie Ansehen</span>
                    </button>
                    <button class="secondary-btn" onclick="showView('about')">
                        <span data-lang="pl">Poznaj Mnie</span>
                        <span data-lang="en">Meet Me</span>
                        <span data-lang="de">Über Mich</span>
                    </button>
                </div>
            </div>

            <div class="hero-visual">
                <div class="hero-frame">
                    <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=800&q=80" alt="Landscape Photo">
                </div>
                <div class="hero-badge">
                    <strong data-lang="pl">Natura & Pasja</strong>
                    <strong data-lang="en">Nature & Passion</strong>
                    <strong data-lang="de">Natur & Leidenschaft</strong>
                    <span>Cytruszek84 Photography</span>
                </div>
            </div>
        </section>

        <!-- FOLDERS / CATEGORIES SECTION -->
        <section id="portfolio-sec" class="section">
            <div class="section-heading">
                <div class="section-label" data-lang="pl">Kategorie</div>
                <div class="section-label" data-lang="en">Categories</div>
                <div class="section-label" data-lang="de">Kategorien</div>

                <h2 data-lang="pl">Galeria Zdjęć</h2>
                <h2 data-lang="en">Photo Gallery</h2>
                <h2 data-lang="de">Fotogalerie</h2>

                <p data-lang="pl">Wybierz kategorię, aby zobaczyć zebrane fotografie.</p>
                <p data-lang="en">Select a category to explore the collected photographs.</p>
                <p data-lang="de">Wählen Sie eine Kategorie, um die Fotosammlung zu erkunden.</p>
            </div>

            <div class="folders-grid">
                <!-- FOLDER 1 -->
                <div class="folder-card" onclick="openFolder('Krajobrazy')">
                    <div class="folder-art art-1"></div>
                    <div class="folder-number">01</div>
                    <div class="folder-info">
                        <div class="folder-title" data-lang="pl">Krajobrazy</div>
                        <div class="folder-title" data-lang="en">Landscapes</div>
                        <div class="folder-title" data-lang="de">Landschaften</div>

                        <div class="folder-count" data-lang="pl">Natura, mgły i poranki</div>
                        <div class="folder-count" data-lang="en">Nature, mists and mornings</div>
                        <div class="folder-count" data-lang="de">Natur, Nebel und Morgenstunden</div>
                    </div>
                </div>

                <!-- FOLDER 2 -->
                <div class="folder-card" onclick="openFolder('Góry')">
                    <div class="folder-art art-2"></div>
                    <div class="folder-number">02</div>
                    <div class="folder-info">
                        <div class="folder-title" data-lang="pl">Góry</div>
                        <div class="folder-title" data-lang="en">Mountains</div>
                        <div class="folder-title" data-lang="de">Berge</div>

                        <div class="folder-count" data-lang="pl">Szczyty i szlaki</div>
                        <div class="folder-count" data-lang="en">Peaks and trails</div>
                        <div class="folder-count" data-lang="de">Gipfel und Pfade</div>
                    </div>
                </div>

                <!-- FOLDER 3 -->
                <div class="folder-card" onclick="openFolder('Miasta')">
                    <div class="folder-art art-3"></div>
                    <div class="folder-number">03</div>
                    <div class="folder-info">
                        <div class="folder-title" data-lang="pl">Miasta</div>
                        <div class="folder-title" data-lang="en">Urban</div>
                        <div class="folder-title" data-lang="de">Städte</div>

                        <div class="folder-count" data-lang="pl">Architektura i światła nocą</div>
                        <div class="folder-count" data-lang="en">Architecture & night lights</div>
                        <div class="folder-count" data-lang="de">Architektur & Nachtlichter</div>
                    </div>
                </div>

                <!-- FOLDER 4 -->
                <div class="folder-card" onclick="openFolder('Zmierzch & Noc')">
                    <div class="folder-art art-4"></div>
                    <div class="folder-number">04</div>
                    <div class="folder-info">
                        <div class="folder-title" data-lang="pl">Zmierzch & Noc</div>
                        <div class="folder-title" data-lang="en">Dusk & Night</div>
                        <div class="folder-title" data-lang="de">Dämmerung & Nacht</div>

                        <div class="folder-count" data-lang="pl">Gwiazdy i smugi światła</div>
                        <div class="folder-count" data-lang="en">Stars and light trails</div>
                        <div class="folder-count" data-lang="de">Sterne und Lichtspuren</div>
                    </div>
                </div>

                <!-- FOLDER 5 -->
                <div class="folder-card" onclick="openFolder('Natura')">
                    <div class="folder-art art-5"></div>
                    <div class="folder-number">05</div>
                    <div class="folder-info">
                        <div class="folder-title" data-lang="pl">Natura</div>
                        <div class="folder-title" data-lang="en">Nature</div>
                        <div class="folder-title" data-lang="de">Natur</div>

                        <div class="folder-count" data-lang="pl">Flora i ujęcia makro</div>
                        <div class="folder-count" data-lang="en">Flora and macro shots</div>
                        <div class="folder-count" data-lang="de">Flora und Makroaufnahmen</div>
                    </div>
                </div>

                <!-- FOLDER 6 -->
                <div class="folder-card" onclick="openFolder('Woda')">
                    <div class="folder-art art-6"></div>
                    <div class="folder-number">06</div>
                    <div class="folder-info">
                        <div class="folder-title" data-lang="pl">Rzeki & Jeziora</div>
                        <div class="folder-title" data-lang="en">Rivers & Lakes</div>
                        <div class="folder-title" data-lang="de">Flüsse & Seen</div>

                        <div class="folder-count" data-lang="pl">Odbicia i żywioł wody</div>
                        <div class="folder-count" data-lang="en">Reflections and water elements</div>
                        <div class="folder-count" data-lang="de">Spiegelungen und Wasserelemente</div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- GALLERY VIEW (FULL GRID) -->
    <section id="gallery-view" class="section">
        <div class="gallery-header">
            <button class="back-btn" onclick="showView('home')">
                <span data-lang="pl">← Powrót do kategorii</span>
                <span data-lang="en">← Back to categories</span>
                <span data-lang="de">← Zurück zu den Kategorien</span>
            </button>
            <h2 id="gallery-category-title" class="gallery-title">Krajobrazy</h2>
        </div>

        <div class="photo-grid" id="photo-grid-container">
            <!-- Dynamic / Firebase Grid Items -->
            <div class="photo-card" onclick="openLightbox('https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=1600&q=80')">
                <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=600&q=80" alt="Landscape 1">
            </div>
            <div class="photo-card" onclick="openLightbox('https://images.unsplash.com/photo-1511884642898-4c92249e20b6?auto=format&fit=crop&w=1600&q=80')">
                <img src="https://images.unsplash.com/photo-1511884642898-4c92249e20b6?auto=format&fit=crop&w=600&q=80" alt="Landscape 2">
            </div>
            <div class="photo-card" onclick="openLightbox('https://images.unsplash.com/photo-1434725039720-aaad6dd32dfe?auto=format&fit=crop&w=1600&q=80')">
                <img src="https://images.unsplash.com/photo-1434725039720-aaad6dd32dfe?auto=format&fit=crop&w=600&q=80" alt="Landscape 3">
            </div>
            <div class="photo-card" onclick="openLightbox('https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&w=1600&q=80')">
                <img src="https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&w=600&q=80" alt="Landscape 4">
            </div>
            <div class="photo-card" onclick="openLightbox('https://images.unsplash.com/photo-1501785888041-af3ef285b470?auto=format&fit=crop&w=1600&q=80')">
                <img src="https://images.unsplash.com/photo-1501785888041-af3ef285b470?auto=format&fit=crop&w=600&q=80" alt="Landscape 5">
            </div>
            <div class="photo-card" onclick="openLightbox('https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?auto=format&fit=crop&w=1600&q=80')">
                <img src="https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?auto=format&fit=crop&w=600&q=80" alt="Landscape 6">
            </div>
        </div>
    </section>

    <!-- ABOUT VIEW SECTION (COMPLETE MULTI-LANGUAGE HTML BINDING) -->
    <section id="about-view" class="section">
        <div class="about-layout">
            <div class="about-photo">
                <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&w=800&q=80" alt="Piotr - Cytruszek84">
                <div class="about-photo-label" data-lang="pl">Fotograf Krajobrazu</div>
                <div class="about-photo-label" data-lang="en">Landscape Photographer</div>
                <div class="about-photo-label" data-lang="de">Landschaftsfotograf</div>
            </div>
            
            <div class="about-content">
                <!-- HEADINGS -->
                <h2 data-lang="pl">O mnie</h2>
                <h2 data-lang="en">About Me</h2>
                <h2 data-lang="de">Über mich</h2>
                
                <!-- POLISH TEXT -->
                <div data-lang="pl">
                    <p>Witaj! Nazywam się Piotr. Fotografia to moja pasja, w której skupiam się na chwytaniu piękna natury, górskich krajobrazów, porannych mgieł, nocnego nieba oraz wyjątkowej gry światła.</p>
                    <p>Pracuję z aparatem Sony DSC-HX400V, wyciągając z niego wszystko, co najlepsze – od malowniczych wschodów i zachodów słońca po eksperymenty z malowaniem światłem oraz długim czasem naświetlania.</p>
                    <p>Kamera towarzyszy mi w podróżach i codziennych kadrach, pozwalając zatrzymać ulotne chwile i ukazać świat z perspektywy pełnej spokoju, magii oraz dopracowanych detali.</p>
                </div>

                <!-- ENGLISH TEXT -->
                <div data-lang="en">
                    <p>Welcome! My name is Piotr. Photography is my passion, where I focus on capturing the beauty of nature, mountain landscapes, morning mists, night skies, and the unique play of light.</p>
                    <p>I shoot with a Sony DSC-HX400V camera, squeezing the best out of it – from picturesque sunrises and sunsets to light painting experiments and long exposure shots.</p>
                    <p>My camera accompanies me on travels and everyday moments, allowing me to freeze fleeting memories and show the world through a perspective full of peace, magic, and refined details.</p>
                </div>

                <!-- GERMAN TEXT -->
                <div data-lang="de">
                    <p>Willkommen! Mein Name ist Piotr. Fotografie ist meine Leidenschaft, bei der ich mich darauf konzentriere, die Schönheit der Natur, Berglandschaften, Morgennebel, den Nachthimmel und das besondere Spiel des Lichts einzufangen.</p>
                    <p>Ich fotografiere mit einer Sony DSC-HX400V Kamera und hole das Beste aus ihr heraus – von malerischen Sonnenauf- und -untergängen bis hin zu Lichtmalerei-Experimenten und Langzeitbelichtungen.</p>
                    <p>Meine Kamera begleitet mich auf Reisen und im Alltag. Sie ermöglicht es mir, flüchtige Momente festzuhalten und die Welt aus einer Perspektive voller Ruhe, Magie und durchdachter Details zu zeigen.</p>
                </div>
                
                <div class="about-signature">Cytruszek84</div>
            </div>
        </div>
    </section>

    <!-- SOCIAL SECTION -->
    <section class="social-section section">
        <div class="social-box">
            <div>
                <h2 data-lang="pl">Dołącz do społeczności</h2>
                <h2 data-lang="en">Join the Community</h2>
                <h2 data-lang="de">Treten Sie der Community bei</h2>

                <p data-lang="pl">Śledź moje najnowsze kadry i projekty fotograficzne.</p>
                <p data-lang="en">Follow my latest shots and photography projects.</p>
                <p data-lang="de">Folgen Sie meinen neuesten Fotos und Fotoprojekten.</p>
            </div>
            <div class="social-links">
                <a href="#" class="social-link">Instagram</a>
                <a href="https://github.com/cytruszek84" target="_blank" class="social-link">GitHub</a>
            </div>
        </div>
    </section>

    <!-- FOOTER -->
    <footer>
        <div class="footer-brand">CYTRUSZEK84</div>
        <p class="footer-copy" data-lang="pl">Fotografia Krajobrazowa & Natura</p>
        <p class="footer-copy" data-lang="en">Landscape & Nature Photography</p>
        <p class="footer-copy" data-lang="de">Landschafts- & Naturfotografie</p>
        <div class="copyright">© 2026 Cytruszek84. All rights reserved.</div>
    </footer>

    <!-- LIGHTBOX MODAL -->
    <div id="lightbox" onclick="closeLightbox()">
        <button class="lightbox-close" onclick="closeLightbox()">&times;</button>
        <img id="lightbox-img" src="" alt="Enlarged view">
    </div>

    <!-- JAVASCRIPT: FIREBASE, VIEWS, LIGHTBOX, MULTI-LANGUAGE -->
    <script>
        // 1. FIREBASE INITIALIZATION PLACEHOLDER
        const firebaseConfig = {
            apiKey: "YOUR_API_KEY",
            authDomain: "cytruszek84.firebaseapp.com",
            projectId: "cytruszek84",
            storageBucket: "cytruszek84.appspot.com",
            messagingSenderId: "123456789",
            appId: "1:123456789:web:abc123def456"
        };
        
        // Initialize Firebase if compat libraries loaded
        if (typeof firebase !== 'undefined') {
            firebase.initializeApp(firebaseConfig);
            const db = firebase.firestore();
            console.log("Firebase initialized successfully.");
        }

        // 2. MULTI-LANGUAGE LOGIC (CSS CLASS SWITCHER + LOCALSTORAGE)
        function setLanguage(lang) {
            // Apply body class
            document.body.className = `lang-${lang}`;

            // Update active state on navigation language buttons
            document.querySelectorAll('.lang-btn').forEach(btn => btn.classList.remove('active'));
            const activeBtn = document.getElementById(`btn-${lang}`);
            if (activeBtn) activeBtn.classList.add('active');

            // Save preference to LocalStorage
            localStorage.setItem('cytruszek_lang', lang);
        }

        // 3. SINGLE PAGE VIEW SWITCHER
        function showView(viewName) {
            const homeView = document.getElementById('home-view');
            const galleryView = document.getElementById('gallery-view');
            const aboutView = document.getElementById('about-view');
            
            const navHome = document.getElementById('nav-home');
            const navPortfolio = document.getElementById('nav-portfolio');
            const navAbout = document.getElementById('nav-about');

            // Reset active states on menu
            navHome.classList.remove('active');
            navPortfolio.classList.remove('active');
            navAbout.classList.remove('active');

            // Hide all views
            homeView.style.display = 'none';
            galleryView.style.display = 'none';
            aboutView.style.display = 'none';

            if (viewName === 'about') {
                aboutView.style.display = 'block';
                navAbout.classList.add('active');
            } else if (viewName === 'gallery') {
                galleryView.style.display = 'block';
                navPortfolio.classList.add('active');
            } else {
                homeView.style.display = 'block';
                navHome.classList.add('active');
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function openFolder(categoryName) {
            document.getElementById('gallery-category-title').innerText = categoryName;
            showView('gallery');
        }

        // 4. LIGHTBOX MECHANISM
        function openLightbox(imgSrc) {
            const lightbox = document.getElementById('lightbox');
            const lightboxImg = document.getElementById('lightbox-img');
            lightboxImg.src = imgSrc;
            lightbox.classList.add('show');
            document.body.style.overflow = 'hidden';
        }

        function closeLightbox() {
            const lightbox = document.getElementById('lightbox');
            lightbox.classList.remove('show');
            document.body.style.overflow = 'auto';
        }

        // 5. ON LOAD INITIALIZATION
        document.addEventListener('DOMContentLoaded', () => {
            const savedLang = localStorage.getItem('cytruszek_lang') || 'pl';
            setLanguage(savedLang);
        });
    </script>
</body>
</html>
