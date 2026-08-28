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

        /* HEADER */
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

        /* HERO */
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

        .primary-btn, .secondary-btn {
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

        /* SECTIONS & VIEWS */
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

        /* VIEW SWITCHING */
        .view-section {
            display: block;
        }

        #gallery-view, #about-view {
            display: none;
        }

        /* ABOUT SECTION STYLES */
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

        /* SOCIAL */
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

        /* FOOTER */
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

        /* RESPONSIVE */
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

            .social-links {
                width: 100%;
                flex-direction: column;
            }

            .social-link {
                width: 100%;
            }
        }

        @media (max-width: 430px) {
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
<body>

    <!-- HEADER / NAVIGATION -->
    <header>
        <div class="nav">
            <button class="brand" onclick="showView('home')">
                <span class="brand-name">CYTRUSZEK84</span>
                <span class="brand-sub" data-pl="FOTOGRAFIA KRAJOBRAZOWA" data-en="LANDSCAPE PHOTOGRAPHY" data-de="LANDSCHAFTSFOTOGRAFIE">FOTOGRAFIA KRAJOBRAZOWA</span>
            </button>

            <nav class="main-menu">
                <button class="nav-btn active" id="nav-home" onclick="showView('home')" data-pl="Główna" data-en="Home" data-de="Startseite">Główna</button>
                <button class="nav-btn" id="nav-portfolio" onclick="showView('home')" data-pl="Portfolio" data-en="Portfolio" data-de="Portfolio">Portfolio</button>
                <button class="nav-btn" id="nav-about" onclick="showView('about')" data-pl="O mnie" data-en="About Me" data-de="Über mich">O mnie</button>
            </nav>

            <div class="languages">
                <button class="lang-btn active" id="lang-pl" onclick="changeLanguage('pl')">PL</button>
                <button class="lang-btn" id="lang-en" onclick="changeLanguage('en')">EN</button>
                <button class="lang-btn" id="lang-de" onclick="changeLanguage('de')">DE</button>
            </div>
        </div>
    </header>

    <!-- HOME VIEW -->
    <main id="home-view" class="view-section">
        <!-- HERO -->
        <section class="hero">
            <div class="hero-content">
                <div class="hero-label" data-pl="Fotografia Krajobrazowa" data-en="Landscape Photography" data-de="Landschaftsfotografie">Fotografia Krajobrazowa</div>
                <h1 data-pl="Chwytając <span>światło</span> i ulotne chwile." data-en="Capturing <span>light</span> and fleeting moments." data-de="Licht und <span>flüchtige</span> Momente einfangen.">Chwytając <span>światło</span> i ulotne chwile.</h1>
                <p class="hero-text" data-pl="Odkrywaj naturę, poranne mgły, górskie szczyty i miejskie pejzaże uchwycone w wyjątkowych kadrach." data-en="Discover nature, morning mists, mountain peaks, and urban landscapes captured in unique frames." data-de="Entdecken Sie die Natur, Morgennebel, Berggipfel und Stadtlandschaften in einzigartigen Bildern.">Odkrywaj naturę, poranne mgły, górskie szczyty i miejskie pejzaże uchwycone w wyjątkowych kadrach.</p>
                <div class="hero-actions">
                    <button class="primary-btn" onclick="document.getElementById('portfolio-sec').scrollIntoView({behavior: 'smooth'})" data-pl="Zobacz Galerię" data-en="View Gallery" data-de="Galerie Ansehen">Zobacz Galerię</button>
                    <button class="secondary-btn" onclick="showView('about')" data-pl="Poznaj Mnie" data-en="Meet Me" data-de="Über Mich">Poznaj Mnie</button>
                </div>
            </div>
            <div class="hero-visual">
                <div class="hero-frame">
                    <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=800&q=80" alt="Landscape Photo">
                </div>
                <div class="hero-badge">
                    <strong data-pl="Natura & Pasja" data-en="Nature & Passion" data-de="Natur & Leidenschaft">Natura & Pasja</strong>
                    <span data-pl="Cytruszek84 Photography" data-en="Cytruszek84 Photography" data-de="Cytruszek84 Fotografie">Cytruszek84 Photography</span>
                </div>
            </div>
        </section>

        <!-- PORTFOLIO CATEGORIES -->
        <section id="portfolio-sec" class="section">
            <div class="section-heading">
                <div class="section-label" data-pl="Kategorie" data-en="Categories" data-de="Kategorien">Kategorie</div>
                <h2 data-pl="Galeria Zdjęć" data-en="Photo Gallery" data-de="Fotogalerie">Galeria Zdjęć</h2>
                <p data-pl="Wybierz kategorię, aby zobaczyć zebrane fotografie." data-en="Select a category to explore the collected photographs." data-de="Wählen Sie eine Kategorie, um die Fotosammlung zu erkunden.">Wybierz kategorię, aby zobaczyć zebrane fotografie.</p>
            </div>

            <div class="folders-grid">
                <div class="folder-card" onclick="alert('Kategoria Krajobrazy')">
                    <div class="folder-art art-1"></div>
                    <div class="folder-number">01</div>
                    <div class="folder-info">
                        <div class="folder-title" data-pl="Krajobrazy" data-en="Landscapes" data-de="Landschaften">Krajobrazy</div>
                        <div class="folder-count" data-pl="Natura, mgły i poranki" data-en="Nature, mists and mornings" data-de="Natur, Nebel und Morgenstunden">Natura, mgły i poranki</div>
                    </div>
                </div>

                <div class="folder-card" onclick="alert('Kategoria Góry')">
                    <div class="folder-art art-2"></div>
                    <div class="folder-number">02</div>
                    <div class="folder-info">
                        <div class="folder-title" data-pl="Góry" data-en="Mountains" data-de="Berge">Góry</div>
                        <div class="folder-count" data-pl="Szczyty i szlaki" data-en="Peaks and trails" data-de="Gipfel und Pfade">Szczyty i szlaki</div>
                    </div>
                </div>

                <div class="folder-card" onclick="alert('Kategoria Miasta')">
                    <div class="folder-art art-3"></div>
                    <div class="folder-number">03</div>
                    <div class="folder-info">
                        <div class="folder-title" data-pl="Miasta" data-en="Urban" data-de="Städte">Miasta</div>
                        <div class="folder-count" data-pl="Architektura i światła nocą" data-en="Architecture & night lights" data-de="Architektur & Nachtlichter">Architektura i światła nocą</div>
                    </div>
                </div>

                <div class="folder-card" onclick="alert('Kategoria Zmierzch & Noc')">
                    <div class="folder-art art-4"></div>
                    <div class="folder-number">04</div>
                    <div class="folder-info">
                        <div class="folder-title" data-pl="Zmierzch & Noc" data-en="Dusk & Night" data-de="Dämmerung & Nacht">Zmierzch & Noc</div>
                        <div class="folder-count" data-pl="Gwiazdy i smugi światła" data-en="Stars and light trails" data-de="Sterne und Lichtspuren">Gwiazdy i smugi światła</div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- ABOUT VIEW -->
    <section id="about-view" class="section view-section">
        <div class="about-layout">
            <div class="about-photo">
                <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&w=800&q=80" alt="Piotr - Cytruszek84">
                <div class="about-photo-label" 
                     data-pl="Fotograf Krajobrazu" 
                     data-en="Landscape Photographer" 
                     data-de="Landschaftsfotograf">
                     Fotograf Krajobrazu
                </div>
            </div>
            
            <div class="about-content">
                <h2 data-pl="O mnie" 
                    data-en="About Me" 
                    data-de="Über mich">
                    O mnie
                </h2>
                
                <p data-pl="Witaj! Nazywam się Piotr. Fotografia to moja pasja, w której skupiam się na chwytaniu piękna natury, górskich krajobrazów, porannych mgieł, nocnego nieba oraz wyjątkowej gry światła."
                   data-en="Welcome! My name is Piotr. Photography is my passion, where I focus on capturing the beauty of nature, mountain landscapes, morning mists, night skies, and the unique play of light."
                   data-de="Willkommen! Mein Name ist Piotr. Fotografie ist meine Leidenschaft, bei der ich mich darauf konzentriere, die Schönheit der Natur, Berglandschaften, Morgennebel, den Nachthimmel und das besondere Spiel des Lichts einzufangen.">
                   Witaj! Nazywam się Piotr. Fotografia to moja pasja, w której skupiam się na chwytaniu piękna natury, górskich krajobrazów, porannych mgieł, nocnego nieba oraz wyjątkowej gry światła.
                </p>

                <p data-pl="Pracuję z aparatem Sony DSC-HX400V, wyciągając z niego wszystko, co najlepsze – od malowniczych wschodów i zachodów słońca po eksperymenty z malowaniem światłem oraz długim czssem naświetlania."
                   data-en="I shoot with a Sony DSC-HX400V camera, squeezing the best out of it – from picturesque sunrises and sunsets to light painting experiments and long exposure shots."
                   data-de="Ich fotografiere mit einer Sony DSC-HX400V Kamera und hole das Beste aus ihr heraus – von malerischen Sonnenauf- und -untergängen bis hin zu Lichtmalerei-Experimenten und Langzeitbelichtungen.">
                   Pracuję z aparatem Sony DSC-HX400V, wyciągając z niego wszystko, co najlepsze – od malowniczych wschodów i zachodów słońca po eksperymenty z malowaniem światłem oraz długim czasem naświetlania.
                </p>
                
                <p data-pl="Kamera towarzyszy mi w podróżach i codziennych kadrach, pozwalając zatrzymać ulotne chwile i ukazać świat z perspektywy pełnej spokoju, magii oraz dopracowanych detali."
                   data-en="My camera accompanies me on travels and everyday moments, allowing me to freeze fleeting memories and show the world through a perspective full of peace, magic, and refined details."
                   data-de="Meine Kamera begleitet mich auf Reisen und im Alltag. Sie ermöglicht es mir, flüchtige Momente festzuhalten und die Welt aus einer Perspektive voller Ruhe, Magie und durchdachter Details zu zeigen.">
                   Kamera towarzyszy mi w podróżach i codziennych kadrach, pozwalając zatrzymać ulotne chwile i ukazać świat z perspektywy pełnej spokoju, magii oraz dopracowanych detali.
                </p>
                
                <div class="about-signature">Cytruszek84</div>
            </div>
        </div>
    </section>

    <!-- SOCIAL SECTION -->
    <section class="social-section section">
        <div class="social-box">
            <div>
                <h2 data-pl="Dołącz do społeczności" data-en="Join the Community" data-de="Treten Sie der Community bei">Dołącz do społeczności</h2>
                <p data-pl="Śledź moje najnowsze kadry i projekty fotograficzne." data-en="Follow my latest shots and photography projects." data-de="Folgen Sie meinen neuesten Fotos und Fotoprojekten.">Śledź moje najnowsze kadry i projekty fotograficzne.</p>
            </div>
            <div class="social-links">
                <a href="#" class="social-link">Instagram</a>
                <a href="#" class="social-link">GitHub</a>
            </div>
        </div>
    </section>

    <!-- FOOTER -->
    <footer>
        <div class="footer-brand">CYTRUSZEK84</div>
        <p class="footer-copy" data-pl="Fotografia Krajobrazowa & Natura" data-en="Landscape & Nature Photography" data-de="Landschafts- & Naturfotografie">Fotografia Krajobrazowa & Natura</p>
        <div class="copyright">© 2026 Cytruszek84. All rights reserved.</div>
    </footer>

    <!-- JAVASCRIPT FOR MULTI-LANGUAGE & VIEW SWITCHING -->
    <script>
        // Language Switcher Function
        function changeLanguage(lang) {
            // Update active state on language buttons
            document.querySelectorAll('.lang-btn').forEach(btn => btn.classList.remove('active'));
            const activeBtn = document.getElementById(`lang-${lang}`);
            if (activeBtn) activeBtn.classList.add('active');

            // Find all elements with translation attributes
            const translatableElements = document.querySelectorAll('[data-pl][data-en][data-de]');
            
            translatableElements.forEach(el => {
                const translation = el.getAttribute(`data-${lang}`);
                if (translation) {
                    el.innerHTML = translation;
                }
            });

            // Save preferred language in LocalStorage
            localStorage.setItem('preferred_lang', lang);
        }

        // Simple Single Page View Switching (Home vs About)
        function showView(viewName) {
            const homeView = document.getElementById('home-view');
            const aboutView = document.getElementById('about-view');
            const navHome = document.getElementById('nav-home');
            const navAbout = document.getElementById('nav-about');

            if (viewName === 'about') {
                homeView.style.display = 'none';
                aboutView.style.display = 'block';
                navHome.classList.remove('active');
                navAbout.classList.add('active');
                window.scrollTo({ top: 0, behavior: 'smooth' });
            } else {
                homeView.style.display = 'block';
                aboutView.style.display = 'none';
                navHome.classList.add('active');
                navAbout.classList.remove('active');
            }
        }

        // Initialize preferred language on DOM load
        document.addEventListener('DOMContentLoaded', () => {
            const savedLang = localStorage.getItem('preferred_lang') || 'pl';
            changeLanguage(savedLang);
        });
    </script>
</body>
</html>
