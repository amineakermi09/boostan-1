<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>BOOSTan – Smart Greenhouse Automation</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />

  <!-- Google Font -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">

  <style>
    :root {
      --bg: #f7f8f3;
      --white: #ffffff;
      --green: #4f8f3a;
      --green-dark: #336428;
      --green-soft: #e4f4df;
      --yellow: #ffd966;
      --text-main: #202020;
      --text-muted: #707070;
      --border-soft: #eceee6;
      --shadow-soft: 0 14px 40px rgba(0, 0, 0, 0.06);
      --radius-lg: 22px;
      --radius-md: 16px;
      --radius-pill: 999px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: "Poppins", system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
      background: var(--bg);
      color: var(--text-main);
      line-height: 1.6;
    }

    img {
      max-width: 100%;
      display: block;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    .page {
      min-height: 100vh;
      padding: 32px 32px 48px;
    }

    .shell {
      max-width: 1160px;
      margin: 0 auto;
    }

    /* NAVBAR */
    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 40px;
    }

    .nav-left {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .nav-logo {
      width: 38px;
      height: 38px;
      border-radius: 12px;
      background: #e7f5df;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .nav-logo img {
      width: 30px;
      height: auto;
    }

    .brand-name {
      font-weight: 700;
      font-size: 20px;
      color: var(--green-dark);
    }

    .nav-menu {
      display: flex;
      align-items: center;
      gap: 28px;
      font-size: 14px;
      color: var(--text-muted);
    }

    .nav-menu a {
      position: relative;
    }

    .nav-menu a:hover::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: -6px;
      width: 100%;
      height: 2px;
      border-radius: 999px;
      background: var(--green);
    }

    .nav-right {
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 14px;
    }

    .btn {
      border-radius: var(--radius-pill);
      padding: 10px 24px;
      font-size: 14px;
      border: 1px solid transparent;
      cursor: pointer;
      font-weight: 500;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      transition: transform 0.1s ease, box-shadow 0.1s ease, background 0.15s ease;
      background: transparent;
    }

    .btn-primary {
      background: var(--green);
      color: #fff;
      box-shadow: 0 10px 24px rgba(79, 143, 58, 0.32);
    }

    .btn-primary:hover {
      background: var(--green-dark);
      transform: translateY(-1px);
    }

    .btn-outline {
      background: #ffffff;
      color: var(--text-main);
      border-color: var(--border-soft);
    }

    .btn-outline:hover {
      box-shadow: 0 8px 18px rgba(0,0,0,0.05);
      transform: translateY(-1px);
    }

    .nav-signin {
      color: var(--text-muted);
      cursor: pointer;
    }

    /* HERO */
    .hero {
      display: grid;
      grid-template-columns: minmax(0, 1.2fr) minmax(0, 1fr);
      gap: 40px;
      align-items: center;
      margin-bottom: 48px;
    }

    .hero-eyebrow {
      font-size: 14px;
      color: var(--green-dark);
      font-weight: 500;
      margin-bottom: 6px;
    }

    .hero-title {
      font-size: 42px;
      font-weight: 700;
      line-height: 1.2;
      margin-bottom: 12px;
      color: var(--green-dark);
    }

    .hero-subtitle {
      font-size: 18px;
      font-weight: 500;
      margin-bottom: 12px;
    }

    .hero-body {
      font-size: 14px;
      color: var(--text-muted);
      max-width: 420px;
      margin-bottom: 22px;
    }

    .hero-ctas {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
    }

    /* CARD: HERO APP PREVIEW */
    .panel {
      background: var(--white);
      border-radius: 26px;
      box-shadow: var(--shadow-soft);
      padding: 24px 22px;
      border: 1px solid var(--border-soft);
    }

    .panel-header {
      font-weight: 600;
      margin-bottom: 12px;
      font-size: 16px;
    }

    .list {
      display: flex;
      flex-direction: column;
      gap: 10px;
      margin-bottom: 18px;
    }

    .list-item {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 10px 12px;
      border-radius: 14px;
      background: #f8faf4;
      font-size: 13px;
    }

    .list-item-label {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .icon-pill {
      width: 22px;
      height: 22px;
      border-radius: 999px;
      background: var(--green-soft);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 13px;
      color: var(--green-dark);
    }

    .panel-foot {
      margin-top: 6px;
      padding-top: 14px;
      border-top: 1px dashed #e2e6d8;
      font-size: 12px;
    }

    .health-label {
      font-weight: 600;
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 6px;
    }

    .mini-chart {
      height: 40px;
      border-radius: 12px;
      background: linear-gradient(90deg, #9fd59b, #f3e28f);
      position: relative;
      overflow: hidden;
    }

    .mini-chart-line {
      position: absolute;
      left: 6%;
      right: 6%;
      bottom: 12px;
      height: 2px;
      border-radius: 999px;
      background: #2f6c28;
    }

    /* FEATURE ROW */
    .features-row {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 18px;
      margin-bottom: 48px;
    }

    .feature-card {
      background: var(--white);
      border-radius: var(--radius-lg);
      padding: 20px 18px;
      box-shadow: 0 10px 26px rgba(0, 0, 0, 0.04);
      border: 1px solid var(--border-soft);
      display: flex;
      flex-direction: column;
      gap: 8px;
      font-size: 13px;
    }

    .feature-icon {
      width: 30px;
      height: 30px;
      border-radius: 12px;
      background: var(--green-soft);
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 4px;
      font-size: 16px;
      color: var(--green-dark);
    }

    .feature-title {
      font-weight: 600;
    }

    .feature-text {
      color: var(--text-muted);
    }

    /* PREDICT SECTION */
    .section {
      margin-bottom: 48px;
    }

    .section-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.1fr) minmax(0, 1fr);
      gap: 32px;
      align-items: flex-start;
    }

    .section-title {
      font-size: 24px;
      font-weight: 600;
      margin-bottom: 10px;
      color: var(--green-dark);
    }

    .section-text {
      font-size: 14px;
      color: var(--text-muted);
      max-width: 430px;
    }

    /* METRICS CARD */
    .metrics-card {
      background: var(--white);
      border-radius: var(--radius-lg);
      box-shadow: var(--shadow-soft);
      padding: 18px 20px;
      border: 1px solid var(--border-soft);
      font-size: 13px;
    }

    .metrics-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 10px;
    }

    .metrics-header span:last-child {
      font-size: 11px;
      color: var(--text-muted);
    }

    .metric-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 10px;
    }

    .metric-label {
      color: var(--text-muted);
      font-size: 12px;
    }

    .metric-value {
      font-weight: 500;
    }

    .metric-bar {
      position: relative;
      height: 8px;
      border-radius: 999px;
      background: #eef0e5;
      overflow: hidden;
    }

    .metric-bar-fill {
      position: absolute;
      top: 0;
      left: 0;
      bottom: 0;
      width: 70%;
      border-radius: inherit;
      background: linear-gradient(90deg, #91d489, #f2e27f);
    }

    /* DASHBOARD SECTION */
    .section-heading-row {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      margin-bottom: 16px;
    }

    .section-heading-row h2 {
      font-size: 22px;
      font-weight: 600;
    }

    .section-heading-row span {
      font-size: 12px;
      color: var(--text-muted);
    }

    .dashboard-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.5fr) minmax(0, 0.9fr);
      gap: 24px;
    }

    .dashboard-card {
      background: var(--white);
      border-radius: var(--radius-lg);
      box-shadow: var(--shadow-soft);
      padding: 18px 20px 20px;
      border: 1px solid var(--border-soft);
      font-size: 13px;
    }

    .status-pill {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border-radius: var(--radius-pill);
      padding: 6px 14px;
      font-size: 11px;
      background: #e4f4df;
      color: var(--green-dark);
      margin-bottom: 16px;
      font-weight: 500;
    }

    .metrics-grid {
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: 8px;
      margin-bottom: 16px;
    }

    .metrics-pill {
      background: #f8faf4;
      border-radius: 14px;
      padding: 10px;
      border: 1px solid #ecf1e4;
      font-size: 11px;
    }

    .metrics-pill strong {
      display: block;
      margin-bottom: 4px;
    }

    .health-trend {
      font-size: 12px;
    }

    .trend-bars {
      height: 10px;
      border-radius: 999px;
      background: #eef0e5;
      margin-top: 6px;
      overflow: hidden;
      display: grid;
      grid-template-columns: 3fr 1.5fr 1fr;
      gap: 0;
    }

    .trend-good {
      background: #7ccf7c;
    }

    .trend-watch {
      background: #f3cb63;
    }

    .trend-issue {
      background: #f08b76;
    }

    .automation-card {
      background: var(--white);
      border-radius: var(--radius-lg);
      box-shadow: var(--shadow-soft);
      padding: 18px 18px 20px;
      border: 1px solid var(--border-soft);
      font-size: 13px;
    }

    .automation-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 6px;
    }

    .automation-title {
      font-weight: 600;
    }

    .automation-badge {
      padding: 4px 10px;
      border-radius: var(--radius-pill);
      background: #e4f4df;
      font-size: 11px;
      color: var(--green-dark);
      font-weight: 500;
    }

    .automation-body {
      font-size: 12px;
      color: var(--text-muted);
      margin-bottom: 12px;
    }

    .automation-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 11px;
    }

    .automation-icons {
      display: flex;
      gap: 8px;
      font-size: 14px;
      color: #b0b2aa;
    }

    .automation-progress {
      width: 100%;
      height: 7px;
      border-radius: 999px;
      background: #eef0e5;
      overflow: hidden;
      margin-top: 6px;
    }

    .automation-progress span {
      display: block;
      height: 100%;
      width: 60%;
      background: linear-gradient(90deg, #7ccf7c, #f3cb63);
    }

    /* FOOTER */
    footer {
      margin-top: 40px;
      padding-top: 16px;
      border-top: 1px solid #e1e5d7;
      font-size: 12px;
      color: var(--text-muted);
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 8px;
      align-items: center;
    }

    .footer-links {
      display: flex;
      gap: 18px;
    }

    .footer-brand {
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .footer-leaf {
      width: 16px;
      height: 16px;
      border-radius: 999px;
      background: var(--green-soft);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 11px;
      color: var(--green-dark);
    }

    /* RESPONSIVE */
    @media (max-width: 960px) {
      .page {
        padding: 20px 16px 32px;
      }

      .nav-menu {
        display: none;
      }

      .hero {
        grid-template-columns: minmax(0, 1fr);
      }

      .hero-title {
        font-size: 34px;
      }

      .features-row {
        grid-template-columns: 1fr;
      }

      .section-grid,
      .dashboard-grid {
        grid-template-columns: 1fr;
      }

      .metrics-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
    }
  </style>
</head>
<body>
  <div class="page">
    <div class="shell">

      <!-- NAVBAR -->
      <header class="nav">
        <div class="nav-left">
          <div class="nav-logo">
            <!-- replace src with your logo file -->
            <img src="logo-boostan.png" alt="BOOSTan logo" />
          </div>
          <div class="brand-name">BOOSTan</div>
        </div>

        <nav class="nav-menu" aria-label="Main navigation">
          <a href="#">How it works</a>
          <a href="#">Dashboard</a>
          <a href="#">Pricing</a>
          <a href="#">Contact</a>
        </nav>

        <div class="nav-right">
          <span class="nav-signin">Sign in</span>
          <button class="btn btn-primary">Get Started</button>
        </div>
      </header>

      <main>
        <!-- HERO -->
        <section class="hero">
          <div>
            <div class="hero-eyebrow">Smart Greenhouse Automation</div>
            <h1 class="hero-title">What if growing green was easier than ever?</h1>
            <h2 class="hero-subtitle">Letting you grow more with less.</h2>
            <p class="hero-body">
              <strong>Boost plant and planet health</strong> with intelligent greenhouse automation that
              monitors conditions and reacts in real time.
            </p>

            <div class="hero-ctas">
              <button class="btn btn-primary">Get Started</button>
              <button class="btn btn-outline">View Dashboard</button>
            </div>
          </div>

          <!-- App-like preview card -->
          <aside class="panel" aria-label="Smart automation preview">
            <div class="panel-header">Smart Automation</div>

            <div class="list">
              <div class="list-item">
                <div class="list-item-label">
                  <span class="icon-pill">🏠</span>
                  <span>Smart Application</span>
                </div>
                <span>Active</span>
              </div>
              <div class="list-item">
                <div class="list-item-label">
                  <span class="icon-pill">🌿</span>
                  <span>Illness Detection</span>
                </div>
                <span>Scanning</span>
              </div>
              <div class="list-item">
                <div class="list-item-label">
                  <span class="icon-pill">⚙️</span>
                  <span>Predictive Maintenance</span>
                </div>
                <span>Ready</span>
              </div>
            </div>

            <div class="panel-foot">
              <div class="health-label">
                <span>Plant Health</span>
                <span>Healthy ✓</span>
              </div>
              <div class="mini-chart">
                <div class="mini-chart-line"></div>
              </div>
            </div>
          </aside>
        </section>

        <!-- FEATURES -->
        <section class="features-row" aria-label="Key features">
          <article class="feature-card">
            <div class="feature-icon">🏡</div>
            <div class="feature-title">Smart Automation</div>
            <p class="feature-text">
              Automate complex greenhouse tasks with rules that respond to live sensor data.
            </p>
          </article>

          <article class="feature-card">
            <div class="feature-icon">🌱</div>
            <div class="feature-title">Illness Detection</div>
            <p class="feature-text">
              Spot harmful conditions early with continuous monitoring and anomaly alerts.
            </p>
          </article>

          <article class="feature-card">
            <div class="feature-icon">⚙️</div>
            <div class="feature-title">Predictive Maintenance</div>
            <p class="feature-text">
              Stay ahead of repairs and upkeep with predictive insights and reminders.
            </p>
          </article>
        </section>

        <!-- PREDICT PROBLEMS -->
        <section class="section">
          <div class="section-grid">
            <div>
              <h2 class="section-title">Predict plant problems before they happen.</h2>
              <p class="section-text">
                Monitor CO₂, soil pH, nutrients and light levels in real time. Receive smart alerts
                before plants are stressed so you can intervene early and protect your yields.
              </p>
            </div>

            <aside class="metrics-card" aria-label="Health metrics">
              <div class="metrics-header">
                <strong>Stack health</strong>
                <span>Live overview</span>
              </div>

              <div class="metric-row">
                <span class="metric-label">Status</span>
                <span class="metric-value">Healthy ✓</span>
              </div>
              <div class="metric-row">
                <span class="metric-label">CO₂</span>
                <span class="metric-value">742 ppm</span>
              </div>
              <div class="metric-row">
                <span class="metric-label">Soil pH</span>
                <span class="metric-value">6.4 pH</span>
              </div>
              <div class="metric-row">
                <span class="metric-label">Nutrients</span>
                <span class="metric-value">88%</span>
              </div>
              <div class="metric-row">
                <span class="metric-label">Light</span>
                <span class="metric-value">91%</span>
              </div>

              <div class="metric-bar">
                <div class="metric-bar-fill"></div>
              </div>
            </aside>
          </div>
        </section>

        <!-- DASHBOARD -->
        <section class="section">
          <div class="section-heading-row">
            <h2>Dashboard — Aiesec’s GreenHouse</h2>
            <span>View everything in a single, simple place.</span>
          </div>

          <div class="dashboard-grid">
            <article class="dashboard-card" aria-label="Dashboard metrics">
              <div class="status-pill">
                <span>●</span> Status: 95% Healthy
              </div>

              <div class="metrics-grid">
                <div class="metrics-pill">
                  <strong>Moisture</strong>
                  71% · Good
                </div>
                <div class="metrics-pill">
                  <strong>Heat</strong>
                  22°C · Optimal
                </div>
                <div class="metrics-pill">
                  <strong>Nutrients</strong>
                  High · Sufficient
                </div>
                <div class="metrics-pill">
                  <strong>Light</strong>
                  High · Stable
                </div>
              </div>

              <div class="health-trend">
                Health Trend
                <div class="trend-bars">
                  <div class="trend-good"></div>
                  <div class="trend-watch"></div>
                  <div class="trend-issue"></div>
                </div>
              </div>
            </article>

            <aside class="automation-card" aria-label="Automation rule">
              <div class="automation-header">
                <div class="automation-title">Morning Irrigation</div>
                <div class="automation-badge">Active</div>
              </div>
              <div class="automation-body">
                If moisture &lt; 45% and time is between 6–10 AM, automatically run Zone 1 irrigation
                for 15 minutes.
              </div>
              <div class="automation-footer">
                <div>
                  Next run: tomorrow · 06:15
                  <div class="automation-progress">
                    <span></span>
                  </div>
                </div>
                <div class="automation-icons">
                  <span>✏️</span>
                  <span>🗑️</span>
                </div>
              </div>
            </aside>
          </div>
        </section>
      </main>

      <!-- FOOTER -->
      <footer>
        <div class="footer-brand">
          <div class="footer-leaf">🌿</div>
          <span>BOOSTan · Growing green made easier.</span>
        </div>
        <div class="footer-links">
          <a href="#">About</a>
          <a href="#">How it works</a>
          <a href="#">Contact</a>
          <a href="#">Privacy</a>
        </div>
      </footer>

    </div>
  </div>
</body>
</html>
