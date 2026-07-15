<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Certificate of Completion - Md. Tahmidul Alam Ahad</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=EB+Garamond:ital,wght@0,400;0,600;0,700;1,400&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background: #8c8c8c;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 30px;
    }

    /* ═══════════════════════════════════════
       CERTIFICATE OUTER SHELL
    ═══════════════════════════════════════ */
    .cert {
      width: 1060px;
      height: 750px;
      position: relative;
      /* Cream parchment background */
      background-color: #f1edde;
      box-shadow: 0 20px 70px rgba(32, 31, 31, 0.5);
      overflow: hidden;
    }

    /* ─── Border Layers ─── */

    /* 1. Thick navy outer border */
    .b-navy {
      position: absolute;
      inset: 0;
      border: 16px solid #12235e;
      z-index: 20;
      pointer-events: none;
    }

    /* 2. Thin gold line just inside navy */
    .b-g1 {
      position: absolute;
      inset: 19px;
      border: 1.5px solid #c8a22a;
      z-index: 20;
      pointer-events: none;
    }

    /* 3. Second thin gold line */
    .b-g2 {
      position: absolute;
      inset: 26px;
      border: 1px solid #c8a22a;
      z-index: 20;
      pointer-events: none;
    }

    /* ─── Corner Ornaments ─── */
    .corn {
      position: absolute;
      width: 52px;
      height: 52px;
      z-index: 25;
      pointer-events: none;
    }
    /* TL: inner gold-border corner at cert(26,26) = svg(11,11) since svg starts at cert(15,15) */
    .corn-tl { top: 15px; left: 15px; }
    /* TR: inner gold-border corner at cert(1034,26), svg starts at cert(1060-15-52,15)=(993,15), so svg=(1034-993,11)=(41,11) */
    .corn-tr { top: 15px; right: 15px; }
    /* BL: inner gold-border corner at cert(26,724), svg starts at cert(15,750-15-52)=(15,683), so svg=(11,724-683)=(11,41) */
    .corn-bl { bottom: 15px; left: 15px; }
    /* BR: inner gold-border corner at cert(1034,724), svg=(41,41) */
    .corn-br { bottom: 15px; right: 15px; }

    /* ─── Main Content ─── */
    .cert-body-wrap {
      position: absolute;
      top: 32px; left: 32px; right: 32px; bottom: 32px;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 14px 85px 28px;
      z-index: 10;
    }

    /* Logo */
    .logo-img {
      width: 118px;
      height: 118px;
      object-fit: contain;
      margin-bottom: 13px;
    }

    /* "Certificate of Completion" */
    .cert-title {
      font-family: 'Playfair Display', Georgia, 'Times New Roman', serif;
      font-size: 51px;
      font-weight: 400;
      color: #12235e;
      text-align: center;
      letter-spacing: 0.5px;
      line-height: 1.15;
      margin-bottom: 6px;
    }

    /* italic subtitle */
    .cert-sub {
      font-family: 'EB Garamond', Georgia, serif;
      font-size: 19px;
      font-style: italic;
      color: #6a6a72;
      margin-bottom: 10px;
      letter-spacing: 0.2px;
    }

    /* Recipient name */
    .cert-name {
      font-family: 'EB Garamond', Georgia, serif;
      font-size: 47px;
      font-weight: 600;
      color: #12235e;
      text-align: center;
      letter-spacing: 0.5px;
      line-height: 1.2;
      margin-bottom: 11px;
    }

    /* Gold rule below name */
    .name-rule {
      width: 620px;
      height: 1.5px;
      background: linear-gradient(to right, transparent, #c8a22a 14%, #c8a22a 86%, transparent);
      margin-bottom: 15px;
    }

    /* Body paragraph */
    .cert-para {
      font-family: 'EB Garamond', Georgia, serif;
      font-size: 16.5px;
      line-height: 1.88;
      color: #2b2b2b;
      text-align: center;
      max-width: 830px;
    }
    .cert-para strong { font-weight: 700; }
    .cert-para em { font-style: italic; }

    /* Issued date line */
    .issued-on {
      font-family: 'EB Garamond', Georgia, serif;
      font-size: 16px;
      color: #2b2b2b;
      text-align: center;
      margin-top: 16px;
      font-weight: 700;
    }

    /* ─── Signature Section ─── */
    .cert-sigs {
      width: 100%;
      margin-top: auto;
      display: flex;
      justify-content: space-between;
      padding-top: 8px;
    }

    .sig-block {
      width: 220px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .sig-line {
      width: 100%;
      height: 1px;
      background: #9a9a9a;
      margin-bottom: 7px;
    }

    .sig-name {
      font-family: 'EB Garamond', Georgia, serif;
      font-size: 20px;
      font-weight: 700;
      color: #12235e;
      letter-spacing: 0.2px;
    }

    .sig-role {
      font-family: 'EB Garamond', Georgia, serif;
      font-size: 16px;
      font-weight: 500;
      color: #3b4256;
      letter-spacing: 0.2px;
      margin-top: 2px;
    }

    .sig-co {
      font-family: 'EB Garamond', Georgia, serif;
      font-size: 13.5px;
      color: #555555;
      margin-top: 2px;
      white-space: nowrap;
    }

    @page {
      size: A4 landscape;
      margin: 0;
    }

    @media print {
      body {
        margin: 0;
        padding: 0;
        background: transparent;
        display: flex;
        justify-content: center;
        align-items: center;
        -webkit-print-color-adjust: exact;
        print-color-adjust: exact;
      }
      .cert {
        box-shadow: none;
        page-break-after: avoid;
        page-break-before: avoid;
      }
    }
  </style>
</head>
<body>

<div class="cert">

  <!-- ══ Hex Watermark Background ══ -->
  <svg style="position:absolute;inset:0;width:100%;height:100%;z-index:1;" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <!--
        Flat-top hexagonal tile: circumradius r=13, tile 39×22.52
        3 polygons needed for seamless tiling:
          A: center(13, 11.26)
          B: center(32.5, 0)   — top-half clipped
          C: center(32.5, 22.52) — bottom-half clipped
      -->
      <pattern id="hexBg" x="0" y="0" width="39" height="22.52" patternUnits="userSpaceOnUse">
        <!-- Polygon A – full hex, center (13, 11.26) -->
        <polygon points="26,11.26 19.5,0 6.5,0 0,11.26 6.5,22.52 19.5,22.52"
                 fill="none" stroke="#12235e" stroke-width="0.7" stroke-opacity="0.08"/>
        <!-- Polygon B – partial hex, center (32.5, 0) -->
        <polygon points="45.5,0 39,11.26 26,11.26 19.5,0 26,-11.26 39,-11.26"
                 fill="none" stroke="#12235e" stroke-width="0.7" stroke-opacity="0.08"/>
        <!-- Polygon C – partial hex, center (32.5, 22.52) -->
        <polygon points="45.5,22.52 39,33.78 26,33.78 19.5,22.52 26,11.26 39,11.26"
                 fill="none" stroke="#12235e" stroke-width="0.7" stroke-opacity="0.08"/>
      </pattern>
    </defs>
    <rect width="1060" height="750" fill="url(#hexBg)"/>
  </svg>

  <!-- ══ Border Layers ══ -->
  <div class="b-navy"></div>
  <div class="b-g1"></div>
  <div class="b-g2"></div>

  <!-- ══ Corner Ornaments ══ -->
  <!-- TOP-LEFT: inner-gold corner at svg(11,11) -->
  <svg class="corn corn-tl" viewBox="0 0 52 52" xmlns="http://www.w3.org/2000/svg">
    <line x1="11" y1="11" x2="52" y2="11" stroke="#c8a22a" stroke-width="1.5"/>
    <line x1="11" y1="11" x2="11" y2="52" stroke="#c8a22a" stroke-width="1.5"/>
    <path d="M11,3 L19,11 L11,19 L3,11 Z" fill="#c8a22a"/>
    <rect x="26" y="8" width="6" height="6" fill="#c8a22a"/>
    <rect x="8" y="26" width="6" height="6" fill="#c8a22a"/>
  </svg>

  <!-- TOP-RIGHT: inner-gold corner at svg(41,11) -->
  <svg class="corn corn-tr" viewBox="0 0 52 52" xmlns="http://www.w3.org/2000/svg">
    <line x1="41" y1="11" x2="0" y2="11" stroke="#c8a22a" stroke-width="1.5"/>
    <line x1="41" y1="11" x2="41" y2="52" stroke="#c8a22a" stroke-width="1.5"/>
    <path d="M41,3 L49,11 L41,19 L33,11 Z" fill="#c8a22a"/>
    <rect x="20" y="8" width="6" height="6" fill="#c8a22a"/>
    <rect x="38" y="26" width="6" height="6" fill="#c8a22a"/>
  </svg>

  <!-- BOTTOM-LEFT: inner-gold corner at svg(11,41) -->
  <svg class="corn corn-bl" viewBox="0 0 52 52" xmlns="http://www.w3.org/2000/svg">
    <line x1="11" y1="41" x2="52" y2="41" stroke="#c8a22a" stroke-width="1.5"/>
    <line x1="11" y1="41" x2="11" y2="0" stroke="#c8a22a" stroke-width="1.5"/>
    <path d="M11,33 L19,41 L11,49 L3,41 Z" fill="#c8a22a"/>
    <rect x="26" y="38" width="6" height="6" fill="#c8a22a"/>
    <rect x="8" y="20" width="6" height="6" fill="#c8a22a"/>
  </svg>

  <!-- BOTTOM-RIGHT: inner-gold corner at svg(41,41) -->
  <svg class="corn corn-br" viewBox="0 0 52 52" xmlns="http://www.w3.org/2000/svg">
    <line x1="41" y1="41" x2="0" y2="41" stroke="#c8a22a" stroke-width="1.5"/>
    <line x1="41" y1="41" x2="41" y2="0" stroke="#c8a22a" stroke-width="1.5"/>
    <path d="M41,33 L49,41 L41,49 L33,41 Z" fill="#c8a22a"/>
    <rect x="20" y="38" width="6" height="6" fill="#c8a22a"/>
    <rect x="38" y="20" width="6" height="6" fill="#c8a22a"/>
  </svg>

  <!-- ══ Main Certificate Content ══ -->
  <div class="cert-body-wrap">

    <!-- Logo -->
    <img class="logo-img" src="modhuban_logo.png" alt="Modhuban Sweets & Cafe Logo">

    <!-- Title -->
    <div class="cert-title">Certificate of Completion</div>

    <!-- Italic subtitle -->
    <div class="cert-sub">This certificate is proudly presented to</div>

    <!-- Recipient name -->
    <div class="cert-name">Md. Tahmidul Alam Ahad</div>

    <!-- Gold rule -->
    <div class="name-rule"></div>

    <!-- Body paragraph — exact text from the original image including original typos/formatting -->
    <p class="cert-para">
      for successfully completing the <strong>Six-Month Management Trainee Officer (MTO) Internship</strong> in the <br>Production and IT/MIS Departments at MODHUBAN BREAD &amp; BISCUITS IND. (PVT.) LTD.,<br>
      from 01 January 2026 to 01 July 2026. During this period, he demonstrated dedication, professionalism,<br>
      excellent analytical skills, and a commendable work ethic. His contributions were highly valued and appreciated.
    </p>

    <div class="issued-on"><strong>Issued on: July 01, 2026</strong></div>

    <!-- ══ Signature Section — inside flex so margin-top:auto closes the gap ══ -->
    <div class="cert-sigs">
      <div class="sig-block">
        <div class="sig-line"></div>
        <div class="sig-name">M Abu Taher</div>
        <div class="sig-role">Manager</div>
        <div class="sig-co">MODHUBAN BREAD &amp; BISCUITS IND. (PVT.) LTD.</div>
      </div>
      <div class="sig-block">
        <div class="sig-line"></div>
        <div class="sig-name">Md. Nurul Amin</div>
        <div class="sig-role">Managing Director</div>
        <div class="sig-co">MODHUBAN BREAD &amp; BISCUITS IND. (PVT.) LTD.</div>
      </div>
    </div>

  </div>

</div>

</body>
</html>
