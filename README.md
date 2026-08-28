<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Waxoyl Polska — Professional Car Care</title>
  <style>
    :root {
      --red: #e30613;
      --red-dark: #b8000a;
      --black: #070707;
      --dark: #101010;
      --line: #292929;
      --text: #ffffff;
      --muted: #999999;
    }

    * { box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      background: var(--black);
      color: var(--text);
      font-family: Arial, Helvetica, sans-serif;
    }

    button, input, textarea { font: inherit; }

    .container {
      width: min(1280px, 100%);
      margin: 0 auto;
      padding: 0 40px;
    }

    /* =========================
       HEADER
       ========================= */

    .header {
      position: sticky;
      top: 0;
      z-index: 1000;
      height: 88px;
      background: rgba(5,5,5,.97);
      border-bottom: 1px solid var(--line);
      display: flex;
      align-items: center;
      padding: 0 40px;
      gap: 35px;
    }

    .logo {
      width: 90px;
      height: 70px;
      object-fit: contain;
      flex-shrink: 0;
    }

    .navigation {
      margin-left: auto;
      display: flex;
      align-items: center;
      gap: 32px;
    }

    .navigation a {
      color: #fff;
      text-decoration: none;
      font-size: 13px;
      font-weight: 800;
      letter-spacing: .4px;
      white-space: nowrap;
      padding: 32px 0;
      border-bottom: 2px solid transparent;
      transition: .2s;
    }

    .navigation a:hover,
    .navigation a.active {
      color: #fff;
      border-color: var(--red);
    }

    .home {
      color: var(--red) !important;
      font-size: 22px !important;
    }

    /* =========================
       HERO
       ========================= */

    .hero {
      min-height: 560px;
      position: relative;
      overflow: hidden;
      display: flex;
      align-items: center;
      background:
        radial-gradient(circle at 78% 50%, rgba(227,6,19,.22), transparent 28%),
        linear-gradient(110deg, #050505 0%, #171717 100%);
    }

    .hero::after {
      content: "WAXOYL";
      position: absolute;
      right: -50px;
      bottom: -65px;
      font-size: 180px;
      font-weight: 900;
      letter-spacing: -10px;
      color: rgba(255,255,255,.025);
      pointer-events: none;
    }

    .hero-content {
      position: relative;
      z-index: 2;
      max-width: 700px;
      padding: 95px 0;
    }

    .eyebrow {
      color: var(--red);
      font-size: 11px;
      font-weight: 900;
      letter-spacing: 2px;
      text-transform: uppercase;
    }

    h1 {
      font-size: clamp(42px, 6vw, 68px);
      line-height: .94;
      letter-spacing: -3px;
      margin: 15px 0 22px;
      font-weight: 950;
    }

    h1 span { color: var(--red); }

    .hero p,
    .lead {
      color: #c8c8c8;
      font-size: 15px;
      line-height: 1.7;
      max-width: 650px;
    }

    .buttons {
      display: flex;
      gap: 12px;
      margin-top: 30px;
      flex-wrap: wrap;
    }

    .btn {
      border: 1px solid #666;
      background: transparent;
      color: #fff;
      padding: 14px 22px;
      font-size: 10px;
      font-weight: 900;
      letter-spacing: .5px;
      cursor: pointer;
      transition: .2s;
    }

    .btn:hover {
      background: #fff;
      color: #111;
      border-color: #fff;
    }

    .btn.red {
      background: var(--red);
      border-color: var(--red);
    }

    .btn.red:hover {
      background: #ff1b27;
      color: #fff;
    }

    /* =========================
       FOUR MAIN AREAS
       ========================= */

    .tiles {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      border-top: 1px solid #333;
      border-bottom: 1px solid #333;
    }

    .tile {
      min-height: 205px;
      padding: 30px 25px;
      border-right: 1px solid #333;
      background: linear-gradient(145deg, #151515, #090909);
      transition: .2s;
    }

    .tile:last-child { border-right: 0; }

    .tile:hover {
      background: linear-gradient(145deg, #1c1c1c, #0b0b0b);
      transform: translateY(-2px);
    }

    .tile .icon {
      color: var(--red);
      font-size: 28px;
      margin-bottom: 16px;
    }

    .tile h3 {
      font-size: 15px;
      margin: 0 0 10px;
    }

    .tile p {
      color: #999;
      font-size: 11px;
      line-height: 1.55;
      margin: 0;
    }

    .tile a {
      display: block;
      margin-top: 20px;
      color: var(--red);
      font-size: 9px;
      font-weight: 900;
    }

    /* =========================
       GENERAL SECTIONS
       ========================= */

    .section {
      padding: 80px 0;
    }

    .section.dark {
      background: #0b0b0b;
    }

    .section h2 {
      font-size: clamp(36px, 5vw, 52px);
      line-height: 1;
      letter-spacing: -2px;
      margin: 10px 0 18px;
    }

    .split {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 55px;
      align-items: center;
    }

    .feature-list { margin-top: 30px; }

    .feature {
      display: flex;
      gap: 17px;
      padding: 17px 0;
      border-bottom: 1px solid var(--line);
    }

    .feature > b {
      color: var(--red);
      font-size: 17px;
    }

    .feature strong { font-size: 13px; }

    .feature p {
      margin: 4px 0 0;
      color: #888;
      font-size: 10px;
      line-height: 1.5;
    }

    .visual {
      min-height: 360px;
      border: 1px solid var(--line);
      display: flex;
      align-items: center;
      justify-content: center;
      background:
        radial-gradient(circle, rgba(227,6,19,.22), transparent 42%),
        linear-gradient(145deg, #191919, #070707);
    }

    .visual img {
      width: 230px;
      height: 230px;
      object-fit: contain;
    }

    /* =========================
       PRODUCTS
       ========================= */

    .products-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 15px;
      margin-top: 35px;
    }

    .product {
      min-height: 330px;
      padding: 22px;
      text-align: center;
      background: #111;
      border: 1px solid var(--line);
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
    }

    .product-bottle {
      width: 65px;
      height: 165px;
      margin: auto auto 20px;
      border-radius: 5px 5px 10px 10px;
      background: linear-gradient(90deg, #080808, #444, #090909);
      position: relative;
      box-shadow: 0 25px 35px rgba(227,6,19,.25);
    }

    .product-bottle::before {
      content: "";
      position: absolute;
      top: -18px;
      left: 14px;
      width: 37px;
      height: 20px;
      background: #181818;
      border-radius: 3px;
    }

    .product-bottle::after {
      content: "WAXOYL";
      position: absolute;
      top: 64px;
      left: 4px;
      right: 4px;
      padding: 7px 0;
      border-top: 2px solid var(--red);
      border-bottom: 2px solid var(--red);
      font-size: 7px;
      font-weight: 900;
    }

    .product strong { font-size: 13px; }

    .product small {
      margin-top: 6px;
      color: #888;
      font-size: 10px;
      line-height: 1.4;
    }

    /* =========================
       STATS
       ========================= */

    .stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      margin-top: 45px;
    }

    .stat {
      padding: 30px;
      border-right: 1px solid #333;
    }

    .stat:last-child { border-right: 0; }

    .stat b {
      display: block;
      font-size: 48px;
      letter-spacing: -2px;
    }

    .stat span {
      display: block;
      font-size: 10px;
      font-weight: 900;
      margin-top: 5px;
    }

    .stat small {
      display: block;
      color: #777;
      font-size: 10px;
      margin-top: 5px;
    }

    /* =========================
       MAP
       ========================= */

    .map {
      min-height: 420px;
      position: relative;
      overflow: hidden;
      border: 1px solid var(--line);
      background:
        radial-gradient(circle, #292929 1px, transparent 1px);
      background-size: 24px 24px;
    }

    .map::before {
      content: "POLSKA";
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      font-size: 78px;
      font-weight: 950;
      color: #171717;
    }

    .pin {
      position: absolute;
      width: 13px;
      height: 13px;
      background: var(--red);
      border-radius: 50%;
      box-shadow: 0 0 0 7px rgba(227,6,19,.13);
    }

    .p1 { left: 38%; top: 30%; }
    .p2 { left: 51%; top: 48%; }
    .p3 { left: 61%; top: 37%; }
    .p4 { left: 45%; top: 66%; }
    .p5 { left: 68%; top: 58%; }

    /* =========================
       PARTNER
       ========================= */

    .partner {
      padding: 55px;
      border: 1px solid var(--line);
      background: linear-gradient(100deg, #161616, #080808);
    }

    .partner h2 { max-width: 700px; }

    /* =========================
       CONTACT
       ========================= */

    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 25px;
    }

    .contact-card {
      background: #111;
      border: 1px solid var(--line);
      padding: 32px;
    }

    .contact-card h3 {
      margin: 0 0 18px;
      font-size: 18px;
    }

    .contact-card p {
      color: #999;
      font-size: 12px;
      line-height: 1.8;
    }

    .field {
      display: block;
      width: 100%;
      margin-bottom: 10px;
      padding: 13px;
      background: #080808;
      color: #fff;
      border: 1px solid #333;
      outline: none;
      font-size: 11px;
    }

    .field:focus { border-color: var(--red); }

    /* =========================
       FOOTER
       ========================= */

    footer {
      padding: 50px 0 20px;
      border-top: 1px solid var(--line);
      background: #050505;
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 1.4fr 1fr 1fr 1.2fr;
      gap: 40px;
    }

    footer h4 {
      font-size: 10px;
      letter-spacing: 1px;
      margin: 0 0 16px;
    }

    footer p {
      color: #777;
      font-size: 10px;
      line-height: 1.8;
    }

    .footer-logo {
      width: 110px;
      height: 80px;
      object-fit: contain;
    }

    .copyright {
      border-top: 1px solid #222;
      margin-top: 30px;
      padding-top: 15px;
      display: flex;
      justify-content: space-between;
      color: #555;
      font-size: 9px;
    }

    /* =========================
       RESPONSIVE
       ========================= */

    @media (max-width: 1000px) {
      .header { padding: 0 20px; }
      .navigation { gap: 15px; }
      .navigation a { font-size: 10px; }

      .tiles,
      .products-grid {
        grid-template-columns: repeat(2, 1fr);
      }

      .split,
      .contact-grid {
        grid-template-columns: 1fr;
      }

      .footer-grid {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    @media (max-width: 650px) {
      .header { height: 75px; }

      .logo {
        width: 62px;
        height: 58px;
      }

      .navigation {
        overflow-x: auto;
        justify-content: flex-start;
        gap: 15px;
      }

      .navigation a {
        padding: 27px 0;
        font-size: 9px;
      }

      .navigation a:nth-child(n+5) { display: none; }

      .container { padding: 0 20px; }

      .hero-content { padding: 75px 0; }

      .tiles,
      .products-grid,
      .stats,
      .footer-grid {
        grid-template-columns: 1fr;
      }

      .tile {
        border-right: 0;
        border-bottom: 1px solid #333;
      }

      .stat {
        border-right: 0;
        border-bottom: 1px solid #333;
      }

      .section { padding: 55px 0; }

      .partner { padding: 30px 22px; }

      .copyright {
        flex-direction: column;
        gap: 8px;
      }
    }
  </style>
</head>

<body>

  <!-- =========================
       HEADER / NAVIGATION
       ========================= -->
  <header class="header">
    <a href="#home">
      <img class="logo" src="waxoyl_logo_web.jpg" alt="Waxoyl Professional Car Care">
    </a>

    <nav class="navigation">
      <a class="home active" href="#home">⌂</a>
      <a href="#about">O FIRMIE</a>
      <a href="#products">PRODUKTY</a>
      <a href="#cooperation">WSPÓŁPRACA</a>
      <a href="#points">AUTORYZOWANE PUNKTY</a>
      <a href="#corrosion">ANTYKOROZJA</a>
      <a href="#detailing">DETAILING</a>
      <a href="#contact">KONTAKT</a>
    </nav>
  </header>


  <!-- =========================
       HOME
       ========================= -->
  <main id="home">

    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <div class="eyebrow">
            Professional Car Care · Advanced Technology
          </div>

          <h1>
            PROFESJONALNA<br>
            <span>OCHRONA SAMOCHODU</span>
          </h1>

          <p>
            Kompleksowe systemy Waxoyl do ochrony, pielęgnacji
            i zabezpieczenia samochodów. Technologia stworzona
            dla profesjonalistów.
          </p>

          <div class="buttons">
            <a class="btn red" href="#corrosion">
              POZNAJ ROZWIĄZANIA →
            </a>

            <a class="btn" href="#points">
              ZNAJDŹ PUNKT →
            </a>
          </div>
        </div>
      </div>
    </section>


    <section class="tiles">

      <article class="tile">
        <div class="icon">◈</div>
        <h3>ANTYKOROZJA</h3>
        <p>
          Kompleksowa ochrona podwozia i profili zamkniętych.
        </p>
        <a href="#corrosion">DOWIEDZ SIĘ WIĘCEJ →</a>
      </article>

      <article class="tile">
        <div class="icon">◌</div>
        <h3>DETAILING</h3>
        <p>
          Pielęgnacja, renowacja i zabezpieczenie powierzchni.
        </p>
        <a href="#detailing">DOWIEDZ SIĘ WIĘCEJ →</a>
      </article>

      <article class="tile">
        <div class="icon">◇</div>
        <h3>OCHRONA NOWEGO AUTA</h3>
        <p>
          Program ochrony wartości samochodu od pierwszego dnia.
        </p>
        <a href="#about">DOWIEDZ SIĘ WIĘCEJ →</a>
      </article>

      <article class="tile">
        <div class="icon">♙</div>
        <h3>DLA PROFESJONALISTÓW</h3>
        <p>
          Produkty, szkolenia, certyfikacja i wsparcie.
        </p>
        <a href="#cooperation">DOWIEDZ SIĘ WIĘCEJ →</a>
      </article>

    </section>
  </main>


  <!-- =========================
       O FIRMIE
       ========================= -->
  <section id="about" class="section">

    <div class="container">

      <div class="split">

        <div>
          <div class="eyebrow">Waxoyl Professional Car Care</div>

          <h2>
            TECHNOLOGIA<br>
            ZE SZWAJCARSKIMI KORZENIAMI.
          </h2>

          <p class="lead">
            Waxoyl to marka rozwijająca profesjonalne rozwiązania
            do ochrony i pielęgnacji pojazdów. Od ochrony
            antykorozyjnej po produkty car care — celem jest
            zachowanie wartości pojazdu na dłużej.
          </p>

          <div class="feature-list">

            <div class="feature">
              <b>01</b>
              <div>
                <strong>PROFESJONALIZM</strong>
                <p>
                  Rozwiązania przeznaczone do profesjonalnego zastosowania.
                </p>
              </div>
            </div>

            <div class="feature">
              <b>02</b>
              <div>
                <strong>DOŚWIADCZENIE</strong>
                <p>
                  Ponad pięć dekad rozwoju technologii ochrony.
                </p>
              </div>
            </div>

            <div class="feature">
              <b>03</b>
              <div>
                <strong>GLOBALNA MARKA</strong>
                <p>
                  Waxoyl jest obecny na wielu rynkach na całym świecie.
                </p>
              </div>
            </div>

          </div>
        </div>

        <div class="visual">
          <img src="waxoyl_logo_web.jpg" alt="Waxoyl logo">
        </div>

      </div>

      <div class="stats">

        <div class="stat">
          <b>50+</b>
          <span>LAT DOŚWIADCZENIA</span>
          <small>w profesjonalnej ochronie</small>
        </div>

        <div class="stat">
          <b>25+</b>
          <span>KRAJÓW</span>
          <small>globalnej obecności marki</small>
        </div>

        <div class="stat">
          <b>200+</b>
          <span>PUNKTÓW</span>
          <small>sieci partnerskiej w Polsce</small>
        </div>

      </div>

    </div>

  </section>


  <!-- =========================
       PRODUKTY
       ========================= -->
  <section id="products" class="section dark">

    <div class="container">

      <div class="eyebrow">Profesjonalne rozwiązania</div>

      <h2>PRODUKTY WAXOYL</h2>

      <p class="lead">
        Wybrane produkty z gamy profesjonalnych środków ochrony
        i pielęgnacji samochodów.
      </p>

      <div class="products-grid">

        <article class="product">
          <div class="product-bottle"></div>
          <strong>100 PLUS</strong>
          <small>
            Ochrona antykorozyjna i zabezpieczenie profili.
          </small>
        </article>

        <article class="product">
          <div class="product-bottle"></div>
          <strong>TBL</strong>
          <small>
            Trwała ochrona podwozia.
          </small>
        </article>

        <article class="product">
          <div class="product-bottle"></div>
          <strong>UB PROTECTION</strong>
          <small>
            Profesjonalne zabezpieczenie podwozia.
          </small>
        </article>

        <article class="product">
          <div class="product-bottle"></div>
          <strong>HARDWAX PLUS</strong>
          <small>
            Ochrona powierzchni na bazie wosku.
          </small>
        </article>

      </div>

    </div>

  </section>


  <!-- =========================
       ANTYKOROZJA
       ========================= -->
  <section id="corrosion" class="section">

    <div class="container">

      <div class="split">

        <div>
          <div class="eyebrow">Ochrona samochodu</div>

          <h2>
            ANTYKOROZJA,<br>
            KTÓRA MA ZNACZENIE.
          </h2>

          <p class="lead">
            System Waxoyl obejmuje zabezpieczenie podwozia,
            nadkoli i profili zamkniętych. Celem jest ograniczenie
            działania wilgoci, soli i czynników powodujących korozję.
          </p>

          <div class="feature-list">

            <div class="feature">
              <b>01</b>
              <div>
                <strong>PODWOZIE</strong>
                <p>
                  Warstwa ochronna dla najbardziej narażonych elementów.
                </p>
              </div>
            </div>

            <div class="feature">
              <b>02</b>
              <div>
                <strong>PROFILE ZAMKNIĘTE</strong>
                <p>
                  Ochrona trudno dostępnych przestrzeni wewnątrz konstrukcji.
                </p>
              </div>
            </div>

            <div class="feature">
              <b>03</b>
              <div>
                <strong>PROFESJONALNA APLIKACJA</strong>
                <p>
                  Proces wykonywany przez przeszkolonych specjalistów.
                </p>
              </div>
            </div>

          </div>
        </div>

        <div class="visual">
          <div style="font-size:100px;color:#e30613;">⚙</div>
        </div>

      </div>

    </div>

  </section>


  <!-- =========================
       DETAILING
       ========================= -->
  <section id="detailing" class="section dark">

    <div class="container">

      <div class="eyebrow">Car Care</div>

      <h2>
        DETAILING I OCHRONA<br>
        POWIERZCHNI.
      </h2>

      <p class="lead">
        Program pielęgnacji dla nowych i używanych samochodów —
        przygotowanie, renowacja, czyszczenie i ochrona.
      </p>

      <div class="tiles" style="margin-top:35px;">

        <article class="tile">
          <div class="icon">01</div>
          <h3>LAKIER</h3>
          <p>
            Przygotowanie i ochrona powierzchni lakierowanych.
          </p>
        </article>

        <article class="tile">
          <div class="icon">02</div>
          <h3>WNĘTRZE</h3>
          <p>
            Czyszczenie i ochrona materiałów wewnątrz pojazdu.
          </p>
        </article>

        <article class="tile">
          <div class="icon">03</div>
          <h3>RENOWACJA</h3>
          <p>
            Program dla samochodów używanych wymagających odświeżenia.
          </p>
        </article>

        <article class="tile">
          <div class="icon">04</div>
          <h3>PIELĘGNACJA</h3>
          <p>
            Rozwiązania do późniejszego utrzymania efektu.
          </p>
        </article>

      </div>

    </div>

  </section>


  <!-- =========================
       WSPÓŁPRACA
       ========================= -->
  <section id="cooperation" class="section">

    <div class="container">

      <div class="partner">

        <div class="eyebrow">Waxoyl Polska · B2B</div>

        <h2>
          ZOSTAŃ AUTORYZOWANYM
          PARTNEREM
        </h2>

        <p class="lead">
          Rozwijaj swój biznes z profesjonalną marką ochrony
          i pielęgnacji samochodów.
        </p>

        <div class="feature-list">

          <div class="feature">
            <b>✓</b>
            <div>
              <strong>SZKOLENIA</strong>
              <p>Wsparcie techniczne i wiedza produktowa.</p>
            </div>
          </div>

          <div class="feature">
            <b>✓</b>
            <div>
              <strong>MARKETING</strong>
              <p>Materiały i wsparcie w budowaniu oferty.</p>
            </div>
          </div>

          <div class="feature">
            <b>✓</b>
            <div>
              <strong>ROZPOZNAWALNA MARKA</strong>
              <p>Profesjonalny system współpracy.</p>
            </div>
          </div>

        </div>

        <div class="buttons">
          <a class="btn red" href="#contact">
            SKONTAKTUJ SIĘ →
          </a>
        </div>

      </div>

    </div>

  </section>


  <!-- =========================
       AUTORYZOWANE PUNKTY
       ========================= -->
  <section id="points" class="section dark">

    <div class="container">

      <div class="split">

        <div>

          <div class="eyebrow">Sieć Waxoyl Polska</div>

          <h2>
            ZNAJDŹ<br>
            AUTORYZOWANY PUNKT.
          </h2>

          <p class="lead">
            Wybierz profesjonalny punkt Waxoyl i zapytaj
            o dostępne usługi ochrony i pielęgnacji samochodu.
          </p>

          <div class="buttons">
            <button class="btn red">
              POBIERZ LISTĘ PUNKTÓW →
            </button>
          </div>

        </div>

        <div class="map">
          <i class="pin p1"></i>
          <i class="pin p2"></i>
          <i class="pin p3"></i>
          <i class="pin p4"></i>
          <i class="pin p5"></i>
        </div>

      </div>

    </div>

  </section>


  <!-- =========================
       KONTAKT
       ========================= -->
  <section id="contact" class="section">

    <div class="container">

      <div class="contact-grid">

        <div class="contact-card">

          <div class="eyebrow">Kontakt</div>

          <h2>POROZMAWIAJMY.</h2>

          <p>
            Masz pytanie dotyczące produktów, współpracy
            lub autoryzowanych punktów? Skontaktuj się z nami.
          </p>

          <p>
            <strong>Vehicle Care System Sp. z o.o.</strong><br>
            Polska<br><br>
            tel. +48 58 550 05 50<br>
            biuro@waxoyl.pl
          </p>

        </div>

        <div class="contact-card">

          <h3>FORMULARZ KONTAKTOWY</h3>

          <form>
            <input class="field" type="text" placeholder="Imię i nazwisko">
            <input class="field" type="email" placeholder="E-mail">
            <input class="field" type="tel" placeholder="Telefon">
            <textarea class="field" rows="6" placeholder="Wiadomość"></textarea>

            <button class="btn red" type="submit">
              WYŚLIJ WIADOMOŚĆ →
            </button>
          </form>

        </div>

      </div>

    </div>

  </section>


  <!-- =========================
       FOOTER
       ========================= -->
  <footer>

    <div class="container">

      <div class="footer-grid">

        <div>
          <img
            class="footer-logo"
            src="waxoyl_logo_web.jpg"
            alt="Waxoyl Professional Car Care"
          >

          <p>
            Professional Car Care.<br>
            Advanced Technology.
          </p>
        </div>

        <div>
          <h4>NAWIGACJA</h4>
          <p>
            O firmie<br>
            Produkty<br>
            Współpraca<br>
            Autoryzowane punkty
          </p>
        </div>

        <div>
          <h4>ROZWIĄZANIA</h4>
          <p>
            Antykorozja<br>
            Detailing<br>
            Ochrona nowego auta
          </p>
        </div>

        <div>
          <h4>KONTAKT</h4>
          <p>
            +48 58 550 05 50<br>
            biuro@waxoyl.pl<br>
            Polska
          </p>
        </div>

      </div>

      <div class="copyright">
        <span>© 2026 Waxoyl Polska</span>
        <span>Polityka prywatności · Polityka cookies</span>
      </div>

    </div>

  </footer>

</body>
</html>
