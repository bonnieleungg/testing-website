<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <title>YouFind AIPO | GEO 服務</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      --primary: #ff6b35;
      --primary-dark: #e15422;
      --bg: #050816;
      --bg-alt: #0b1020;
      --text-main: #f5f5f7;
      --text-muted: #a0a3b1;
      --border-subtle: #262a3b;
      --accent: #4f46e5;
      --card-bg: #111827;
      --radius-lg: 18px;
      --radius-md: 12px;
      --radius-pill: 999px;
      --shadow-soft: 0 18px 45px rgba(0,0,0,0.45);
      --shadow-subtle: 0 10px 30px rgba(0,0,0,0.35);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text", system-ui, sans-serif;
      background: radial-gradient(circle at top left, #1a1f3c 0, #050816 45%, #000 100%);
      color: var(--text-main);
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(18px);
      background: linear-gradient(to bottom, rgba(5,8,22,0.92), rgba(5,8,22,0.75));
      border-bottom: 1px solid rgba(255,255,255,0.04);
    }

    .nav {
      max-width: 1120px;
      margin: 0 auto;
      padding: 14px 20px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .logo-mark {
      width: 32px;
      height: 32px;
      border-radius: 12px;
      background: radial-gradient(circle at 30% 0, #ffcf71, #ff6b35 45%, #7c3aed 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 700;
      font-size: 18px;
      box-shadow: 0 8px 26px rgba(0,0,0,0.55);
    }

    .logo-text {
      font-weight: 600;
      font-size: 18px;
      letter-spacing: 0.05em;
    }

    .logo-sub {
      font-size: 11px;
      color: var(--text-muted);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 20px;
      font-size: 14px;
    }

    .nav-links a {
      color: var(--text-muted);
      padding: 4px 0;
    }

    .nav-links a:hover {
      color: #ffffff;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 8px 18px;
      border-radius: var(--radius-pill);
      border: 1px solid transparent;
      font-size: 14px;
      cursor: pointer;
      transition: all 0.18s ease-out;
      white-space: nowrap;
      gap: 6px;
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--primary), var(--primary-dark));
      color: #fff;
      box-shadow: var(--shadow-subtle);
    }

    .btn-primary:hover {
      transform: translateY(-1px);
      box-shadow: 0 16px 40px rgba(225,84,34,0.45);
    }

    .btn-ghost {
      border-color: rgba(255,255,255,0.10);
      color: #ffffff;
      background: rgba(15,23,42,0.6);
    }

    .btn-ghost:hover {
      background: rgba(15,23,42,0.9);
      border-color: rgba(255,255,255,0.18);
    }

    main {
      max-width: 1120px;
      margin: 0 auto;
      padding: 26px 20px 72px;
    }

    section {
      padding: 48px 0;
      border-bottom: 1px solid rgba(255,255,255,0.03);
    }

    .section-title {
      font-size: 26px;
      margin-bottom: 10px;
    }

    .section-kicker {
      font-size: 13px;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--primary);
      margin-bottom: 8px;
    }

    .section-lead {
      color: var(--text-muted);
      max-width: 640px;
      font-size: 15px;
    }

    /* Hero */
    .hero {
      display: grid;
      grid-template-columns: minmax(0, 1.4fr) minmax(0, 1.2fr);
      gap: 36px;
      align-items: center;
      padding-top: 26px;
      padding-bottom: 40px;
    }

    .hero-title {
      font-size: 34px;
      line-height: 1.18;
      margin-bottom: 14px;
    }

    .hero-subtitle {
      font-size: 18px;
      color: var(--primary);
      margin-bottom: 10px;
      font-weight: 500;
    }

    .hero-bullets {
      margin: 18px 0 22px;
      list-style: none;
      color: var(--text-muted);
      font-size: 14px;
    }

    .hero-bullets li {
      margin-bottom: 6px;
    }

    .hero-cta-row {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      align-items: center;
      margin-top: 4px;
    }

    .hero-note {
      font-size: 12px;
      color: var(--text-muted);
    }

    .hero-metrics {
      display: flex;
      gap: 18px;
      margin-top: 22px;
      font-size: 11px;
      color: var(--text-muted);
    }

    .hero-metrics strong {
      font-size: 16px;
      color: #fff;
      display: block;
    }

    .hero-right {
      position: relative;
    }

    .hero-card {
      background: radial-gradient(circle at top, rgba(148,163,255,0.35), rgba(15,23,42,0.98) 40%);
      border-radius: 26px;
      padding: 18px 18px 16px;
      box-shadow: var(--shadow-soft);
      border: 1px solid rgba(255,255,255,0.05);
    }

    .badge-pill {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-size: 11px;
      padding: 5px 10px;
      border-radius: 999px;
      background: rgba(15,23,42,0.8);
      border: 1px solid rgba(148,163,255,0.45);
      color: #e5e7ff;
      margin-bottom: 10px;
    }

    .hero-report-layout {
      background: rgba(15,23,42,0.96);
      border-radius: 20px;
      padding: 14px;
      border: 1px solid rgba(148,163,255,0.35);
      position: relative;
      overflow: hidden;
      font-size: 11px;
    }

    .hero-report-header {
      display: flex;
      justify-content: space-between;
      margin-bottom: 10px;
      align-items: center;
    }

    .tag {
      font-size: 10px;
      padding: 3px 8px;
      border-radius: 999px;
      background: rgba(15,118,110,0.16);
      color: #a5f3fc;
    }

    .hero-mock-chart {
      height: 96px;
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 8px;
      align-items: end;
    }

    .hero-mock-bar {
      border-radius: 8px 8px 0 0;
      background: linear-gradient(to top, rgba(248,113,113,0.15), rgba(248,113,113,0.9));
      position: relative;
      overflow: hidden;
    }

    .hero-mock-bar:nth-child(2) {
      height: 60%;
      background: linear-gradient(to top, rgba(96,165,250,0.15), rgba(96,165,250,0.9));
    }

    .hero-mock-bar:nth-child(3) {
      height: 90%;
      background: linear-gradient(to top, rgba(34,197,94,0.15), rgba(34,197,94,1));
    }

    .hero-mock-bar:nth-child(4) {
      height: 45%;
    }

    .hero-mock-bar span {
      position: absolute;
      bottom: 6px;
      left: 50%;
      transform: translateX(-50%);
      font-size: 9px;
      color: #0b1120;
      font-weight: 600;
    }

    .hero-report-footer {
      margin-top: 10px;
      display: flex;
      justify-content: space-between;
      font-size: 10px;
      color: var(--text-muted);
    }

    .pill-mini {
      font-size: 10px;
      padding: 3px 7px;
      border-radius: 999px;
      background: rgba(55,65,81,0.75);
      color: #e5e7eb;
    }

    .hero-floating {
      position: absolute;
      right: -10px;
      bottom: -12px;
      width: 160px;
      padding: 10px;
      border-radius: 16px;
      background: rgba(15,23,42,0.98);
      border: 1px solid rgba(148,163,255,0.4);
      box-shadow: 0 16px 40px rgba(0,0,0,0.8);
      font-size: 11px;
    }

    .hero-floating-title {
      font-size: 11px;
      margin-bottom: 4px;
    }

    .hero-floating-metric {
      font-size: 10px;
      color: var(--text-muted);
    }

    /* Intro GEO */
    .two-col {
      display: grid;
      grid-template-columns: minmax(0, 1.3fr) minmax(0, 1.1fr);
      gap: 24px;
      align-items: flex-start;
    }

    .muted-card {
      background: linear-gradient(135deg, rgba(15,23,42,0.9), rgba(15,23,42,0.98));
      border-radius: var(--radius-lg);
      padding: 18px 18px 14px;
      border: 1px solid var(--border-subtle);
      box-shadow: var(--shadow-subtle);
      font-size: 13px;
      color: var(--text-muted);
    }

    .muted-card h4 {
      font-size: 14px;
      margin-bottom: 8px;
      color: #e5e7eb;
    }

    /* Customer journey */
    .journey-card {
      background: radial-gradient(circle at top left, rgba(56,189,248,0.18), rgba(15,23,42,0.98));
      border-radius: var(--radius-lg);
      padding: 16px;
      border: 1px solid rgba(56,189,248,0.4);
      font-size: 13px;
      color: var(--text-muted);
      box-shadow: var(--shadow-subtle);
    }

    .journey-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 16px;
      margin-top: 10px;
    }

    .journey-col h4 {
      font-size: 13px;
      margin-bottom: 6px;
      color: #e5e7eb;
    }

    .journey-badge {
      font-size: 10px;
      padding: 3px 7px;
      border-radius: 999px;
      background: rgba(15,23,42,0.9);
      border: 1px solid rgba(56,189,248,0.5);
      color: #bae6fd;
      display: inline-block;
      margin-bottom: 6px;
    }

    /* Problem section */
    .alert-card {
      background: radial-gradient(circle at top left, rgba(248,113,113,0.22), rgba(15,23,42,0.98));
      border-radius: var(--radius-lg);
      padding: 18px;
      border: 1px solid rgba(248,113,113,0.45);
      font-size: 13px;
      color: var(--text-muted);
      box-shadow: var(--shadow-subtle);
    }

    .alert-title {
      font-size: 15px;
      margin-bottom: 8px;
      color: #fecaca;
    }

    .alert-list {
      margin: 8px 0 0;
      padding-left: 16px;
    }

    .alert-list li {
      margin-bottom: 4px;
    }

    /* Services strip image placeholder */
    .wide-image-card {
      border-radius: var(--radius-lg);
      padding: 14px;
      background: linear-gradient(120deg, rgba(15,23,42,0.9), rgba(15,23,42,0.98));
      border: 1px dashed rgba(148,163,255,0.45);
      text-align: center;
      font-size: 12px;
      color: var(--text-muted);
    }

    /* Success logos strip */
    .logos-strip {
      background: linear-gradient(90deg, rgba(15,23,42,0.9), rgba(30,64,175,0.7));
      border-radius: var(--radius-lg);
      padding: 14px 16px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
      border: 1px solid rgba(59,130,246,0.45);
      box-shadow: var(--shadow-subtle);
      font-size: 13px;
    }

    .logos-buttons {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
    }

    .chip {
      padding: 7px 14px;
      border-radius: var(--radius-pill);
      background: rgba(15,23,42,0.9);
      border: 1px solid rgba(191,219,254,0.6);
      font-size: 12px;
      cursor: pointer;
    }

    /* Table SEO vs GEO */
    .table-wrap {
      margin-top: 18px;
      border-radius: var(--radius-lg);
      overflow: hidden;
      border: 1px solid var(--border-subtle);
      background: rgba(15,23,42,0.9);
      box-shadow: var(--shadow-subtle);
      font-size: 13px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
    }

    thead {
      background: radial-gradient(circle at top left, rgba(96,165,250,0.26), rgba(15,23,42,0.95));
    }

    th, td {
      padding: 10px 12px;
      text-align: left;
    }

    tbody tr:nth-child(even) {
      background: rgba(15,23,42,0.9);
    }

    tbody tr:nth-child(odd) {
      background: rgba(15,23,42,0.96);
    }

    th {
      font-weight: 500;
    }

    /* Zero moment */
    .zmot-card {
      background: linear-gradient(145deg, rgba(79,70,229,0.22), rgba(15,23,42,0.98));
      border-radius: var(--radius-lg);
      padding: 18px;
      border: 1px solid rgba(79,70,229,0.5);
      font-size: 13px;
      color: var(--text-muted);
      box-shadow: var(--shadow-subtle);
    }

    .pill-row {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 10px;
      font-size: 11px;
    }

    .pill-row span {
      padding: 4px 9px;
      border-radius: 999px;
      border: 1px solid rgba(129,140,248,0.6);
      background: rgba(15,23,42,0.9);
      color: #e0e7ff;
    }

    /* How AI engines work */
    .cards-grid-3 {
      display: grid;
      grid-template-columns: repeat(3, minmax(0,1fr));
      gap: 16px;
      margin-top: 16px;
    }

    .small-card {
      background: rgba(15,23,42,0.96);
      border-radius: var(--radius-md);
      border: 1px solid var(--border-subtle);
      padding: 12px;
      font-size: 12px;
      color: var(--text-muted);
    }

    .small-card h4 {
      font-size: 13px;
      margin-bottom: 6px;
      color: #e5e7eb;
    }

    .link-list {
      margin-top: 6px;
      font-size: 11px;
    }

    .link-list a {
      display: block;
      margin-bottom: 3px;
      color: #bfdbfe;
    }

    /* 1+1+1 combo */
    .combo-card {
      background: radial-gradient(circle at top left, rgba(251,191,36,0.2), rgba(15,23,42,0.98));
      border-radius: var(--radius-lg);
      padding: 18px;
      border: 1px solid rgba(251,191,36,0.55);
      font-size: 13px;
      color: var(--text-muted);
      box-shadow: var(--shadow-subtle);
    }

    .combo-grid {
      display: grid;
      grid-template-columns: repeat(3,minmax(0,1fr));
      gap: 16px;
      margin-top: 12px;
    }

    .combo-item {
      background: rgba(15,23,42,0.96);
      border-radius: var(--radius-md);
      padding: 10px;
      border: 1px solid rgba(251,191,36,0.35);
      font-size: 12px;
    }

    .combo-tag {
      font-size: 11px;
      padding: 3px 7px;
      border-radius: 999px;
      background: rgba(161,98,7,0.3);
      color: #facc15;
      display: inline-block;
      margin-bottom: 4px;
    }

    /* Why YouFind */
    .why-grid {
      display: grid;
      grid-template-columns: repeat(3,minmax(0,1fr));
      gap: 16px;
      margin-top: 14px;
    }

    .why-item {
      background: rgba(15,23,42,0.96);
      border-radius: var(--radius-md);
      padding: 12px;
      border: 1px solid var(--border-subtle);
      font-size: 12px;
      color: var(--text-muted);
    }

    .why-item h4 {
      font-size: 13px;
      margin-bottom: 6px;
      color: #e5e7eb;
    }

    /* Free GEO audit */
    .audit-card {
      background: radial-gradient(circle at top left, rgba(74,222,128,0.22), rgba(15,23,42,0.98));
      border-radius: var(--radius-lg);
      padding: 18px;
      border: 1px solid rgba(74,222,128,0.55);
      display: grid;
      grid-template-columns: minmax(0,1.4fr) minmax(0,1.1fr);
      gap: 18px;
      align-items: center;
      box-shadow: var(--shadow-subtle);
      font-size: 13px;
      color: var(--text-muted);
    }

    .bullet-list {
      margin-top: 8px;
      padding-left: 16px;
    }

    .bullet-list li {
      margin-bottom: 4px;
    }

    /* Ongoing consulting */
    .strip-card {
      background: linear-gradient(90deg, rgba(15,23,42,0.96), rgba(79,70,229,0.9));
      border-radius: var(--radius-lg);
      padding: 16px;
      border: 1px solid rgba(129,140,248,0.6);
      color: var(--text-main);
      font-size: 13px;
      box-shadow: var(--shadow-subtle);
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 18px;
      flex-wrap: wrap;
    }

    .strip-card ul {
      padding-left: 16px;
      margin-top: 6px;
      color: #e5e7ff;
      font-size: 12px;
    }

    /* Case studies */
    .case-grid {
      display: grid;
      grid-template-columns: minmax(0,1.2fr) minmax(0,1fr);
      gap: 18px;
      align-items: flex-start;
    }

    .case-card {
      background: rgba(15,23,42,0.96);
      border-radius: var(--radius-lg);
      border: 1px solid var(--border-subtle);
      padding: 14px 16px;
      font-size: 13px;
      color: var(--text-muted);
    }

    .case-header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      margin-bottom: 6px;
    }

    .case-header h4 {
      font-size: 14px;
      color: #e5e7eb;
    }

    .case-tag {
      font-size: 11px;
      padding: 2px 8px;
      border-radius: 999px;
      background: rgba(15,23,42,0.9);
      border: 1px solid rgba(148,163,255,0.55);
      color: #c7d2fe;
    }

    .case-subtitle {
      font-size: 12px;
      color: var(--text-muted);
      margin-bottom: 6px;
    }

    .case-star-list {
      margin-top: 6px;
      padding-left: 16px;
      font-size: 12px;
    }

    .case-aside {
      display: grid;
      gap: 12px;
    }

    .case-metric-card {
      background: radial-gradient(circle at top left, rgba(52,211,153,0.18), rgba(15,23,42,1));
      border-radius: var(--radius-md);
      border: 1px solid rgba(52,211,153,0.55);
      padding: 10px;
      font-size: 12px;
      color: var(--text-muted);
    }

    /* Blog */
    .blog-grid {
      display: grid;
      grid-template-columns: repeat(3,minmax(0,1fr));
      gap: 16px;
      margin-top: 16px;
      font-size: 12px;
    }

    .blog-card {
      background: rgba(15,23,42,0.96);
      border-radius: var(--radius-md);
      border: 1px solid var(--border-subtle);
      padding: 12px;
      color: var(--text-muted);
    }

    .blog-card h4 {
      font-size: 13px;
      margin-bottom: 6px;
      color: #e5e7eb;
    }

    .blog-tag {
      font-size: 11px;
      padding: 2px 8px;
      border-radius: 999px;
      background: rgba(15,23,42,0.9);
      border: 1px solid rgba(59,130,246,0.55);
      color: #bfdbfe;
      display: inline-block;
      margin-bottom: 4px;
    }

    /* Pricing */
    .pricing-grid {
      display: grid;
      grid-template-columns: repeat(3,minmax(0,1fr));
      gap: 16px;
      margin-top: 16px;
    }

    .pricing-card {
      background: rgba(15,23,42,0.96);
      border-radius: var(--radius-lg);
      border: 1px solid var(--border-subtle);
      padding: 14px 16px 16px;
      font-size: 13px;
      color: var(--text-muted);
    }

    .pricing-card h4 {
      font-size: 15px;
      margin-bottom: 6px;
      color: #e5e7eb;
    }

    .pricing-price {
      font-size: 18px;
      color: #f9fafb;
      margin-bottom: 4px;
    }

    .pricing-features {
      margin-top: 8px;
      padding-left: 16px;
      font-size: 12px;
    }

    /* FAQ */
    .faq-grid {
      display: grid;
      grid-template-columns: repeat(2,minmax(0,1fr));
      gap: 14px;
      margin-top: 16px;
      font-size: 13px;
    }

    .faq-item {
      background: rgba(15,23,42,0.96);
      border-radius: var(--radius-md);
      border: 1px solid var(--border-subtle);
      padding: 10px 12px;
    }

    .faq-item h4 {
      font-size: 13px;
      margin-bottom: 4px;
      color: #e5e7eb;
    }

    /* Contact */
    .contact-grid {
      display: grid;
      grid-template-columns: minmax(0,1.2fr) minmax(0,1fr);
      gap: 18px;
      align-items: flex-start;
    }

    .contact-card {
      background: rgba(15,23,42,0.96);
      border-radius: var(--radius-lg);
      border: 1px solid var(--border-subtle);
      padding: 16px;
      font-size: 13px;
      color: var(--text-muted);
    }

    .contact-form {
      display: grid;
      gap: 10px;
      margin-top: 10px;
    }

    .field {
      display: grid;
      gap: 4px;
      font-size: 12px;
    }

    .field label {
      color: #e5e7eb;
    }

    .field input,
    .field textarea,
    .field select {
      background: rgba(15,23,42,0.96);
      border-radius: 10px;
      border: 1px solid rgba(55,65,81,1);
      padding: 7px 9px;
      color: #e5e7eb;
      font-family: inherit;
      font-size: 13px;
      outline: none;
    }

    .field textarea {
      resize: vertical;
      min-height: 80px;
    }

    footer {
      max-width: 1120px;
      margin: 0 auto;
      padding: 18px 20px 40px;
      font-size: 12px;
      color: var(--text-muted);
      display: flex;
      justify-content: space-between;
      border-top: 1px solid rgba(255,255,255,0.03);
    }

    footer a {
      color: var(--text-muted);
    }

    /* Responsive */
    @media (max-width: 960px) {
      .hero,
      .two-col,
      .cards-grid-3,
      .combo-grid,
      .why-grid,
      .audit-card,
      .case-grid,
      .blog-grid,
      .pricing-grid,
      .faq-grid,
      .contact-grid {
        grid-template-columns: minmax(0,1fr);
      }

      .hero {
        padding-top: 18px;
      }

      .hero-floating {
        position: static;
        margin-top: 10px;
        width: 100%;
      }

      .nav-links {
        display: none;
      }

      header {
        position: static;
      }

      main {
        padding-top: 16px;
      }
    }

    @media (max-width: 640px) {
      section {
        padding: 34px 0;
      }

      .hero-title {
        font-size: 26px;
      }

      .hero-subtitle {
        font-size: 16px;
      }

      .logos-strip {
        flex-direction: column;
        align-items: flex-start;
      }

      footer {
        flex-direction: column;
        gap: 10px;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="nav">
      <div class="logo">
        <div class="logo-mark">YF</div>
        <div>
          <div class="logo-text">YouFind AIPO</div>
          <div class="logo-sub">From SEO to GEO</div>
        </div>
      </div>
      <nav class="nav-links">
        <a href="#home">首頁</a>
        <a href="#services-main">主要服務</a>
        <a href="#cases">成功案例</a>
        <a href="#blog">部落格</a>
        <a href="#pricing">Pricing</a>
        <a href="#faq">常見問題</a>
        <a href="#contact">預約諮詢</a>
        <button class="btn btn-primary" onclick="document.querySelector('#geo-audit').scrollIntoView({behavior:'smooth'});">
          免費GEO報告
        </button>
      </nav>
    </div>
  </header>

  <main>
    <!-- Hero / Home -->
    <section id="home">
      <div class="hero">
        <div>
          <div class="section-kicker">首頁 · YouFind AIPO</div>
          <h1 class="hero-title">從 SEO 到 GEO：AI時代的新一代能見度戰場</h1>
          <div class="hero-subtitle">AI時代，流量之外的品牌決策點！</div>
          <p class="section-lead">
            近半數的 Google 搜索已顯示 AI 摘要，您的網站也許排名靠前，但在 AI 回答中卻完全沒有被提及。這代表當客戶向 AI 發問時，真正被推薦的，可能是您的競爭對手。
          </p>
          <ul class="hero-bullets">
            <li>掌握 GEO 數據，在消費者決策的「零關鍵時刻」鎖定勝局。</li>
            <li>重塑品牌在 Google AI Overview、Perplexity 等 AI 引擎中的認知與曝光。</li>
            <li>把過去 SEO 的投資，轉化為 AI 時代可被引用、可被推薦的內容資產。</li>
          </ul>
          <div class="hero-cta-row">
            <button class="btn btn-primary" onclick="document.querySelector('#geo-audit').scrollIntoView({behavior:'smooth'});">
              免費 GEO 報告
            </button>
            <button class="btn btn-ghost" onclick="document.querySelector('#services-main').scrollIntoView({behavior:'smooth'});">
              了解更多 GEO 服務 →
            </button>
          </div>
          <div class="hero-metrics">
            <div>
              <strong>AI 搜索可見度</strong>
              從 0% 到 40%+ 的品牌覆蓋率成長（示例）
            </div>
            <div>
              <strong>引用次數</strong>
              於生成式引擎中 90 天內提升 300%（示例）
            </div>
          </div>
        </div>

        <div class="hero-right">
          <div class="hero-card">
            <div class="badge-pill">
              <span>🔎</span>
              GEO 能見度報告 · Demo
            </div>
            <div class="hero-report-layout">
              <div class="hero-report-header">
                <div>
                  <div style="font-size:11px;color:#e5e7eb;margin-bottom:2px;">品牌 AI 能見度總覽</div>
                  <div style="font-size:10px;color:var(--text-muted);">關鍵提示詞：<span style="color:#bfdbfe;">「最佳保險公司」、「MBA in Hong Kong」</span></div>
                </div>
                <span class="tag">GEO Score 62 / 100</span>
              </div>
              <div class="hero-mock-chart">
                <div class="hero-mock-bar"><span>SEO</span></div>
                <div class="hero-mock-bar"><span>社交</span></div>
                <div class="hero-mock-bar"><span>AI 引用</span></div>
                <div class="hero-mock-bar"><span>口碑</span></div>
              </div>
              <div class="hero-report-footer">
                <div>
                  主要缺口：
                  <span class="pill-mini">AI 未引用關鍵 FAQ</span>
                </div>
                <div>
                  優先建議：
                  <span class="pill-mini">結構化數據 + 來源中心</span>
                </div>
              </div>
            </div>
          </div>
          <div class="hero-floating">
            <div class="hero-floating-title">AI 搜索真實使用場景</div>
            <p class="hero-floating-metric">
              客戶在手機搜尋「香港聖誕餐廳推薦」，Google AI Overview 給出幾間餐廳建議；她選擇其中一間、完成預訂、用餐，事後留下正面評價，並影響下一位看到分享的潛在客戶。
            </p>
            <p class="hero-floating-metric" style="margin-top:6px;">
              這就是 GEO 在「零關鍵時刻」與「終極關鍵時刻」之間的關鍵角色。
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- What is GEO / Intro -->
    <section id="geo-intro">
      <div class="two-col">
        <div>
          <div class="section-kicker">GEO 是什麼？</div>
          <h2 class="section-title">AI 搜索時代的下一步：GEO 建基於優質 SEO 之上</h2>
          <p class="section-lead">
            AI 搜索整合多元資訊來源，包括資料庫、用戶生成內容以及不同部落格等，遠不止傳統搜尋引擎的單一結果頁。傳統 SEO 著眼於網站內容與關鍵字，而 AI 搜索則同時考慮結構化數據、權威引用與內容質素。
          </p>
          <p class="section-lead" style="margin-top:10px;">
            GEO（Generative Engine Optimization）建立在穩固 SEO 基礎之上，品牌仍然需要為特定受眾創作優質內容，讓搜尋與 AI 系統「看得懂」並願意引用您的答案，從而在 AI 摘要與回答中取得推薦與曝光。
          </p>
        </div>
        <div>
          <div class="muted-card">
            <h4>從「被搜尋」到「被回答」</h4>
            <p>
              當用戶問的是「哪一間保險公司最好？」而不是輸入品牌名稱，AI 會在整個網絡中尋找最可信、最完整的答案。若缺乏 GEO 佈局，即使您在傳統 SERP 名列前茅，也有可能在 AI 回答裡完全消失。
            </p>
            <p style="margin-top:6px;">
              GEO 的核心是系統性地塑造與管理品牌在 AI 認知世界中的形象，讓您在關鍵決策對話中，成為那個被點名推薦的答案。
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Customer journey / video & image -->
    <section id="customer-journey">
      <div class="section-kicker">顧客旅程 · AI 時代</div>
      <h2 class="section-title">從搜尋到口碑：SEO、GEO 與 UMOT 的角色</h2>
      <p class="section-lead">
        在過去，顧客多依賴搜尋結果與官網內容做決策；今天，AI 平台已成為預先過濾資訊的「顧問」，而社交平台與用戶評價則放大了終極關鍵時刻（UMOT）的口碑效應。
      </p>

      <div class="journey-card" style="margin-top:16px;">
        <div>示意 · 顧客在 Google 搜尋「Christmas 餐廳 Hong Kong」，AI Overview 推薦數間餐廳，她選擇其中一間、完成預訂、用餐，並在社交媒體分享正面體驗；另一位用戶看到貼文後，被帶入同一間餐廳。</div>
        <div class="journey-grid">
          <div class="journey-col">
            <span class="journey-badge">過去：SEO 為主</span>
            <h4>傳統模式</h4>
            <p>使用者查看 SERP、逐一點擊網站與評論，品牌主要透過 SEO 與廣告競逐曝光，決策時間較長且分散於多個頁面。</p>
          </div>
          <div class="journey-col">
            <span class="journey-badge">現在：AI + UMOT</span>
            <h4>AI 時代</h4>
            <p>AI 將多個來源整合成一個答案，直接推薦數個選項；使用者完成體驗後的分享，成為影響下一輪 AI 內容與他人決策的重要訊號。</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Problem statement / Main services intro -->
    <section id="services-main">
      <div class="section-kicker">主要服務頁面</div>
      <h2 class="section-title">您佔領了搜索排名，卻輸掉了 AI 的「決策對話」</h2>
      <p class="section-lead">
        您的品牌在搜索引擎上名列前茅、網站流量節節攀升，這曾是數位營銷成功的黃金指標。然而，當潛在客戶站在最後決策的十字路口時，他們越來越少反覆點擊多個搜尋結果，而是轉向更智能、更個人化的 AI 助手。
      </p>

      <div class="alert-card" style="margin-top:18px;">
        <div class="alert-title">排名領先的假象：AI 沒有義務「照單全收」您的 SEO 成果</div>
        <p>
          AI 並不會像傳統搜尋引擎一樣，只依賴單一頁面和關鍵字排序，而是整合全域資訊，包括第三方網站、媒體報導、FAQ、用戶評價與結構化資料。若品牌在 AI 認知中的內容稀薄或不完整，即使在 SERP 上名列前茅，也可能在 AI 回答中完全缺席。
        </p>
        <ul class="alert-list">
          <li>當用戶問的是「香港最好的 MBA 是哪間？」結果只出現 HKUST、HKU、CUHK、HKBU、PolyU，而 CityU 即使在「mba hk」有高自然排名，仍然在 AI 回覆中「完全沒有被提及」。</li>
          <li>當您的品牌名稱沒有被主動搜尋，而是被 AI 作為「候選清單」的一部分時，缺乏 GEO 便意味著徹底流失該客戶。</li>
        </ul>
      </div>

      <div class="wide-image-card" style="margin-top:16px;">
        Illustration placeholder：放置「傳統搜尋結果頁 vs AI 平台回答」示意圖，可展示市大商學院案例（SERP 有排名，AI 回答卻沒有品牌名稱）。
      </div>
    </section>

    <!-- SEO vs GEO table -->
    <section id="seo-vs-geo">
      <div class="section-kicker">SEO vs GEO</div>
      <h2 class="section-title">當遊戲規則改變，優化對象也必須升級</h2>
      <p class="section-lead">
        SEO 仍然重要，但只優化傳統搜尋結果已經不足以支撐 AI 決策時代的品牌競爭。GEO 並不是取代 SEO，而是在其基礎上，將內容轉化為 AI 願意引用與總結的結構化答案。
      </p>

      <div class="table-wrap">
        <table>
          <thead>
            <tr>
              <th>維度</th>
              <th>SEO</th>
              <th>GEO</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>平台</td>
              <td>Google、Bing 等傳統搜尋引擎</td>
              <td>Google AI Overviews、ChatGPT、Perplexity、Bing Copilot 等 AI 答案引擎</td>
            </tr>
            <tr>
              <td>搜尋方式</td>
              <td>關鍵字輸入與點擊結果</td>
              <td>對話式提問與追問、多輪互動</td>
            </tr>
            <tr>
              <td>優化目標</td>
              <td>在 SERP 中取得更高自然排名</td>
              <td>在 AI 生成答案中被引用、被作為示例品牌或推薦選項</td>
            </tr>
            <tr>
              <td>主要因素</td>
              <td>關聯性、關鍵字佈局、反向連結、網站權重</td>
              <td>結構化數據、權威引用、清晰可總結的答案、內容完整度與質素</td>
            </tr>
            <tr>
              <td>結果型態</td>
              <td>給用戶一個結果頁，讓他們自行篩選</td>
              <td>替用戶整合多個來源，直接提供縮短版決策建議</td>
            </tr>
          </tbody>
        </table>
      </div>
    </section>

    <!-- Zero Moment of Truth -->
    <section id="zmot">
      <div class="section-kicker">零關鍵時刻 · ZMOT</div>
      <h2 class="section-title">重塑「零關鍵時刻」：從被動等待點擊到主動植入決策</h2>
      <p class="section-lead">
        在 AI 驅動的顧客旅程中，消費者在接觸品牌之前，往往已透過 AI 平台完成一輪深入調研；使用後的真實體驗與線上分享，則成為下一批潛在客戶的關鍵證據鏈。
      </p>

      <div class="zmot-card">
        <p>
          YouFind GEO 以「全方位能見度閉環系統」為核心，連接從 ZMOT（Zero Moment of Truth）到 UMOT（Ultimate Moment of Truth）的每一個節點，協助品牌從「被動等待點擊」轉型為「主動植入決策」。
        </p>
        <div class="pill-row">
          <span>AI 搜尋認知（Zero Moment of Truth）</span>
          <span>內容體驗與服務感受（First / Second Moment of Truth）</span>
          <span>用戶分享與評價（Ultimate Moment of Truth）</span>
        </div>
      </div>
    </section>

    <!-- How AI answer engines work -->
    <section id="ai-engines">
      <div class="section-kicker">AI 答案引擎如何運作？</div>
      <h2 class="section-title">AI Overviews、ChatGPT、Perplexity 為什麼需要 GEO？</h2>
      <p class="section-lead">
        AI 答案引擎會擷取多個來源，重組為一段自然語言答案，並只在畫面底部展示少量引用來源。若品牌的內容不具備「可引用性」與「可總結性」，便難以在這些平台中取得一席之地。
      </p>

      <div class="cards-grid-3">
        <div class="small-card">
          <h4>Google AI Overview</h4>
          <p>將傳統 SERP、知識圖譜、結構化資料與第三方內容融合為一段回答，並於答案下方附上少數來源連結。</p>
          <div class="link-list">
            <a href="https://www.youfind.hk/google-ai-overview" target="_blank">➜ 深入了解 Google AI Overview</a>
          </div>
        </div>
        <div class="small-card">
          <h4>ChatGPT / Gemini 等</h4>
          <p>以對話方式處理複雜問題，逐步引導用戶決策。品牌需要透過長期內容與權威訊號，讓 AI 將您視為「可引用」的專家來源。</p>
          <div class="link-list">
            <a href="https://www.youfind.hk/ai-chatgpt" target="_blank">➜ ChatGPT 與內容引用</a>
            <a href="https://www.youfind.hk/ai-gemini" target="_blank">➜ Google Gemini</a>
          </div>
        </div>
        <div class="small-card">
          <h4>Perplexity / Deepseek</h4>
          <p>強調「帶引用」的答案，會清楚標示內容來源。GEO 的目標之一，就是讓品牌成為這些引用中經常出現的名稱。</p>
          <div class="link-list">
            <a href="https://www.youfind.hk/ai-perplexity" target="_blank">➜ Perplexity 介紹</a>
            <span>Deepseek：TBC</span>
          </div>
        </div>
      </div>
    </section>

    <!-- 1+1+1 combo -->
    <section id="combo">
      <div class="section-kicker">YouFind GEO 1+1+1 &gt; 3</div>
      <h2 class="section-title">打造您的品牌能見度閉環</h2>
      <p class="section-lead">
        YouFind GEO 將技術 SEO、內容策略與 AI 引擎優化整合為 1+1+1 &gt; 3 的方案組合，為不同階段品牌建立可持續擴張的 AI 能見度。
      </p>

      <div class="combo-card">
        <p>三大模組可按需組合，從單一專案到持續顧問，靈活配合企業內部資源與成長階段。</p>
        <div class="combo-grid">
          <div class="combo-item">
            <span class="combo-tag">1 · 技術與基礎</span>
            <p>Full funnel audit（SEO & SEM）、技術健康檢查、結構化資料實作、Robots.txt 與 AI 爬蟲設定等。</p>
          </div>
          <div class="combo-item">
            <span class="combo-tag">1 · 內容與來源中心</span>
            <p>SEO / GEO 內容計畫、FAQ 中心與支柱頁建置、內容原子化與跨渠道再利用。</p>
          </div>
          <div class="combo-item">
            <span class="combo-tag">1 · AI 引擎優化</span>
            <p>針對 Google AI Overview、Perplexity 等的提示詞場景設計、結果監測與持續優化。</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Why YouFind -->
    <section id="why-youfind">
      <div class="section-kicker">為什麼選擇 YouFind？</div>
      <h2 class="section-title">GEO 不是實驗，而是方法論</h2>
      <p class="section-lead">
        YouFind 結合多年 SEO & Performance Marketing 實戰經驗與最新 AI 搜索研究，為品牌設計可落地、可量度的 GEO 策略，避免將預算耗費在無法被 AI 讀懂的內容上。
      </p>

      <div class="why-grid">
        <div class="why-item">
          <h4>跨行業實戰經驗</h4>
          <p>從保險、金融到醫療與教育，已協助多個行業建立 AI 搜索能見度，累積大量真實搜尋場景與關鍵字資料。</p>
        </div>
        <div class="why-item">
          <h4>完整方法與工具</h4>
          <p>自研 GEO Audit Framework，結合技術掃描、內容評估與 AI 實測，輸出具體行動清單與優先順序。</p>
        </div>
        <div class="why-item">
          <h4>顧問式長期合作</h4>
          <p>不只交付報告，而是伴隨品牌持續調整內容與技術，與不斷變化的 AI 生態一起演進。</p>
        </div>
      </div>
    </section>

    <!-- Free GEO Audit -->
    <section id="geo-audit">
      <div class="section-kicker">GEO 免費評核</div>
      <h2 class="section-title">在行動前，先看見自己的 AI 盲區</h2>
      <p class="section-lead">
        透過 GEO 免費評核，您可以在短時間內掌握目前品牌在主要 AI 引擎中的能見度、與競爭者的差距，以及最值得優先處理的三個行動項目。
      </p>

      <div class="audit-card">
        <div>
          <h3 style="font-size:16px;margin-bottom:4px;">報告將包含什麼？</h3>
          <ul class="bullet-list">
            <li>AI 能見度分析：品牌在 Google AI Overview、Perplexity 等平台的出現次數與位置。</li>
            <li>競爭對手差距：選定 2–3 個關鍵競爭者，對比其在關鍵提示詞下的引用情況。</li>
            <li>技術與內容漏洞檢查：結構化資料、FAQ 架構、來源可信度與可引用性評估。</li>
            <li>3 項優先建議：在 90 天內可執行、可衡量的 GEO 行動方案。</li>
          </ul>
          <button class="btn btn-primary" style="margin-top:12px;" onclick="document.querySelector('#contact').scrollIntoView({behavior:'smooth'});">
            預約免費 GEO 評核
          </button>
        </div>
        <div>
          <div class="wide-image-card">
            Illustration placeholder：放置 GEO 報告樣本截圖，標示 AI 能見度分數、競品對比圖與優先建議清單。
          </div>
        </div>
      </div>
    </section>

    <!-- Ongoing consulting -->
    <section id="consulting">
      <div class="section-kicker">持續優化顧問服務</div>
      <h2 class="section-title">AI 生態不斷變化，您的內容也要跟上</h2>
      <p class="section-lead">
        AI 引擎的演算法與引用規則會持續更新，單次專案難以長期維持能見度。YouFind 提供持續顧問服務，協助品牌在變化中穩定擴張 AI 版圖。
      </p>

      <div class="strip-card">
        <div>
          <div style="font-weight:500;margin-bottom:4px;">YouFind GEO 顧問服務內容</div>
          <ul>
            <li>主題擴展與內容原子化：將旗艦內容拆分為多個可被 AI 引用的小單位。</li>
            <li>結構化資料維護：持續更新 FAQPage、Article 等 Schema 標記。</li>
            <li>內容更新與測試：按 AI 搜尋結果調整標題、段落與示例，並進行 A/B 測試。</li>
            <li>成效衡量：追蹤 AI 引用次數、關鍵提示詞覆蓋率與轉化指標。</li>
          </ul>
        </div>
        <button class="btn btn-ghost" onclick="document.querySelector('#contact').scrollIntoView({behavior:'smooth'});">
          了解顧問方案 →
        </button>
      </div>
    </section>

    <!-- Success cases -->
    <section id="cases">
      <div class="section-kicker">成功案例</div>
      <h2 class="section-title">用 STAR 法則說故事，而不是只列清單</h2>
      <p class="section-lead">
        以下為示例結構，可依實際客戶資料填入數據與細節；建議選擇來自不同產業的代表性案例，並以 STAR（情境、任務、行動、成果）框架呈現。
      </p>

      <div class="logos-strip" style="margin-top:14px;">
        <div>
          <div style="font-size:13px;margin-bottom:2px;">代表客戶 · 點擊前往案例頁</div>
          <div style="font-size:12px;color:#e5e7eb;">（保險 · 金融 · 醫療等行業示意）</div>
        </div>
        <div class="logos-buttons">
          <button class="chip" onclick="document.querySelector('#case-insurance').scrollIntoView({behavior:'smooth'});">Insurance</button>
          <button class="chip" onclick="document.querySelector('#case-finance').scrollIntoView({behavior:'smooth'});">Finance</button>
          <button class="chip" onclick="document.querySelector('#case-health').scrollIntoView({behavior:'smooth'});">Healthcare</button>
        </div>
      </div>

      <div class="case-grid" style="margin-top:18px;">
        <div>
          <div class="case-card" id="case-insurance">
            <div class="case-header">
              <h4>Successful Case 1：Insurance</h4>
              <span class="case-tag">Hong Leong Insurance</span>
            </div>
            <div class="case-subtitle">
              Hong Leong Insurance 成立於 1973 年，是香港持牌保險公司，為個人、企業及工業客戶提供多元產品，並致力成為領先的個人保險供應商。
            </div>
            <ol class="case-star-list">
              <li><strong>情境：</strong>隨著 AI 平台查詢興起，品牌在傳統搜尋仍有能見度，但在 AI 搜尋結果中幾乎沒有被提及。</li>
              <li><strong>任務：</strong>提升與品牌及產品相關的關鍵詞，在主要生成式引擎中的引用比例與出現次數。</li>
              <li><strong>行動：</strong>聚焦四大方向：
                <ul style="margin-top:4px;padding-left:18px;">
                  <li>Intent-driven Content：圍繞「為何」與「如何」撰寫內容，而非只堆砌關鍵字。</li>
                  <li>Holistic Topic Coverage：以「家居保險」等主題建立完整知識版圖。</li>
                  <li>Establishing Credibility：加入專業參考、數據與術語，加強專家形象。</li>
                  <li>AI-readable Organization：優化段落架構與 FAQ，使 AI 更易於摘要與引用。</li>
                </ul>
              </li>
              <li><strong>成果：</strong>可於此放置具體數字，例如「90 天內 Perplexity 引用次數提升 300%，Google AI Overviews 覆蓋率由 0% 升至 40%。」</li>
            </ol>
          </div>
        </div>

        <div class="case-aside">
          <div class="case-metric-card">
            <div style="font-size:12px;color:#bbf7d0;margin-bottom:4px;">量化成效示意</div>
            <p>建議於此放置 AI 搜尋結果截圖（如品牌被列為示例保險公司），並標示前後對比數據。</p>
          </div>
          <div class="case-card" id="case-finance">
            <div class="case-header">
              <h4>Successful Case 2：Finance</h4>
              <span class="case-tag">Promise</span>
            </div>
            <p class="case-subtitle">
              於此填入財務品牌背景、目標受眾與面臨挑戰，並以 STAR 結構呈現任務與成果。
            </p>
          </div>
          <div class="case-card" id="case-health">
            <div class="case-header">
              <h4>Successful Case 3：Healthcare</h4>
              <span class="case-tag">Chinese Essence Medicine / Hair Care</span>
            </div>
            <p class="case-subtitle">
              適合展示在高度競爭、講求專業信任的行業中，如何透過 GEO 增加在 AI 平台上的專家地位與品牌能見度。
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Blog -->
    <section id="blog">
      <div class="section-kicker">部落格 · GEO Insight</div>
      <h2 class="section-title">用內容教育市場，同時教育 AI</h2>
      <p class="section-lead">
        部落格不只是 SEO 工具，更是讓 AI 理解您在某個主題上是否具備深度與廣度的重要訊號。建議以「支柱頁 + 叢集內容」方式長期經營。
      </p>

      <div class="blog-grid">
        <div class="blog-card">
          <span class="blog-tag">教學類</span>
          <h4>如何讓您的內容被 Google AI 引用？</h4>
          <p>示範從結構化資料、FAQ 設計到來源可信度，逐步提升在 AI Overviews 中的引用機率。</p>
        </div>
        <div class="blog-card">
          <span class="blog-tag">趨勢類</span>
          <h4>Perplexity 內容引用趨勢觀察（2024）</h4>
          <p>整理常被引用網站的共通點，例如內容深度、更新頻率與外部權威來源連結等。</p>
        </div>
        <div class="blog-card">
          <span class="blog-tag">觀點類</span>
          <h4>為什麼 GEO 是 SEO 的下一步？</h4>
          <p>從品牌資產角度，解釋為何應將內容視為「AI 可讀的長期投資」，而非短期排名專案。</p>
        </div>
      </div>
    </section>

    <!-- Pricing -->
    <section id="pricing">
      <div class="section-kicker">Pricing</div>
      <h2 class="section-title">按品牌成熟度與需求設計的 GEO 方案</h2>
      <p class="section-lead">
        以下為建議的頁面結構，可對應實際定價與服務內容作出調整；由入門評核、專案型優化，以至長期顧問皆可配置。
      </p>

      <div class="pricing-grid">
        <div class="pricing-card">
          <h4>Starter · GEO Audit</h4>
          <div class="pricing-price">請聯絡報價</div>
          <ul class="pricing-features">
            <li>AI 搜索能見度掃描</li>
            <li>關鍵提示詞與競品對比</li>
            <li>高層管理摘要簡報一次</li>
          </ul>
          <button class="btn btn-ghost" style="margin-top:10px;" onclick="document.querySelector('#contact').scrollIntoView({behavior:'smooth'});">
            索取評核方案
          </button>
        </div>
        <div class="pricing-card" style="border-color:rgba(234,179,8,0.6);box-shadow:0 20px 50px rgba(234,179,8,0.28);">
          <h4>Growth · GEO 專案</h4>
          <div class="pricing-price">請聯絡報價</div>
          <ul class="pricing-features">
            <li>完整 GEO Audit 與優化 Roadmap</li>
            <li>內容 / FAQ / 結構化資料落地實作</li>
            <li>AI 平台實測與效果追蹤</li>
          </ul>
          <button class="btn btn-primary" style="margin-top:10px;" onclick="document.querySelector('#contact').scrollIntoView({behavior:'smooth'});">
            預約專人講解
          </button>
        </div>
        <div class="pricing-card">
          <h4>Enterprise · 顧問服務</h4>
          <div class="pricing-price">請聯絡報價</div>
          <ul class="pricing-features">
            <li>跨國 / 多品牌 GEO 戰略規劃</li>
            <li>每月顧問會議與報告</li>
            <li>與內部 SEO / Brand / IT 團隊協作</li>
          </ul>
          <button class="btn btn-ghost" style="margin-top:10px;" onclick="document.querySelector('#contact').scrollIntoView({behavior:'smooth'});">
            了解企業方案
          </button>
        </div>
      </div>
    </section>

    <!-- FAQ -->
    <section id="faq">
      <div class="section-kicker">常見問題</div>
      <h2 class="section-title">還在猶豫 GEO 是否適合您？</h2>
      <p class="section-lead">
        以下問題與答案可作為 FAQ 結構草稿，亦建議以 FAQPage 結構化資料形式實作，提升被 AI 讀取與摘要的機會。
      </p>

      <div class="faq-grid">
        <div class="faq-item">
          <h4>Q：我們已經在做 SEO，為什麼還需要 GEO？</h4>
          <p>A：SEO 解決的是「在 SERP 上被看見」的問題，GEO 則是讓 AI 願意在回答中「引用您」。兩者並非二選一，而是相互強化的關係。</p>
        </div>
        <div class="faq-item">
          <h4>Q：GEO 是否可以在短時間內看到結果？</h4>
          <p>A：部分技術修正與 FAQ 結構優化可以在數週內出現初步變化，但要在多個 AI 平台建立穩定能見度，仍需視行業與競爭程度而定。</p>
        </div>
        <div class="faq-item">
          <h4>Q：哪些行業特別適合優先投資 GEO？</h4>
          <p>A：高決策成本與資訊不對稱的行業，如保險、金融、醫療、教育、B2B 解決方案等，尤為適合優先佈局。</p>
        </div>
        <div class="faq-item">
          <h4>Q：如果我們沒有內部內容團隊，還能做 GEO 嗎？</h4>
          <p>A：可以。YouFind 可協助您從策略到內容製作一站式執行，或與既有代理商與內部團隊協作。</p>
        </div>
      </div>
    </section>

    <!-- Contact / Consultation -->
    <section id="contact">
      <div class="section-kicker">預約諮詢</div>
      <h2 class="section-title">想知道您的品牌在 AI 世界裡「看得見嗎」？</h2>
      <p class="section-lead">
        填妥以下資料，我們將安排專人與您聯絡，說明 GEO 免費評核內容，並一起討論適合貴公司的方案。
      </p>

      <div class="contact-grid">
        <div class="contact-card">
          <h3 style="font-size:15px;margin-bottom:8px;">聯絡方法</h3>
          <p>您可以透過以下任一方式與我們聯絡：</p>
          <ul class="bullet-list">
            <li>填寫右方表格，預約 GEO 顧問諮詢。</li>
            <li>電郵：<a href="mailto:info@youfind.com">info@youfind.com</a>（示意，可替換為實際電郵）。</li>
            <li>電話：+852 XXXX XXXX（示意，可替換為實際電話）。</li>
          </ul>
        </div>
        <div class="contact-card">
          <form class="contact-form">
            <div class="field">
              <label for="name">姓名 / Name</label>
              <input type="text" id="name" name="name" placeholder="請輸入您的姓名" />
            </div>
            <div class="field">
              <label for="company">公司名稱 / Company</label>
              <input type="text" id="company" name="company" placeholder="請輸入公司名稱" />
            </div>
            <div class="field">
              <label for="email">電郵 / Email</label>
              <input type="email" id="email" name="email" placeholder="name@company.com" />
            </div>
            <div class="field">
              <label for="industry">行業 / Industry</label>
              <select id="industry" name="industry">
                <option value="">請選擇</option>
                <option>保險 / Insurance</option>
                <option>金融 / Finance</option>
                <option>醫療 / Healthcare</option>
                <option>教育 / Education</option>
                <option>B2B / SaaS</option>
                <option>其他 / Others</option>
              </select>
            </div>
            <div class="field">
              <label for="message">想了解的重點 / Message</label>
              <textarea id="message" name="message" placeholder="例如：希望了解現時在 AI 搜尋中的能見度、某產品線的 GEO 策略等。"></textarea>
            </div>
            <button type="submit" class="btn btn-primary">提交預約</button>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div>© YouFind AIPO · GEO Solutions</div>
    <div>設計參考 HubSpot AI CRM 產品頁 · 內容為示意，可按實際服務調整。</div>
  </footer>
</body>
</html>
