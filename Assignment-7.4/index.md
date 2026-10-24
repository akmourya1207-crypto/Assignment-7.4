Here is your complete Assignment 7.4 — Modern Landing Page Header using HTML and CSS Flexbox. It includes a logo, navigation links, a call-to-action (CTA) button, a hero heading and paragraph, an illustration, and a footer. The layout is responsive, so the text and image sit side-by-side on larger screens and stack on smaller screens.

Save the file as Assignment-7.4.html and paste the following code into it.
Complete HTML and CSS code

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 7.4 - Modern Landing Page</title>

    <style>
        /* Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: Arial, sans-serif;
            color: #1e293b;
            background-color: #f8faff;
            line-height: 1.6;
        }

        /* Header */
        .header {
            position: sticky;
            top: 0;
            z-index: 1000;
            background-color: white;
            box-shadow: 0 2px 10px #0000000d;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 25px;
            max-width: 1200px;
            margin: 0 auto;
            padding: 18px 25px;
        }

        /* Logo */
        .logo {
            color: #2457d6;
            font-size: 27px;
            font-weight: bold;
            text-decoration: none;
            white-space: nowrap;
        }

        .logo span {
            color: #172554;
        }

        /* Navigation links */
        .nav-links {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 25px;
            list-style: none;
        }

        .nav-links a {
            color: #475569;
            text-decoration: none;
            font-size: 15px;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #2457d6;
        }

        /* Buttons */
        .button {
            display: inline-block;
            padding: 13px 23px;
            border-radius: 8px;
            font-size: 15px;
            font-weight: bold;
            text-decoration: none;
            text-align: center;
            cursor: pointer;
            transition: background-color 0.3s,
                        transform 0.3s;
        }

        .button-primary {
            background-color: #2457d6;
            color: white;
            border: 2px solid #2457d6;
        }

        .button-primary:hover {
            background-color: #173ea8;
            border-color: #173ea8;
            transform: translateY(-2px);
        }

        .button-secondary {
            color: #2457d6;
            background-color: white;
            border: 2px solid #d6e1ff;
        }

        .button-secondary:hover {
            background-color: #edf2ff;
        }

        /* Hero section */
        .hero {
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 50px;
            max-width: 1200px;
            min-height: 600px;
            margin: 0 auto;
            padding: 70px 25px;
        }

        .hero-content {
            flex: 1 1 50%;
            min-width: 0;
        }

        .hero-label {
            display: inline-block;
            padding: 7px 14px;
            margin-bottom: 20px;
            background-color: #e6edff;
            color: #2457d6;
            border-radius: 20px;
            font-size: 13px;
            font-weight: bold;
        }

        .hero h1 {
            color: #172554;
            font-size: clamp(36px, 5vw, 58px);
            line-height: 1.15;
            margin-bottom: 22px;
        }

        .hero h1 span {
            color: #2457d6;
        }

        .hero-description {
            max-width: 520px;
            color: #64748b;
            font-size: 17px;
            margin-bottom: 28px;
        }

        .hero-buttons {
            display: flex;
            align-items: center;
            flex-wrap: wrap;
            gap: 14px;
            margin-bottom: 30px;
        }

        .hero-note {
            color: #64748b;
            font-size: 14px;
        }

        /* Hero illustration */
        .hero-image {
            flex: 1 1 50%;
            min-width: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .illustration {
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            max-width: 480px;
            aspect-ratio: 1 / 1;
            background: linear-gradient(
                135deg,
                #dbeafe,
                #e9e7ff,
                #f1f5ff
            );
            border-radius: 35% 65% 60% 40% / 45% 40% 60% 55%;
        }

        .illustration-card {
            position: relative;
            z-index: 2;
            width: 75%;
            padding: 28px 20px;
            background-color: white;
            border: 1px solid #e2e8f0;
            border-radius: 20px;
            box-shadow: 0 15px 40px #233c781c;
            text-align: center;
            transform: rotate(-3deg);
        }

        .illustration-icon {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100px;
            height: 100px;
            margin: 0 auto 18px;
            background: linear-gradient(135deg, #2457d6, #8b5cf6);
            color: white;
            border-radius: 25px;
            font-size: 48px;
        }

        .illustration-card h2 {
            color: #172554;
            margin-bottom: 8px;
            font-size: 23px;
        }

        .illustration-card p {
            color: #64748b;
            font-size: 14px;
        }

        .floating-badge {
            position: absolute;
            top: 12%;
            right: 2%;
            z-index: 3;
            padding: 12px 18px;
            background-color: white;
            color: #159b62;
            border-radius: 12px;
            box-shadow: 0 5px 20px #00000012;
            font-size: 14px;
            font-weight: bold;
        }

        .floating-dot {
            position: absolute;
            bottom: 12%;
            left: 3%;
            width: 65px;
            height: 65px;
            background-color: #fbbf24;
            border-radius: 50%;
        }

        /* Features section */
        .features {
            padding: 65px 25px;
            background-color: white;
            text-align: center;
        }

        .features h2 {
            color: #172554;
            font-size: 32px;
            margin-bottom: 12px;
        }

        .features-intro {
            color: #64748b;
            margin-bottom: 35px;
        }

        .feature-container {
            display: flex;
            justify-content: center;
            align-items: stretch;
            flex-wrap: wrap;
            gap: 22px;
            max-width: 1100px;
            margin: 0 auto;
        }

        .feature-card {
            flex: 1 1 230px;
            max-width: 330px;
            padding: 25px;
            border: 1px solid #e2e8f0;
            border-radius: 12px;
            background-color: #f8faff;
        }

        .feature-card h3 {
            color: #2457d6;
            margin-bottom: 10px;
        }

        .feature-card p {
            color: #64748b;
            font-size: 15px;
        }

        /* Footer */
        .footer {
            padding: 25px 20px;
            background-color: #172554;
            color: white;
            text-align: center;
        }

        .footer p {
            font-size: 14px;
        }

        /* Tablet and mobile responsive layout */
        @media (max-width: 850px) {
            .navbar {
                flex-wrap: wrap;
                justify-content: center;
            }

            .logo {
                width: 100%;
                text-align: center;
            }

            .nav-links {
                flex-wrap: wrap;
                gap: 18px;
            }

            .hero {
                flex-direction: column;
                text-align: center;
                gap: 35px;
                padding: 55px 22px;
            }

            .hero-content {
                width: 100%;
            }

            .hero-description {
                margin-left: auto;
                margin-right: auto;
            }

            .hero-buttons {
                justify-content: center;
            }

            .hero-image {
                width: 100%;
            }

            .illustration {
                max-width: 420px;
            }
        }

        @media (max-width: 480px) {
            .navbar {
                gap: 15px;
                padding: 15px 12px;
            }

            .nav-links {
                gap: 12px;
            }

            .nav-links a {
                font-size: 13px;
            }

            .navbar > .button {
                padding: 10px 15px;
            }

            .hero {
                padding: 40px 18px;
            }

            .hero h1 {
                font-size: 36px;
            }

            .hero-description {
                font-size: 15px;
            }

            .button {
                padding: 11px 16px;
                font-size: 14px;
            }

            .illustration-card {
                padding: 22px 12px;
            }

            .illustration-icon {
                width: 75px;
                height: 75px;
                font-size: 36px;
            }

            .illustration-card h2 {
                font-size: 19px;
            }

            .floating-badge {
                padding: 8px 11px;
                font-size: 12px;
            }

            .features h2 {
                font-size: 26px;
            }
        }
    </style>
</head>

<body>

    <!-- Website header -->
    <header class="header">
        <nav class="navbar">

            <a href="#home" class="logo">
                Bright<span>Web.</span>
            </a>

            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>

            <a href="#contact" class="button button-primary">
                Get Started
            </a>

        </nav>
    </header>

    <!-- Hero section -->
    <main>
        <section class="hero" id="home">

            <div class="hero-content">

                <span class="hero-label">
                    ✨ WELCOME TO BRIGHTWEB
                </span>

                <h1>
                    Build Your Ideas Into
                    <span>Reality.</span>
                </h1>

                <p class="hero-description">
                    Create beautiful, modern, and responsive websites
                    with simple design principles. Turn your ideas
                    into amazing digital experiences with BrightWeb.
                </p>

                <div class="hero-buttons">
                    <a href="#features"
                       class="button button-primary">
                        Explore Features →
                    </a>

                    <a href="#about"
                       class="button button-secondary">
                        Learn More
                    </a>
                </div>

                <p class="hero-note">
                    ✔ Modern Design &nbsp; ✔ Responsive Layout
                </p>

            </div>

            <!-- CSS illustration -->
            <div class="hero-image" id="about">

                <div class="illustration">

                    <div class="floating-dot"></div>

                    <div class="illustration-card">
                        <div class="illustration-icon">
                            &lt;/&gt;
                        </div>

                        <h2>Creative Design</h2>

                        <p>
                            Design. Develop. Deliver.
                        </p>
                    </div>

                    <div class="floating-badge">
                        ✓ 100% Responsive
                    </div>

                </div>

            </div>

        </section>

        <!-- Features section -->
        <section class="features" id="features">

            <h2>Why Choose BrightWeb?</h2>

            <p class="features-intro">
                Everything you need to create a great website.
            </p>

            <div class="feature-container">

                <article class="feature-card">
                    <h3>🎨 Modern Design</h3>
                    <p>
                        Clean layouts, attractive colors, and
                        simple user-friendly interfaces.
                    </p>
                </article>

                <article class="feature-card">
                    <h3>📱 Responsive</h3>
                    <p>
                        Layouts that adapt to desktops,
                        tablets, and mobile screens.
                    </p>
                </article>

                <article class="feature-card">
                    <h3>⚡ Easy to Use</h3>
                    <p>
                        Simple navigation and clear content
                        help visitors find what they need.
                    </p>
                </article>

            </div>

        </section>

    </main>

    <!-- Footer -->
    <footer class="footer" id="contact">
        <p>Contact: student@example.com</p>
        <p>Assignment 7.4 - Modern Landing Page Header</p>
        <p>Created using HTML and CSS Flexbox.</p>
    </footer>

</body>
</html>



How this assignment meets the requirements
Requirement	Implementation
Logo and navigation links	BrightWeb. logo with four navigation links
CTA button	“Get Started” button in the header
Hero heading and paragraph	Main heading, description, and two action buttons
Illustration	Custom CSS illustration with a floating badge
Side-by-side layout	display: flex and justify-content: space-between
Content alignment	align-items: center
Footer	Dark footer with contact information
Sticky header	position: sticky; top: 0
Responsive design	Media queries for tablets and mobile screens

How to run and submit
1. Open Notepad or Visual Studio Code.
2. Paste the complete code and save it as Assignment-7.4.html.
3. Open the saved file in Chrome.
4. Resize the browser to check the desktop and mobile layouts.
5. Take a screenshot using Win + Shift + S.
Submission: Include Assignment-7.4.html and a screenshot named Assignment-7.4-Screenshot.png.

The illustration is created entirely with CSS, so you do not need to download a separate image file.