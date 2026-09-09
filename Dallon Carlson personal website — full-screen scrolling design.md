```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Dallon Carlson</title>

<meta name="description" content="Dallon Carlson — physics graduate student working on Bayesian detection of supermassive black hole binaries in AGN time-domain data.">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>

  /* =========================================================
     VARIABLES
     ========================================================= */

  :root{
    --bg: #080c14;
    --panel: #0e141f;
    --panel-hover: #111925;
    --line: #273142;

    --text: #dce3ec;
    --muted: #7c8798;

    --signal: #5bc8d9;
    --signal-dim: rgba(91,200,217,0.20);
    --signal-faint: rgba(91,200,217,0.06);

    --warm: #e8a33d;

    --radius: 4px;
    --maxw: 1100px;

    --transition: 700ms cubic-bezier(0.22, 1, 0.36, 1);
  }


  /* =========================================================
     RESET
     ========================================================= */

  *{
    box-sizing: border-box;
  }

  html{
    scroll-behavior: smooth;
  }

  body{
    margin: 0;
    background: var(--bg);
    color: var(--text);

    font-family: 'IBM Plex Sans', system-ui, sans-serif;
    font-size: 17px;
    line-height: 1.65;

    -webkit-font-smoothing: antialiased;

    overflow-x: hidden;
  }

  a{
    color: var(--signal);
    text-decoration: none;
  }

  a:hover{
    text-decoration: underline;
    text-underline-offset: 4px;
  }

  a:focus-visible{
    outline: 2px solid var(--signal);
    outline-offset: 4px;
  }

  h1, h2, h3{
    font-family: 'Space Grotesk', sans-serif;
    font-weight: 600;
    color: #fff;
    margin: 0;
  }


  /* =========================================================
     BACKGROUND GRID
     ========================================================= */

  body::before{
    content: "";
    position: fixed;
    inset: 0;

    pointer-events: none;

    opacity: 0.16;

    background-image:
      linear-gradient(rgba(91,200,217,0.035) 1px, transparent 1px),
      linear-gradient(90deg, rgba(91,200,217,0.035) 1px, transparent 1px);

    background-size: 48px 48px;

    mask-image: linear-gradient(
      to bottom,
      black,
      transparent 85%
    );

    z-index: -2;
  }


  /* =========================================================
     MAIN WRAPPER
     ========================================================= */

  .wrap{
    width: min(var(--maxw), calc(100% - 56px));
    margin: 0 auto;
  }


  /* =========================================================
     HEADER
     ========================================================= */

  header.site{
    position: relative;
    z-index: 20;

    padding: 28px 0 0;
  }

  header.site .wrap{
    display: flex;
    justify-content: space-between;
    align-items: baseline;

    flex-wrap: wrap;

    gap: 10px 24px;

    border-bottom: 1px solid var(--line);

    padding-bottom: 20px;
  }

  .mark{
    font-family: 'IBM Plex Mono', monospace;
    font-size: 13px;

    color: var(--muted);

    letter-spacing: 0.02em;
  }

  header nav{
    display: flex;
    gap: 24px;

    font-family: 'IBM Plex Mono', monospace;
    font-size: 13px;
  }

  header nav a{
    color: var(--muted);

    transition:
      color 200ms ease;
  }

  header nav a:hover{
    color: var(--signal);
    text-decoration: none;
  }


  /* =========================================================
     HERO
     ========================================================= */

  .hero{
    min-height: 88vh;

    display: flex;
    flex-direction: column;
    justify-content: center;

    position: relative;

    padding: 80px 0;
  }

  .hero::after{
    content: "";

    position: absolute;

    left: 0;
    bottom: 0;

    width: 100%;
    height: 1px;

    background: linear-gradient(
      90deg,
      transparent,
      var(--line),
      transparent
    );
  }

  .kicker{
    font-family: 'IBM Plex Mono', monospace;

    color: var(--signal);

    font-size: 13px;

    letter-spacing: 0.08em;
    text-transform: uppercase;

    margin-bottom: 20px;
  }

  .hero h1{
    font-size: clamp(54px, 9vw, 100px);

    line-height: 0.95;

    letter-spacing: -0.045em;

    max-width: 8ch;
  }

  .hero .role{
    color: var(--muted);

    font-size: clamp(18px, 2vw, 21px);

    max-width: 600px;

    margin: 30px 0 0;
  }

  .hero-meta{
    display: flex;

    flex-wrap: wrap;

    gap: 12px 28px;

    margin-top: 48px;

    font-family: 'IBM Plex Mono', monospace;

    font-size: 12px;

    color: var(--muted);
  }

  .hero-meta span::before{
    content: "●";

    color: var(--signal);

    margin-right: 8px;

    font-size: 8px;
  }


  /* =========================================================
     SECTION SYSTEM
     ========================================================= */

  .section{
    min-height: 100vh;

    display: flex;
    align-items: center;

    padding: 80px 0;

    position: relative;
  }

  .section-inner{
    width: 100%;

    position: relative;

    padding: 70px 64px;

    background:
      linear-gradient(
        145deg,
        rgba(17,25,37,0.96),
        rgba(10,15,24,0.96)
      );

    border: 1px solid var(--line);

    border-radius: var(--radius);

    box-shadow:
      0 30px 80px rgba(0,0,0,0.22);

    overflow: hidden;

    transform:
      translateY(45px)
      scale(0.97);

    opacity: 0.45;

    transition:
      transform var(--transition),
      opacity var(--transition),
      border-color var(--transition),
      box-shadow var(--transition);
  }

  /*
     The section becomes "active" when the browser's
     IntersectionObserver adds this class.
  */

  .section.active .section-inner{
    transform:
      translateY(0)
      scale(1);

    opacity: 1;

    border-color:
      rgba(91,200,217,0.45);

    box-shadow:
      0 40px 100px rgba(0,0,0,0.35),
      0 0 80px rgba(91,200,217,0.035);
  }


  /* =========================================================
     HUGE SECTION NUMBER
     ========================================================= */

  .section-number{
    position: absolute;

    top: -45px;
    right: 20px;

    font-family: 'Space Grotesk', sans-serif;

    font-size: clamp(160px, 25vw, 300px);

    font-weight: 600;

    line-height: 1;

    color: rgba(91,200,217,0.035);

    letter-spacing: -0.08em;

    pointer-events: none;

    user-select: none;
  }


  /* =========================================================
     SECTION HEADER
     ========================================================= */

  .section-label{
    position: relative;
    z-index: 2;

    display: flex;
    align-items: center;

    gap: 14px;

    margin-bottom: 40px;

    font-family: 'IBM Plex Mono', monospace;

    font-size: 12px;

    color: var(--signal);

    text-transform: uppercase;

    letter-spacing: 0.08em;
  }

  .section-label::before{
    content: "";

    display: block;

    width: 28px;
    height: 1px;

    background: var(--signal);
  }

  .section-title{
    position: relative;
    z-index: 2;

    font-size: clamp(34px, 5vw, 54px);

    line-height: 1.05;

    letter-spacing: -0.035em;

    margin-bottom: 30px;
  }


  /* =========================================================
     ABOUT
     ========================================================= */

  .about-content{
    position: relative;
    z-index: 2;

    max-width: 720px;
  }

  .about-content p{
    font-size: 19px;

    color: var(--muted);

    margin: 0 0 22px;
  }

  .about-content p:last-child{
    margin-bottom: 0;
  }

  .highlight{
    color: var(--text);
  }


  /* =========================================================
     RESEARCH
     ========================================================= */

  .research-grid{
    position: relative;
    z-index: 2;

    display: grid;

    grid-template-columns:
      minmax(0, 1fr)
      180px;

    gap: 50px;
  }

  .project{
    padding: 26px 0;

    border-top: 1px solid var(--line);
  }

  .project:first-child{
    padding-top: 0;

    border-top: none;
  }

  .project-icon{
    width: 46px;
    height: 46px;

    margin-bottom: 18px;
  }

  .project-icon path,
  .project-icon circle{
    vector-effect: non-scaling-stroke;
  }

  .project h3{
    font-size: 22px;

    margin-bottom: 10px;
  }

  .project p{
    color: var(--muted);

    margin: 0;

    max-width: 680px;
  }

  .research-aside{
    align-self: start;

    border-left: 1px solid var(--line);

    padding-left: 24px;
  }

  .aside-label{
    font-family: 'IBM Plex Mono', monospace;

    font-size: 11px;

    color: var(--muted);

    text-transform: uppercase;

    letter-spacing: 0.08em;

    margin-bottom: 12px;
  }

  .aside-value{
    font-family: 'IBM Plex Mono', monospace;

    color: var(--signal);

    font-size: 13px;

    line-height: 1.8;
  }


  /* =========================================================
     PUBLICATIONS
     ========================================================= */

  .pub-list{
    position: relative;
    z-index: 2;

    list-style: none;

    padding: 0;
    margin: 0;

    max-width: 850px;
  }

  .pub-list li{
    display: grid;

    grid-template-columns: 48px 1fr;

    gap: 22px;

    padding: 28px 0;

    border-top: 1px solid var(--line);
  }

  .pub-list li:first-child{
    border-top: none;
  }

  .pub-number{
    font-family: 'IBM Plex Mono', monospace;

    font-size: 13px;

    color: var(--muted);
  }

  .cite{
    color: var(--text);

    line-height: 1.7;
  }

  .cite strong{
    color: #fff;
  }

  .venue{
    color: var(--muted);
  }

  .pub-links{
    margin-top: 12px;

    font-family: 'IBM Plex Mono', monospace;

    font-size: 12px;
  }

  .pub-links a{
    margin-right: 20px;
  }


  /* =========================================================
     CONTACT
     ========================================================= */

  .contact-grid{
    position: relative;
    z-index: 2;

    display: grid;

    grid-template-columns:
      repeat(2, minmax(0, 1fr));

    gap: 1px;

    background: var(--line);

    border: 1px solid var(--line);

    max-width: 850px;
  }

  .contact-item{
    background: var(--panel);

    padding: 28px;
  }

  .contact-key{
    font-family: 'IBM Plex Mono', monospace;

    color: var(--muted);

    font-size: 11px;

    text-transform: uppercase;

    letter-spacing: 0.08em;

    margin-bottom: 8px;
  }

  .contact-value{
    font-size: 16px;
  }

  .department{
    color: var(--muted);
  }


  /* =========================================================
     SCROLL INDICATOR
     ========================================================= */

  .scroll-indicator{
    position: fixed;

    right: 28px;
    top: 50%;

    transform: translateY(-50%);

    display: flex;

    flex-direction: column;

    align-items: center;

    gap: 10px;

    z-index: 30;
  }

  .scroll-dot{
    width: 6px;
    height: 6px;

    border-radius: 50%;

    background: var(--line);

    transition:
      background 250ms ease,
      transform 250ms ease;
  }

  .scroll-dot.active{
    background: var(--signal);

    transform: scale(1.7);

    box-shadow:
      0 0 12px var(--signal-dim);
  }


  /* =========================================================
     FOOTER
     ========================================================= */

  footer{
    padding: 50px 0 70px;

    color: var(--muted);

    font-family: 'IBM Plex Mono', monospace;

    font-size: 12px;
  }

  footer .wrap{
    display: flex;

    justify-content: space-between;

    gap: 20px;

    border-top: 1px solid var(--line);

    padding-top: 24px;
  }


  /* =========================================================
     SMALL DECORATIVE DATA MARKERS
     ========================================================= */

  .data-marker{
    position: absolute;

    bottom: 22px;
    left: 64px;

    font-family: 'IBM Plex Mono', monospace;

    font-size: 10px;

    color: var(--muted);

    opacity: 0.6;

    z-index: 2;
  }

  .data-marker span{
    color: var(--signal);
  }


  /* =========================================================
     MOBILE
     ========================================================= */

  @media (max-width: 700px){

    .wrap{
      width: min(100% - 32px, var(--maxw));
    }

    header.site{
      padding-top: 20px;
    }

    header.site .wrap{
      align-items: flex-start;

      flex-direction: column;
    }

    header nav{
      gap: 16px;

      flex-wrap: wrap;
    }

    .hero{
      min-height: 80vh;

      padding: 60px 0;
    }

    .hero h1{
      font-size: clamp(52px, 18vw, 80px);
    }

    .section{
      min-height: auto;

      padding: 40px 0;
    }

    .section-inner{
      padding: 45px 26px;

      transform:
        translateY(25px)
        scale(0.985);
    }

    .section-number{
      top: -10px;
      right: -5px;

      font-size: 150px;
    }

    .research-grid{
      grid-template-columns: 1fr;

      gap: 30px;
    }

    .research-aside{
      border-left: none;

      border-top: 1px solid var(--line);

      padding-left: 0;
      padding-top: 20px;
    }

    .contact-grid{
      grid-template-columns: 1fr;
    }

    .scroll-indicator{
      display: none;
    }

    .data-marker{
      left: 26px;
      bottom: 14px;
    }

    footer .wrap{
      flex-direction: column;
    }
  }


  /* =========================================================
     REDUCED MOTION
     ========================================================= */

  @media (prefers-reduced-motion: reduce){

    html{
      scroll-behavior: auto;
    }

    .section-inner{
      transform: none;
      opacity: 1;
      transition: none;
    }

  }

</style>
</head>


<body>


<!-- =========================================================
     HEADER
     ========================================================= -->

<header class="site">

  <div class="wrap">

    <span class="mark">
      dallon-carlson.github.io
    </span>

    <nav>
      <a href="#about">About</a>
      <a href="#research">Research</a>
      <a href="#publications">Publications</a>
      <a href="#contact">Contact</a>
    </nav>

  </div>

</header>


<!-- =========================================================
     HERO
     ========================================================= -->

<main>

  <div class="wrap">

    <section class="hero">

      <div class="kicker">
        gravitational-wave &amp; time-domain astrophysics
      </div>

      <h1>
        Dallon Carlson
      </h1>

      <p class="role">
        PhD student working on Bayesian methods for detecting
        supermassive black hole binaries hidden in quasar
        light curves and pulsar timing data.
      </p>

      <div class="hero-meta">
        <span>AGN variability</span>
        <span>Bayesian inference</span>
        <span>SMBHBs</span>
        <span>Gravitational waves</span>
      </div>

    </section>


    <!-- =====================================================
         ABOUT
         ===================================================== -->

    <section class="section" id="about">

      <div class="section-inner">

        <div class="section-number">
          01
        </div>

        <div class="section-label">
          about
        </div>

        <h2 class="section-title">
          About
        </h2>

        <div class="about-content">

          <p>
            I am a PhD student in physics working in the
            <span class="highlight">Caitlin Witt research group</span>.
            My research focuses on Bayesian detection methods for
            supermassive black hole binary (SMBHB) signals in AGN
            time-domain survey data.
          </p>

          <p>
            I'm broadly interested in gravitational-wave astrophysics,
            statistical inference, and time-domain surveys of active
            galactic nuclei.
          </p>

        </div>

        <div class="data-marker">
          STATUS: <span>ACTIVE</span>
        </div>

      </div>

    </section>


    <!-- =====================================================
         RESEARCH
         ===================================================== -->

    <section class="section" id="research">

      <div class="section-inner">

        <div class="section-number">
          02
        </div>

        <div class="section-label">
          research
        </div>

        <h2 class="section-title">
          Research
        </h2>

        <div class="research-grid">

          <div>

            <div class="project">

              <svg class="project-icon"
                   viewBox="0 0 44 44"
                   fill="none">

                <path
                  d="M2,30 Q11,10 22,22 T42,14"
                  stroke="#5bc8d9"
                  stroke-width="2"
                  stroke-linecap="round"
                />

                <path
                  d="M2,34 Q11,23 20,28 T42,24"
                  stroke="#273142"
                  stroke-width="1"
                  stroke-linecap="round"
                />

              </svg>

              <h3>
                SMBHB detection in quasar light curves
              </h3>

              <p>
                An injection-recovery pipeline for identifying periodic
                (CW and sawtooth) signals against damped-random-walk AGN
                variability, using UltraNest nested sampling and survey
                cadences drawn from CRTS and LSST. Current work compares
                candidate waveform templates via Bayesian evidence to
                characterize detection sensitivity.
              </p>

            </div>


            <div class="project">

              <svg class="project-icon"
                   viewBox="0 0 44 44"
                   fill="none">

                <circle
                  cx="22"
                  cy="22"
                  r="16"
                  stroke="#3a4557"
                  stroke-width="2"
                  stroke-dasharray="3 4"
                />

                <circle
                  cx="22"
                  cy="22"
                  r="4"
                  fill="#5bc8d9"
                  opacity="0.7"
                />

              </svg>

              <h3>
                Next project
              </h3>

              <p>
                Add a short description here as new work develops.
              </p>

            </div>

          </div>


          <aside class="research-aside">

            <div class="aside-label">
              Current focus
            </div>

            <div class="aside-value">
              AGN<br>
              SMBHB<br>
              LSST<br>
              Bayesian inference
            </div>

          </aside>

        </div>

        <div class="data-marker">
          FIELD: <span>TIME-DOMAIN</span>
        </div>

      </div>

    </section>


    <!-- =====================================================
         PUBLICATIONS
         ===================================================== -->

    <section class="section" id="publications">

      <div class="section-inner">

        <div class="section-number">
          03
        </div>

        <div class="section-label">
          publications
        </div>

        <h2 class="section-title">
          Publications
        </h2>

        <ul class="pub-list">

          <li>

            <span class="pub-number">
              01
            </span>

            <div>

              <div class="cite">

                Elisabeth R. Adams;
                Brian Jackson;
                Amanda A. Sickafoose;
                Jeffrey P. Morgenthaler;
                Hannah Worters;
                Hailey Stubbers;
                <strong>Dallon Carlson</strong> et al.

                <i>
                  "Doomed Worlds. I. No New Evidence for Orbital
                  Decay in a Long-term Survey of 43 Ultrahot Jupiters."
                </i>

                <span class="venue">
                  PSJ, 2024
                </span>

              </div>

              <div class="pub-links">

                <a href="https://iopscience.iop.org/article/10.3847/PSJ/ad3e80">
                  IOP
                </a>

                <a href="#">
                  PDF
                </a>

              </div>

            </div>

          </li>

        </ul>

        <div class="data-marker">
          RECORDS: <span>01</span>
        </div>

      </div>

    </section>


    <!-- =====================================================
         CONTACT
         ===================================================== -->

    <section class="section" id="contact">

      <div class="section-inner">

        <div class="section-number">
          04
        </div>

        <div class="section-label">
          contact
        </div>

        <h2 class="section-title">
          Contact
        </h2>

        <div class="contact-grid">

          <div class="contact-item">

            <div class="contact-key">
              email
            </div>

            <div class="contact-value">
              <a href="mailto:carldd25@wfu.edu">
                carldd25@wfu.edu
              </a>
            </div>

          </div>


          <div class="contact-item">

            <div class="contact-key">
              github
            </div>

            <div class="contact-value">
              <a href="https://github.com/dallon-carlson">
                dallon-carlson
              </a>
            </div>

          </div>


          <div class="contact-item">

            <div class="contact-key">
              cv
            </div>

            <div class="contact-value">
              <a href="/cv.pdf">
                download PDF
              </a>
            </div>

          </div>


          <div class="contact-item">

            <div class="contact-key">
              department
            </div>

            <div class="contact-value department">
              Department of Physics<br>
              Wake Forest University
            </div>

          </div>

        </div>

        <div class="data-marker">
          CONNECTION: <span>OPEN</span>
        </div>

      </div>

    </section>

  </div>

</main>


<!-- =========================================================
     SCROLL INDICATOR
     ========================================================= -->

<div class="scroll-indicator"
     aria-hidden="true">

  <div class="scroll-dot active"></div>
  <div class="scroll-dot"></div>
  <div class="scroll-dot"></div>
  <div class="scroll-dot"></div>

</div>


<!-- =========================================================
     FOOTER
     ========================================================= -->

<footer>

  <div class="wrap">

    <span>
      © 2026 Dallon Carlson
    </span>

    <span>
      WFU · PHYSICS
    </span>

  </div>

</footer>


<!-- =========================================================
     JAVASCRIPT
     ========================================================= -->

<script>

  /*
   * Activate sections as they enter the viewport.
   *
   * This gives the cards the "pop into focus" effect
   * without requiring any external libraries.
   */

  const sections =
    document.querySelectorAll('.section');

  const dots =
    document.querySelectorAll('.scroll-dot');


  const observer =
    new IntersectionObserver(

      (entries) => {

        entries.forEach(entry => {

          if(entry.isIntersecting){

            entry.target.classList.add('active');

            const index =
              [...sections].indexOf(entry.target);

            dots.forEach((dot, i) => {

              dot.classList.toggle(
                'active',
                i === index
              );

            });

          }

        });

      },

      {
        threshold: 0.45
      }

    );


  sections.forEach(section => {

    observer.observe(section);

  });


  /*
   * Make the navigation feel slightly more deliberate.
   */

  document.querySelectorAll('header nav a')
    .forEach(link => {

      link.addEventListener('click', () => {

        const target =
          document.querySelector(
            link.getAttribute('href')
          );

        if(target){

          target.scrollIntoView({
            behavior: 'smooth',
            block: 'center'
          });

        }

      });

    });

</script>


</body>
</html>
```