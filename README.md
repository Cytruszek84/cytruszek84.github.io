<!DOCTYPE html>
<html lang="pl">
<head>
&#x20;   <meta charset="UTF-8">
&#x20;   <meta name="viewport" content="width=device-width, initial-scale=1.0">


<title>BEZ KADRU | Fotografia</title>

<meta name="description"
      content="BEZ KADRU – fotografia wolności, natury, podróży, światła i chwil poza schematem.">

<link rel="canonical" href="https://cytruszek84.github.io/">

<meta property="og:type" content="website">
<meta property="og:url" content="https://cytruszek84.github.io/">
<meta property="og:title" content="BEZ KADRU | Fotografia">
<meta property="og:description"
      content="Fotografia wolności, natury, podróży, światła i chwil poza schematem.">
<meta name="twitter:card" content="summary_large_image">


<meta name="description"
      content="Bez Kadru Photography – fotografia krajobrazowa, natura, góry, miasta, mgły, światło i wyjątkowe chwile.">

<meta name="theme-color" content="#f7f5f0">

<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-83HTNWWCL"></script>

<script>
    const SITE_URL = "https://cytruszek84.github.io/";
    window.dataLayer = window.dataLayer || [];

    function gtag() {
        dataLayer.push(arguments);
    }

    gtag('js', new Date());
    gtag('config', 'G-83HTNWWCL');
</script>

<!-- Firebase -->
<script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-firestore-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-analytics-compat.js"></script>

<style>

    /* =====================================================
       RESET
    ===================================================== */

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
        font-family:
            Inter,
            "Segoe UI",
            Arial,
            sans-serif;

        min-height: 100vh;
        overflow-x: hidden;
    }

    button,
    a {
        font-family: inherit;
    }

    img {
        max-width: 100%;
    }


    /* =====================================================
       VARIABLES
    ===================================================== */

    :root {
        --cream: #f7f5f0;
        --white: #ffffff;
        --dark: #20252b;
        --text: #30363d;
        --muted: #747b83;

        --gold: #b8893d;
        --gold-light: #d6b477;

        --green: #657765;

        --border: rgba(32, 37, 43, .10);

        --shadow:
            0 15px 50px rgba(31, 35, 40, .09);

        --shadow-hover:
            0 25px 70px rgba(31, 35, 40, .16);

        --radius: 20px;
    }


    /* =====================================================
       TOP BAR
    ===================================================== */

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


    /* BRAND */

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


    /* MENU */

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


    /* LANGUAGES */

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


    /* =====================================================
       HERO
    ===================================================== */

    .hero {
        max-width: 1250px;

        margin: 0 auto;

        padding: 80px 25px 65px;

        display: grid;

        grid-template-columns:
            minmax(0, 1.1fr)
            minmax(350px, .9fr);

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

        font-size:
            clamp(3rem, 6vw, 5.5rem);

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


    /* HERO IMAGE */

    .hero-visual {
        position: relative;
    }

    .hero-frame {
        position: relative;

        aspect-ratio: 4 / 5;

        overflow: hidden;

        border-radius: 30px;

        background:
            linear-gradient(
                135deg,
                #d9d6cf,
                #aaa79e
            );

        box-shadow: var(--shadow);

        transform: rotate(2deg);
    }

    .hero-frame::after {
        content: "";

        position: absolute;

        inset: 0;

        background:
            linear-gradient(
                180deg,
                transparent 55%,
                rgba(0,0,0,.25)
            );

        pointer-events: none;
    }

    .hero-frame img {
        width: 100%;
        height: 100%;

        object-fit: cover;

        display: block;
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


    /* =====================================================
       SECTIONS
    ===================================================== */

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

        font-size:
            clamp(2rem, 4vw, 3rem);

        font-weight: 500;
    }

    .section-heading p {
        max-width: 650px;

        margin-top: 12px;

        color: var(--muted);

        line-height: 1.7;
    }


    /* =====================================================
       FOLDERS
    ===================================================== */

    .folders-grid {
        display: grid;

        grid-template-columns:
            repeat(auto-fit, minmax(260px, 1fr));

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

        transition:
            transform .35s ease,
            box-shadow .35s ease;
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
    }

    .folder-info {
        position: absolute;

        left: 23px;
        right: 23px;
        bottom: 21px;

        z-index: 2;
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


    /* ART COLORS */

    .art-1 {
        background:
            linear-gradient(
                135deg,
                #dfe9ed,
                #9fb9bf
            );
    }

    .art-2 {
        background:
            linear-gradient(
                135deg,
                #d9d6ce,
                #b99f83
            );
    }

    .art-3 {
        background:
            linear-gradient(
                135deg,
                #dce7df,
                #9db5a4
            );
    }

    .art-4 {
        background:
            linear-gradient(
                135deg,
                #ded9d3,
                #aa9990
            );
    }

    .art-5 {
        background:
            linear-gradient(
                135deg,
                #e8dfce,
                #c89d66
            );
    }

    .art-6 {
        background:
            linear-gradient(
                135deg,
                #dedee8,
                #8e95a9
            );
    }

    .art-7 {
        background:
            linear-gradient(
                135deg,
                #e4dfd4,
                #b8aa83
            );
    }

    .art-8 {
        background:
            linear-gradient(
                135deg,
                #dce2e8,
                #91a1b1
            );
    }


    /* =====================================================
       GALLERY
    ===================================================== */

    #gallery-view {
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

        grid-template-columns:
            repeat(auto-fill, minmax(270px, 1fr));

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

        transition:
            transform .35s ease,
            box-shadow .35s ease;
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

    /* OCHRONA */

    .photo-protection {
        position: absolute;

        inset: 0;

        z-index: 3;

        background: transparent;
    }

    .photo-card::after {
        content: "© Bez Kadru";

        position: absolute;

        z-index: 4;

        right: 12px;
        bottom: 10px;

        color: rgba(255,255,255,.7);

        font-size: .65rem;

        letter-spacing: .08em;

        text-shadow:
            0 1px 4px rgba(0,0,0,.7);

        pointer-events: none;
    }


    /* =====================================================
       ABOUT
    ===================================================== */

    #about-view {
        display: none;
    }

    .about-layout {
        display: grid;

        grid-template-columns:
            minmax(300px, .8fr)
            minmax(0, 1.2fr);

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
        font-family: "Brush Script MT", cursive;

        font-size: 2rem;

        color: var(--gold);

        margin-top: 25px;
    }


    /* =====================================================
       SOCIAL
    ===================================================== */

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


    /* =====================================================
       FOOTER
    ===================================================== */

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

    .visit-box {
        margin-top: 20px;

        display: inline-flex;

        align-items: center;

        gap: 8px;

        padding: 8px 14px;

        border: 1px solid rgba(255,255,255,.12);

        border-radius: 50px;
    }

    .visit-number {
        color: white;

        font-weight: 800;
    }


    /* =====================================================
       LIGHTBOX
    ===================================================== */

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

        box-shadow:
            0 30px 100px rgba(0,0,0,.5);
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


    /* =====================================================
       RESPONSIVE
    ===================================================== */

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
            grid-template-columns:
                repeat(2, minmax(0, 1fr));

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
<body
&#x20;   oncontextmenu="return false;"
&#x20;   ondragstart="return false;"
&#x20;   onselectstart="return false;"
\>
<!-- =========================================================
&#x20;    HEADER
\========================================================= -->
<header>


<div class="nav">

    <button
        class="brand"
        onclick="showHome()"
        aria-label="Strona główna"
    >
        <span class="brand-name">
            BEZ KADRU
        </span>

        <span class="brand-sub">
            Photography
        </span>
    </button>


    <nav class="main-menu">

        <button
            class="nav-btn active"
            id="nav-gallery"
            onclick="showHome()"
        >
            Galeria
        </button>

        <button
            class="nav-btn"
            id="nav-about"
            onclick="showAbout()"
        >
            O mnie
        </button>

    </nav>


    <div class="languages">

        <button
            class="lang-btn active"
            data-lang="pl"
            onclick="setLanguage('pl')"
        >
            PL
        </button>

        <button
            class="lang-btn"
            data-lang="en"
            onclick="setLanguage('en')"
        >
            EN
        </button>

        <button
            class="lang-btn"
            data-lang="de"
            onclick="setLanguage('de')"
        >
            DE
        </button>

    </div>

</div>


</header>
<!-- =========================================================
&#x20;    HOME
\========================================================= -->
<main id="home-view">


<!-- HERO -->

<section class="hero">

    <div>

        <div
            class="hero-label"
            id="hero-label"
        >
            Photography
        </div>


        <h1 id="hero-title">
            Świat zapisany<br>
            <span>w kadrze.</span>
        </h1>


        <p
            class="hero-text"
            id="hero-text"
        >
            Fotografia to dla mnie sposób zatrzymywania chwil,
            do których można wrócić nawet po wielu latach.
            Światło, natura, przestrzeń i emocje — właśnie tego szukam
            za każdym razem, kiedy biorę aparat do ręki.
        </p>


        <div class="hero-actions">

            <button
                class="primary-btn"
                onclick="scrollToGallery()"
                id="hero-gallery-btn"
            >
                Odkryj galerię
            </button>

            <button
                class="secondary-btn"
                onclick="showAbout()"
                id="hero-about-btn"
            >
                Poznaj mnie
            </button>

        </div>

    </div>


    <div class="hero-visual">

        <div class="hero-frame">

            <!-- GŁÓWNE ZDJĘCIE -->
            <img
                src="hero.jpg"
                alt="Fotografia Bez Kadru"
                draggable="false"
            >

        </div>


        <div class="hero-badge">

            <strong id="hero-badge-title">
                Chwile. Światło. Emocje.
            </strong>

            <span id="hero-badge-text">
                Fotografia z pasją
            </span>

        </div>

    </div>

</section>


<!-- GALLERY -->

<section
    class="section"
    id="gallery-section"
>

    <div class="section-heading">

        <div
            class="section-label"
            id="gallery-label"
        >
            Portfolio
        </div>

        <h2 id="gallery-title">
            Historie zatrzymane w czasie
        </h2>

        <p id="gallery-description">
            Wybierz kolekcję i zobacz fotografie.
            Każdy folder to inna historia, inne światło
            i inne miejsce.
        </p>

    </div>


    <div
        id="folders-grid"
        class="folders-grid"
    ></div>

</section>


<!-- SOCIAL -->

<section class="social-section">

    <div class="section">

        <div class="social-box">

            <div>

                <h2 id="social-title">
                    Zobacz więcej moich kadrów
                </h2>

                <p id="social-description">
                    Obserwuj mnie również w mediach społecznościowych.
                </p>

            </div>


            <div class="social-links">

                <!-- LINK TIKTOK -->
                <a
                    class="social-link"
                    href="https://www.tiktok.com/@bezkadru"
                    target="_blank"
                    rel="noopener noreferrer"
                >
                    TikTok
                </a>


                <!-- LINK INSTAGRAM -->
                <a
                    class="social-link"
                    href="https://www.instagram.com/bezkadru"
                    target="_blank"
                    rel="noopener noreferrer"
                >
                    Instagram
                </a>

            </div>

        </div>

    </div>

</section>


</main>
<!-- =========================================================
&#x20;    GALLERY VIEW
\========================================================= -->
<section
&#x20;   id="gallery-view"
&#x20;   class="section"
\>


<div class="gallery-header">

    <button
        class="back-btn"
        onclick="showHome()"
        id="back-btn"
    >
        ← Wróć do kolekcji
    </button>

    <h2
        class="gallery-title"
        id="folder-title-display"
    >
    </h2>

</div>


<div
    id="photo-grid"
    class="photo-grid"
>
</div>


</section>
<!-- =========================================================
&#x20;    ABOUT
\========================================================= -->
<section
&#x20;   id="about-view"
&#x20;   class="section"
\>


<div class="about-layout">


    <!-- ZDJĘCIE AUTORA -->

    <div class="about-photo">

        <!--
            ZAPISZ SWOJE ZDJĘCIE JAKO:

            omnie.jpg

            i umieść je obok index.html
        -->

        <img
            src="omnie.jpg"
            alt="Piotr – Bez Kadru"
            draggable="false"
            onerror="this.src='about.jpg';"
        >

        <div
            class="about-photo-label"
            id="about-photo-label"
        >
            Piotr · Bez Kadru
        </div>

    </div>


    <!-- OPIS -->

    <div class="about-content">

        <div
            class="section-label"
            id="about-label"
        >
            O mnie
        </div>


        <h2 id="about-title">
            Nie tylko robię zdjęcia.
            Zbieram chwile.
        </h2>


        <div id="about-text">

            <p>
                Mam na imię Piotr, a w świecie fotografii
                możecie znaleźć mnie jako <strong>Bez Kadru</strong>.
            </p>

            <p>
                Aparat towarzyszy mi od lat. Zabieram go ze sobą
                w podróże, na górskie szlaki, do miast, nad jeziora
                i wszędzie tam, gdzie pojawia się światło,
                którego nie można przegapić.
            </p>

            <p>
                Najbardziej interesują mnie momenty, których
                nie da się powtórzyć — pierwszy promień słońca,
                poranna mgła, pusty szlak, światło zachodzącego
                słońca czy zwykła ulica, która przez kilka sekund
                wygląda zupełnie inaczej.
            </p>

            <p>
                Nie zależy mi na tym, żeby zrobić po prostu
                kolejne zdjęcie. Chcę stworzyć kadr, który
                wywoła emocję i sprawi, że zatrzymasz się
                na chwilę.
            </p>

            <p>
                Zapraszam Cię do mojego fotograficznego świata.
                Mam nadzieję, że znajdziesz tutaj coś,
                co zostanie z Tobą na dłużej.
            </p>

        </div>


        <div class="about-signature">
            Piotr
        </div>

    </div>

</div>


</section>
<!-- =========================================================
&#x20;    LIGHTBOX
\========================================================= -->
<div
&#x20;   id="lightbox"
&#x20;   onclick="closeLightbox()"
\>


<button
    class="lightbox-close"
    onclick="closeLightbox()"
    aria-label="Zamknij"
>
    ×
</button>


<img
    id="lightbox-img"
    src=""
    alt="Powiększona fotografia"
    draggable="false"
>


</div>
<!-- =========================================================
&#x20;    FOOTER
\========================================================= -->
<footer>


<div class="footer-brand">
    BEZ KADRU
</div>

<p
    class="footer-copy"
    id="footer-subtitle"
>
    Photography · Hobby · Passion
</p>

<p
    class="copyright"
    id="footer-copyright"
>
    © Wszystkie fotografie są chronione prawem autorskim.
    Kopiowanie i rozpowszechnianie bez zgody autora jest zabronione.
</p>


<div class="visit-box">

    <span id="footer-visits">
        Odwiedziny
    </span>

    <span
        class="visit-number"
        id="visit-counter"
    >
        …
    </span>

</div>


</footer>
<script>

/* =========================================================
&#x20;  FIREBASE
\========================================================= */

const firebaseConfig = {

&#x20;   apiKey: "AIzaSyDv2QED1ZHbd3xDWIBhcLQJd7Zd7Rz-tWw",

&#x20;   authDomain:
&#x20;       "bezkadru-c2e33.firebaseapp.com",

&#x20;   projectId:
&#x20;       "bezkadru-c2e33",

&#x20;   storageBucket:
&#x20;       "bezkadru-c2e33.firebasestorage.app",

&#x20;   messagingSenderId:
&#x20;       "89741680278",

&#x20;   appId:
&#x20;       "1:89741680278:web:1f032fb3cf28ee73d02cb7",

&#x20;   measurementId:
&#x20;       "G-83HTNWWCL"
};


let db = null;


/* INIT FIREBASE */

try {

&#x20;   firebase.initializeApp(firebaseConfig);

&#x20;   db = firebase.firestore();

&#x20;   try {
&#x20;       firebase.analytics();
&#x20;   } catch (e) {
&#x20;       console.warn("Analytics niedostępne.");
&#x20;   }

} catch (error) {

&#x20;   console.error(
&#x20;       "Firebase initialization error:",
&#x20;       error
&#x20;   );
}


/* =========================================================
&#x20;  VISIT COUNTER
\========================================================= */

function updateVisitCounter() {

&#x20;   const counterElement =
&#x20;       document.getElementById("visit-counter");


&#x20;   if (!db) {

&#x20;       counterElement.textContent = "—";

&#x20;       return;
&#x20;   }


&#x20;   const counterRef =
&#x20;       db.collection("stats")
&#x20;         .doc("visits");


&#x20;   db.runTransaction(async transaction => {

&#x20;       const doc =
&#x20;           await transaction.get(counterRef);


&#x20;       let count = 1;


&#x20;       if (doc.exists) {

&#x20;           const oldCount =
&#x20;               Number(doc.data().count) || 0;

&#x20;           count = oldCount + 1;
&#x20;       }


&#x20;       transaction.set(
&#x20;           counterRef,
&#x20;           {
&#x20;               count: count
&#x20;           },
&#x20;           {
&#x20;               merge: true
&#x20;           }
&#x20;       );


&#x20;       return count;

&#x20;   })
&#x20;   .then(count => {

&#x20;       counterElement.textContent =
&#x20;           count.toLocaleString();

&#x20;   })
&#x20;   .catch(error => {

&#x20;       console.error(
&#x20;           "Błąd licznika odwiedzin:",
&#x20;           error
&#x20;       );


&#x20;       counterElement.textContent = "—";
&#x20;   });
}


updateVisitCounter();


/* =========================================================
&#x20;  SETTINGS
\========================================================= */

const photosPerFolder = 10;

let totalPhotos = 245;

let currentLanguage = "pl";

let currentOpenFolder = null;


/* =========================================================
&#x20;  NAZWY FOLDERÓW
\========================================================= */

const folderNames = {

&#x20;   pl: [
&#x20;       "Światło natury",
&#x20;       "Górskie historie",
&#x20;       "Mgły o poranku",
&#x20;       "Opuszczone miejsca",
&#x20;       "Miasto po zmroku",
&#x20;       "Zachody słońca",
&#x20;       "Drogi i podróże",
&#x20;       "Chwile bez scenariusza"
&#x20;   ],

&#x20;   en: [
&#x20;       "Nature & Light",
&#x20;       "Mountain Stories",
&#x20;       "Morning Mist",
&#x20;       "Abandoned Places",
&#x20;       "City After Dark",
&#x20;       "Sunset Stories",
&#x20;       "Roads & Journeys",
&#x20;       "Unscripted Moments"
&#x20;   ],

&#x20;   de: [
&#x20;       "Natur & Licht",
&#x20;       "Berggeschichten",
&#x20;       "Morgennebel",
&#x20;       "Verlassene Orte",
&#x20;       "Stadt bei Nacht",
&#x20;       "Sonnenuntergänge",
&#x20;       "Reisen & Wege",
&#x20;       "Ungeplante Momente"
&#x20;   ]
};


/* =========================================================
&#x20;  TRANSLATIONS
\========================================================= */

const translations = {

&#x20;   pl: {

&#x20;       heroLabel:
&#x20;           "Fotografia",

&#x20;       heroTitle:
&#x20;           "Świat zapisany<br><span>w kadrze.</span>",

&#x20;       heroText:
&#x20;           "Fotografia to dla mnie sposób zatrzymywania chwil, do których można wrócić nawet po wielu latach. Światło, natura, przestrzeń i emocje — właśnie tego szukam za każdym razem, kiedy biorę aparat do ręki.",

&#x20;       heroGallery:
&#x20;           "Odkryj galerię",

&#x20;       heroAbout:
&#x20;           "Poznaj mnie",

&#x20;       heroBadgeTitle:
&#x20;           "Chwile. Światło. Emocje.",

&#x20;       heroBadgeText:
&#x20;           "Fotografia z pasją",

&#x20;       galleryLabel:
&#x20;           "Portfolio",

&#x20;       galleryTitle:
&#x20;           "Historie zatrzymane w czasie",

&#x20;       galleryDescription:
&#x20;           "Wybierz kolekcję i zobacz fotografie. Każdy folder to inna historia, inne światło i inne miejsce.",

&#x20;       aboutLabel:
&#x20;           "O mnie",

&#x20;       aboutTitle:
&#x20;           "Nie tylko robię zdjęcia. Zbieram chwile.",

&#x20;       aboutPhoto:
&#x20;           "Piotr · Bez Kadru",

&#x20;       socialTitle:
&#x20;           "Zobacz więcej moich kadrów",

&#x20;       socialDescription:
&#x20;           "Obserwuj mnie również w mediach społecznościowych.",

&#x20;       back:
&#x20;           "← Wróć do kolekcji",

&#x20;       visits:
&#x20;           "Odwiedziny",

&#x20;       copyright:
&#x20;           "© Wszystkie fotografie są chronione prawem autorskim. Kopiowanie i rozpowszechnianie bez zgody autora jest zabronione.",

&#x20;       photoCount:
&#x20;           "fotografii"

&#x20;   },


&#x20;   en: {

&#x20;       heroLabel:
&#x20;           "Photography",

&#x20;       heroTitle:
&#x20;           "The world captured<br><span>in a frame.</span>",

&#x20;       heroText:
&#x20;           "Photography is my way of preserving moments that can be revisited years later. Light, nature, space and emotion — these are the things I look for every time I pick up my camera.",

&#x20;       heroGallery:
&#x20;           "Explore gallery",

&#x20;       heroAbout:
&#x20;           "About me",

&#x20;       heroBadgeTitle:
&#x20;           "Moments. Light. Emotion.",

&#x20;       heroBadgeText:
&#x20;           "Photography with passion",

&#x20;       galleryLabel:
&#x20;           "Portfolio",

&#x20;       galleryTitle:
&#x20;           "Stories captured in time",

&#x20;       galleryDescription:
&#x20;           "Choose a collection and explore the photographs. Every folder tells a different story.",

&#x20;       aboutLabel:
&#x20;           "About me",

&#x20;       aboutTitle:
&#x20;           "I don't just take photos. I collect moments.",

&#x20;       aboutPhoto:
&#x20;           "Piotr · Bez Kadru",

&#x20;       socialTitle:
&#x20;           "Discover more of my photography",

&#x20;       socialDescription:
&#x20;           "Follow me on social media.",

&#x20;       back:
&#x20;           "← Back to collections",

&#x20;       visits:
&#x20;           "Visits",

&#x20;       copyright:
&#x20;           "© All photographs are protected by copyright. Copying or distributing them without permission is prohibited.",

&#x20;       photoCount:
&#x20;           "photographs"

&#x20;   },


&#x20;   de: {

&#x20;       heroLabel:
&#x20;           "Fotografie",

&#x20;       heroTitle:
&#x20;           "Die Welt eingefangen<br><span>in einem Bild.</span>",

&#x20;       heroText:
&#x20;           "Fotografie bedeutet für mich, Momente festzuhalten, zu denen man auch Jahre später zurückkehren kann. Licht, Natur, Raum und Emotionen — danach suche ich jedes Mal, wenn ich meine Kamera in die Hand nehme.",

&#x20;       heroGallery:
&#x20;           "Galerie entdecken",

&#x20;       heroAbout:
&#x20;           "Über mich",

&#x20;       heroBadgeTitle:
&#x20;           "Momente. Licht. Emotionen.",

&#x20;       heroBadgeText:
&#x20;           "Fotografie mit Leidenschaft",

&#x20;       galleryLabel:
&#x20;           "Portfolio",

&#x20;       galleryTitle:
&#x20;           "Geschichten, festgehalten in der Zeit",

&#x20;       galleryDescription:
&#x20;           "Wähle eine Sammlung und entdecke die Fotografien.",

&#x20;       aboutLabel:
&#x20;           "Über mich",

&#x20;       aboutTitle:
&#x20;           "Ich mache nicht nur Fotos. Ich sammle Momente.",

&#x20;       aboutPhoto:
&#x20;           "Piotr · Bez Kadru",

&#x20;       socialTitle:
&#x20;           "Mehr von meiner Fotografie entdecken",

&#x20;       socialDescription:
&#x20;           "Folge mir auch in den sozialen Medien.",

&#x20;       back:
&#x20;           "← Zurück zu den Sammlungen",

&#x20;       visits:
&#x20;           "Besuche",

&#x20;       copyright:
&#x20;           "© Alle Fotografien sind urheberrechtlich geschützt. Kopieren und Verbreiten ohne Genehmigung ist untersagt.",

&#x20;       photoCount:
&#x20;           "Fotografien"

&#x20;   }

};


/* =========================================================
&#x20;  FOLDER RENDER
\========================================================= */

function getFolderName(folderNumber) {

&#x20;   const names =
&#x20;       folderNames[currentLanguage];

&#x20;   const index =
&#x20;       (folderNumber - 1) % names.length;

&#x20;   return names[index];
}


function renderFolders() {

&#x20;   const grid =
&#x20;       document.getElementById(
&#x20;           "folders-grid"
&#x20;       );


&#x20;   grid.innerHTML = "";


&#x20;   const totalFolders =
&#x20;       Math.ceil(
&#x20;           totalPhotos / photosPerFolder
&#x20;       );


&#x20;   for (
&#x20;       let i = totalFolders;
&#x20;       i >= 1;
&#x20;       i--
&#x20;   ) {

&#x20;       const card =
&#x20;           document.createElement("div");


&#x20;       card.className =
&#x20;           "folder-card";


&#x20;       const artClass =
&#x20;           "art-" +
&#x20;           (((i - 1) % 8) + 1);


&#x20;       const start =
&#x20;           ((i - 1) *
&#x20;               photosPerFolder) + 1;


&#x20;       const end =
&#x20;           Math.min(
&#x20;               i * photosPerFolder,
&#x20;               totalPhotos
&#x20;           );


&#x20;       const count =
&#x20;           end - start + 1;


&#x20;       card.innerHTML = `

&#x20;           <div class="folder-art ${artClass}">
&#x20;           </div>

&#x20;           <div class="folder-number">
&#x20;               ${String(i).padStart(2, "0")}
&#x20;           </div>

&#x20;           <div class="folder-info">

&#x20;               <div class="folder-title">
&#x20;                   ${getFolderName(i)}
&#x20;               </div>

&#x20;               <div class="folder-count">
&#x20;                   ${count}
&#x20;                   ${translations[currentLanguage].photoCount}
&#x20;               </div>

&#x20;           </div>
&#x20;       `;


&#x20;       card.addEventListener(
&#x20;           "click",
&#x20;           () => openFolder(i)
&#x20;       );


&#x20;       grid.appendChild(card);
&#x20;   }
}


/* =========================================================
&#x20;  OPEN FOLDER
\========================================================= */

function openFolder(folderNumber) {

&#x20;   currentOpenFolder =
&#x20;       folderNumber;


&#x20;   document.getElementById(
&#x20;       "home-view"
&#x20;   ).style.display = "none";


&#x20;   document.getElementById(
&#x20;       "gallery-view"
&#x20;   ).style.display = "block";


&#x20;   document.getElementById(
&#x20;       "about-view"
&#x20;   ).style.display = "none";


&#x20;   document.getElementById(
&#x20;       "nav-gallery"
&#x20;   ).classList.add("active");


&#x20;   document.getElementById(
&#x20;       "nav-about"
&#x20;   ).classList.remove("active");


&#x20;   document.getElementById(
&#x20;       "folder-title-display"
&#x20;   ).textContent =
&#x20;       getFolderName(folderNumber);


&#x20;   const grid =
&#x20;       document.getElementById(
&#x20;           "photo-grid"
&#x20;       );


&#x20;   grid.innerHTML = "";


&#x20;   const start =
&#x20;       ((folderNumber - 1) *
&#x20;           photosPerFolder) + 1;


&#x20;   const end =
&#x20;       Math.min(
&#x20;           folderNumber *
&#x20;               photosPerFolder,
&#x20;           totalPhotos
&#x20;       );


&#x20;   /* Najnowsze zdjęcia pierwsze */

&#x20;   for (
&#x20;       let i = end;
&#x20;       i >= start;
&#x20;       i--
&#x20;   ) {

&#x20;       const card =
&#x20;           document.createElement("div");


&#x20;       card.className =
&#x20;           "photo-card";


&#x20;       const img =
&#x20;           document.createElement("img");


&#x20;       img.src =
&#x20;           `${i}.jpg`;


&#x20;       img.alt =
&#x20;           `Bez Kadru Photography ${i}`;


&#x20;       img.draggable = false;


&#x20;       img.onerror =
&#x20;           function () {

&#x20;               if (
&#x20;                   !this.dataset.capital
&#x20;               ) {

&#x20;                   this.dataset.capital =
&#x20;                       "1";

&#x20;                   this.src =
&#x20;                       `${i}.JPG`;

&#x20;               } else {

&#x20;                   this.parentElement.style.display =
&#x20;                       "none";
&#x20;               }

&#x20;           };


&#x20;       const protection =
&#x20;           document.createElement("div");


&#x20;       protection.className =
&#x20;           "photo-protection";


&#x20;       card.appendChild(img);

&#x20;       card.appendChild(protection);


&#x20;       card.addEventListener(
&#x20;           "click",
&#x20;           function () {

&#x20;               openLightbox(
&#x20;                   img.src
&#x20;               );

&#x20;           }
&#x20;       );


&#x20;       grid.appendChild(card);
&#x20;   }


&#x20;   window\.scrollTo({
&#x20;       top: 0,
&#x20;       behavior: "smooth"
&#x20;   });
}


/* =========================================================
&#x20;  HOME
\========================================================= */

function showHome() {

&#x20;   currentOpenFolder = null;


&#x20;   document.getElementById(
&#x20;       "home-view"
&#x20;   ).style.display = "block";


&#x20;   document.getElementById(
&#x20;       "gallery-view"
&#x20;   ).style.display = "none";


&#x20;   document.getElementById(
&#x20;       "about-view"
&#x20;   ).style.display = "none";


&#x20;   document.getElementById(
&#x20;       "nav-gallery"
&#x20;   ).classList.add("active");


&#x20;   document.getElementById(
&#x20;       "nav-about"
&#x20;   ).classList.remove("active");


&#x20;   window\.scrollTo({
&#x20;       top: 0,
&#x20;       behavior: "smooth"
&#x20;   });
}


/* =========================================================
&#x20;  ABOUT
\========================================================= */

function showAbout() {

&#x20;   document.getElementById(
&#x20;       "home-view"
&#x20;   ).style.display = "none";


&#x20;   document.getElementById(
&#x20;       "gallery-view"
&#x20;   ).style.display = "none";


&#x20;   document.getElementById(
&#x20;       "about-view"
&#x20;   ).style.display = "block";


&#x20;   document.getElementById(
&#x20;       "nav-gallery"
&#x20;   ).classList.remove("active");


&#x20;   document.getElementById(
&#x20;       "nav-about"
&#x20;   ).classList.add("active");


&#x20;   window\.scrollTo({
&#x20;       top: 0,
&#x20;       behavior: "smooth"
&#x20;   });
}


/* =========================================================
&#x20;  SCROLL TO GALLERY
\========================================================= */

function scrollToGallery() {

&#x20;   showHome();


&#x20;   setTimeout(() => {

&#x20;       document.getElementById(
&#x20;           "gallery-section"
&#x20;       ).scrollIntoView({
&#x20;           behavior: "smooth"
&#x20;       });

&#x20;   }, 50);
}


/* =========================================================
&#x20;  LIGHTBOX
\========================================================= */

function openLightbox(src) {

&#x20;   const lightbox =
&#x20;       document.getElementById(
&#x20;           "lightbox"
&#x20;       );


&#x20;   const image =
&#x20;       document.getElementById(
&#x20;           "lightbox-img"
&#x20;       );


&#x20;   image.src = src;

&#x20;   lightbox.classList.add(
&#x20;       "show"
&#x20;   );


&#x20;   document.body.style.overflow =
&#x20;       "hidden";
}


function closeLightbox() {

&#x20;   const lightbox =
&#x20;       document.getElementById(
&#x20;           "lightbox"
&#x20;       );


&#x20;   lightbox.classList.remove(
&#x20;       "show"
&#x20;   );


&#x20;   document.body.style.overflow =
&#x20;       "";
}


document
&#x20;   .getElementById("lightbox-img")
&#x20;   .addEventListener(
&#x20;       "click",
&#x20;       event => {
&#x20;           event.stopPropagation();
&#x20;       }
&#x20;   );


/* =========================================================
&#x20;  LANGUAGE
\========================================================= */

function setLanguage(lang) {

&#x20;   if (!translations[lang]) {
&#x20;       return;
&#x20;   }


&#x20;   currentLanguage = lang;


&#x20;   const t =
&#x20;       translations[lang];


&#x20;   /* buttons */

&#x20;   document
&#x20;       .querySelectorAll(".lang-btn")
&#x20;       .forEach(button => {

&#x20;           button.classList.toggle(
&#x20;               "active",
&#x20;               button.dataset.lang === lang
&#x20;           );

&#x20;       });


&#x20;   /* HERO */

&#x20;   document.getElementById(
&#x20;       "hero-label"
&#x20;   ).textContent =
&#x20;       t.heroLabel;


&#x20;   document.getElementById(
&#x20;       "hero-title"
&#x20;   ).innerHTML =
&#x20;       t.heroTitle;


&#x20;   document.getElementById(
&#x20;       "hero-text"
&#x20;   ).textContent =
&#x20;       t.heroText;


&#x20;   document.getElementById(
&#x20;       "hero-gallery-btn"
&#x20;   ).textContent =
&#x20;       t.heroGallery;


&#x20;   document.getElementById(
&#x20;       "hero-about-btn"
&#x20;   ).textContent =
&#x20;       t.heroAbout;


&#x20;   document.getElementById(
&#x20;       "hero-badge-title"
&#x20;   ).textContent =
&#x20;       t.heroBadgeTitle;


&#x20;   document.getElementById(
&#x20;       "hero-badge-text"
&#x20;   ).textContent =
&#x20;       t.heroBadgeText;


&#x20;   /* GALLERY */

&#x20;   document.getElementById(
&#x20;       "gallery-label"
&#x20;   ).textContent =
&#x20;       t.galleryLabel;


&#x20;   document.getElementById(
&#x20;       "gallery-title"
&#x20;   ).textContent =
&#x20;       t.galleryTitle;


&#x20;   document.getElementById(
&#x20;       "gallery-description"
&#x20;   ).textContent =
&#x20;       t.galleryDescription;


&#x20;   /* ABOUT */

&#x20;   document.getElementById(
&#x20;       "about-label"
&#x20;   ).textContent =
&#x20;       t.aboutLabel;


&#x20;   document.getElementById(
&#x20;       "about-title"
&#x20;   ).textContent =
&#x20;       t.aboutTitle;


&#x20;   document.getElementById(
&#x20;       "about-photo-label"
&#x20;   ).textContent =
&#x20;       t.aboutPhoto;


&#x20;   /* SOCIAL */

&#x20;   document.getElementById(
&#x20;       "social-title"
&#x20;   ).textContent =
&#x20;       t.socialTitle;


&#x20;   document.getElementById(
&#x20;       "social-description"
&#x20;   ).textContent =
&#x20;       t.socialDescription;


&#x20;   /* FOOTER */

&#x20;   document.getElementById(
&#x20;       "back-btn"
&#x20;   ).textContent =
&#x20;       t.back;


&#x20;   document.getElementById(
&#x20;       "footer-visits"
&#x20;   ).textContent =
&#x20;       t.visits;


&#x20;   document.getElementById(
&#x20;       "footer-copyright"
&#x20;   ).textContent =
&#x20;       t.copyright;


&#x20;   /* FOLDERS */

&#x20;   renderFolders();


&#x20;   /* OPEN FOLDER */

&#x20;   if (
&#x20;       currentOpenFolder !== null
&#x20;   ) {

&#x20;       document.getElementById(
&#x20;           "folder-title-display"
&#x20;       ).textContent =
&#x20;           getFolderName(
&#x20;               currentOpenFolder
&#x20;           );
&#x20;   }
}


/* =========================================================
&#x20;  LOAD PHOTOS COUNT
\========================================================= */

fetch("photos.json", {
&#x20;   cache: "no-cache"
})
.then(response => {

&#x20;   if (!response.ok) {
&#x20;       throw new Error(
&#x20;           "photos.json error"
&#x20;       );
&#x20;   }

&#x20;   return response.json();

})
.then(data => {

&#x20;   if (
&#x20;       data &&
&#x20;       Number(data.count) > 0
&#x20;   ) {

&#x20;       totalPhotos =
&#x20;           Number(data.count);

&#x20;       renderFolders();
&#x20;   }

})
.catch(error => {

&#x20;   console.warn(
&#x20;       "Nie udało się odczytać photos.json. Używam wartości domyślnej 245.",
&#x20;       error
&#x20;   );

&#x20;   renderFolders();
});


/* =========================================================
&#x20;  KEYBOARD PROTECTION
\========================================================= */

document.addEventListener(
&#x20;   "keydown",
&#x20;   function(event) {

&#x20;       /* ESC */

&#x20;       if (
&#x20;           event.key === "Escape"
&#x20;       ) {

&#x20;           closeLightbox();

&#x20;       }


&#x20;       /*
&#x20;        * Ctrl+S
&#x20;        * Ctrl+U
&#x20;        * Ctrl+C
&#x20;        * Ctrl+Shift+I
&#x20;        * Ctrl+Shift+J
&#x20;        * F12
&#x20;        */

&#x20;       const blocked =
&#x20;           event.ctrlKey ||
&#x20;           event.metaKey;


&#x20;       if (
&#x20;           blocked &&
&#x20;           (
&#x20;               event.key.toLowerCase() === "s" ||
&#x20;               event.key.toLowerCase() === "u" ||
&#x20;               event.key.toLowerCase() === "c"
&#x20;           )
&#x20;       ) {

&#x20;           event.preventDefault();

&#x20;       }


&#x20;       if (
&#x20;           event.key === "F12"
&#x20;       ) {

&#x20;           event.preventDefault();

&#x20;       }


&#x20;       if (
&#x20;           blocked &&
&#x20;           event.shiftKey &&
&#x20;           (
&#x20;               event.key === "I" ||
&#x20;               event.key === "J" ||
&#x20;               event.key === "C"
&#x20;           )
&#x20;       ) {

&#x20;           event.preventDefault();

&#x20;       }

&#x20;   }
);


/* =========================================================
&#x20;  INIT
\========================================================= */

renderFolders();

</script>
</body>
</html>
