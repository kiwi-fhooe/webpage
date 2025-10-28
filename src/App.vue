<template>
  <div id="app">
    <!-- Header -->
    <header class="header" :style="{ backgroundColor: headerColor }">
      <nav class="nav">
        <div class="container">
          <div class="nav-content">
            <div class="logo">
              <img src="/kiwi_logo.svg" alt="KIWi Logo" class="logo-img">
            </div>
            <div class="nav-links">
              <a href="#about" class="nav-link">Über KIWi</a>
              <a href="#goals" class="nav-link">Ziele</a>
              <a href="#modules" class="nav-link">Module</a>
              <a href="#partners" class="nav-link">Partner</a>
              <a href="#contact" class="nav-link">Kontakt</a>
            </div>
          </div>
        </div>
      </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <div class="hero-text">
            <h1 class="hero-title fade-in-up">
              KI & Wissenschaft:<br>
              <span class="text-gradient">KI-Workshops für Bildungseinrichtungen</span>
            </h1>
            <p class="hero-description fade-in-up">
              KIWi bringt Künstliche Intelligenz kindgerecht in Schulen. 
              Wir fördern kritisches Denken und wecken Begeisterung für Forschung und Technik.
            </p>
            <div class="hero-buttons fade-in-up">
              <a href="#about" class="btn btn-primary">Mehr erfahren</a>
              <a href="#contact" class="btn btn-outline">Kontakt aufnehmen</a>
            </div>
          </div>
          <div class="hero-visual">
            <img src="/kiwi_icon.svg" alt="KIWi Icon" class="hero-icon">
          </div>
        </div>
      </div>
    </section>


    <!-- Goals Section -->
    <section id="goals" class="section section-alt">
      <div class="container">
        <div class="section-header">
          <h2>Ziele des Projekts</h2>
          <p class="section-description">
            Unser Ziel ist es, Kinder und Jugendliche frühzeitig mit KI vertraut zu machen 
            und wichtige Kompetenzen zu fördern.
          </p>
        </div>
        
        <div class="goals-grid grid grid-3">
          <div class="goal-card card">
            <div class="goal-icon">🧠</div>
            <h3>KI-Kompetenzen</h3>
            <p>Verstehen, Anwenden, Gestalten und Reflektieren von KI-Technologien</p>
          </div>
          <div class="goal-card card">
            <div class="goal-icon">🔬</div>
            <h3>Entdeckendes Lernen</h3>
            <p>Förderung von <em>Inquiry-Based Learning</em> und forschendem Lernen</p>
          </div>
          <div class="goal-card card">
            <div class="goal-icon">⚗️</div>
            <h3>MINT-Kompetenzen</h3>
            <p>Vermittlung von MINT- und Forschungskompetenzen durch praktische Projekte</p>
          </div>
          <div class="goal-card card">
            <div class="goal-icon">🤝</div>
            <h3>Gendergerechtigkeit</h3>
            <p>Gezielte Förderung von Mädchen und Diversität in der Technik</p>
          </div>
          <div class="goal-card card">
            <div class="goal-icon">🌐</div>
            <h3>Regionale Vernetzung</h3>
            <p>Verbindung zwischen Schulen, Forschung und Wirtschaft</p>
          </div>
          <div class="goal-card card">
            <div class="goal-icon">🎯</div>
            <h3>UN-SDGs</h3>
            <p>Beitrag zu den UN-Nachhaltigkeitszielen 4, 5 und 10</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Modules Section -->
    <section id="modules" class="section">
      <div class="container">
        <div class="section-header">
          <h2>Pädagogisches Konzept</h2>
          <p class="section-description">
            Das Projekt setzt auf drei altersgerechte Forschungsreisen mit verschiedenen Modulen, 
            die durch Experimentieren, Spielen und Kreativarbeit gestaltet sind.
          </p>
        </div>

        <div class="modules-tabs">
          <div class="tab-buttons">
            <button 
              v-for="(level, index) in schoolLevels" 
              :key="level.name"
              @click="activeTab = index"
              :class="['tab-btn', { active: activeTab === index }]"
            >
              {{ level.name }}
            </button>
          </div>
          
          <div class="tab-content">
            <div v-for="(level, index) in schoolLevels" :key="level.name" v-show="activeTab === index">
              <div class="modules-grid grid grid-2">
                <div v-for="module in level.modules" :key="module.name" class="module-card card">
                  <h4>{{ module.name }}</h4>
                  <p class="module-partner">{{ module.partner }}</p>
                  <p class="module-description">{{ module.description }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="kiwi-day">
          <div class="kiwi-day-content">
            <h3>KIWi-Tag am Campus Hagenberg</h3>
            <p>
              Am Ende jeder Lernreise steht der <strong>KIWi-Tag</strong> am Campus Hagenberg, 
              an dem Schüler*innen ihre Ergebnisse präsentieren, von Unternehmen lernen und 
              Einblicke in Forschung und Wirtschaft erhalten.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section">
      <div class="container">
        <div class="section-header">
          <h2>Projektüberblick</h2>
          <p class="section-description">
            KIWi ist ein gemeinsames Bildungsprojekt des Softwarepark Hagenberg (SWPH), 
            das Künstliche Intelligenz kindgerecht in Schulen bringt.
          </p>
        </div>
        
        <div class="project-stats grid grid-4">
          <div class="stat-card card">
            <div class="stat-number">26</div>
            <div class="stat-label">Monate Laufzeit</div>
          </div>
          <div class="stat-card card">
            <div class="stat-number">€122.439</div>
            <div class="stat-label">Gesamtkosten</div>
          </div>
          <div class="stat-card card">
            <div class="stat-number">100%</div>
            <div class="stat-label">Förderquote</div>
          </div>
          <div class="stat-card card">
            <div class="stat-number">8</div>
            <div class="stat-label">Beteiligte Schulen</div>
          </div>
        </div>

        <div class="project-details">
          <div class="detail-item">
            <h4>Förderprogramm</h4>
            <p>FFG <em>Talente Regional 2024</em></p>
          </div>
          <div class="detail-item">
            <h4>Projektleitung</h4>
            <p>FH Oberösterreich Forschungs- & Entwicklungs GmbH, Campus Hagenberg</p>
          </div>
          <div class="detail-item">
            <h4>Fördergeber</h4>
            <p>FFG – Österreichische Forschungsförderungsgesellschaft</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Partners Section -->
    <section id="partners" class="section section-alt">
      <div class="container">
        <div class="section-header">
          <h2>Konsortium</h2>
          <p class="section-description">
            Ein starkes Netzwerk aus Forschung, Bildung und Wirtschaft arbeitet gemeinsam 
            an der Zukunft der KI-Bildung.
          </p>
        </div>

        <div class="partners-grid">
          <div class="partner-category">
            <h3>Forschung & Bildung</h3>
            <div class="partner-list">
              <div class="partner-item">
                <div class="partner-logo">🏛️</div>
                <div class="partner-info">
                  <div class="partner-name">FH Oberösterreich, Campus Hagenberg</div>
                  <div class="partner-role">(Projektleitung)</div>
                </div>
              </div>
              <div class="partner-item">
                <div class="partner-logo">🔬</div>
                <div class="partner-info">
                  <div class="partner-name">RISC Software GmbH</div>
                </div>
              </div>
              <div class="partner-item">
                <div class="partner-logo">💻</div>
                <div class="partner-info">
                  <div class="partner-name">Software Competence Center Hagenberg (SCCH)</div>
                </div>
              </div>
            </div>
          </div>
          
          <div class="partner-category">
            <h3>Unternehmen</h3>
            <div class="partner-list">
              <div class="partner-item">
                <div class="partner-logo">📱</div>
                <div class="partner-info">
                  <div class="partner-name">bluesource – mobile solutions gmbh</div>
                </div>
              </div>
              <div class="partner-item">
                <div class="partner-logo">🚗</div>
                <div class="partner-info">
                  <div class="partner-name">Porsche Informatik GmbH</div>
                </div>
              </div>
              <div class="partner-item">
                <div class="partner-logo">🥽</div>
                <div class="partner-info">
                  <div class="partner-name">Rise2Reality e.U.</div>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <div class="schools-section">
          <h3>Beteiligte Schulen</h3>
          <div class="schools-grid">
            <div class="school-item">VS Hagenberg</div>
            <div class="school-item">VS Pregarten</div>
            <div class="school-item">VS Wartberg ob der Aist</div>
            <div class="school-item">MS Pregarten</div>
            <div class="school-item">BG/BRG Freistadt</div>
            <div class="school-item">BORG Hagenberg</div>
            <div class="school-item">ABZ Hagenberg</div>
            <div class="school-item">Bischöfliches Gymnasium Petrinum Linz</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Benefits Section -->
    <section class="section">
      <div class="container">
        <div class="section-header">
          <h2>Nutzen</h2>
          <p class="section-description">
            KIWi schafft Mehrwert für alle Beteiligten und die gesamte Region.
          </p>
        </div>

        <div class="benefits-grid grid grid-3">
          <div class="benefit-card card">
            <h3>Für Schüler*innen</h3>
            <ul>
              <li>Verständnis und kritische Reflexion von KI</li>
              <li>Motivation für MINT-Berufe und Forschung</li>
              <li>Stärkung sozialer und methodischer Kompetenzen</li>
              <li>Praxisnahe Einblicke in regionale Unternehmen</li>
            </ul>
          </div>
          
          <div class="benefit-card card">
            <h3>Für Pädagog*innen</h3>
            <ul>
              <li>Zugang zu didaktisch aufbereiteten Lehrmaterialien</li>
              <li>Unterstützung bei der Einbindung von KI in den Unterricht</li>
              <li>Kooperation mit F&E-Expert*innen</li>
              <li>Regionale Vernetzung</li>
            </ul>
          </div>
          
          <div class="benefit-card card">
            <h3>Für die Region</h3>
            <ul>
              <li>Förderung technologischer Bildung im Mühlviertel</li>
              <li>Sichtbarkeit des Softwarepark Hagenberg</li>
              <li>Nachhaltige Verankerung von Forschung und Wirtschaft</li>
              <li>Innovationsstandort stärken</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- Funding Section -->
    <section class="section section-alt">
      <div class="container">
        <div class="funding-content">
          <h2>Förderung & Kooperationszuschüsse</h2>
          <div class="funding-grid grid grid-2">
            <div class="funding-card card">
              <h3>FFG-Förderung</h3>
              <p>
                Gefördert durch die <strong>FFG</strong> im Rahmen der Ausschreibung 
                <em>Talente Regional 2024</em> mit einer Förderquote von 100% der 
                anerkannten Projektkosten.
              </p>
            </div>
            <div class="funding-card card">
              <h3>Kooperationszuschüsse</h3>
              <p>
                KIWi stellt <strong>10 Zuschüsse à €1.000</strong> für weitere Schulen bereit. 
                Diese können für Projekthardware, KI-Tool-Lizenzen, Exkursionen oder 
                Expert*innen-Vorträge genutzt werden.
              </p>
              <a href="#contact" class="btn btn-secondary">Jetzt bewerben</a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section">
      <div class="container">
        <div class="section-header">
          <h2>Kontakt</h2>
          <p class="section-description">
            Haben Sie Fragen oder möchten Sie Teil des KIWi-Netzwerks werden? 
            Kontaktieren Sie uns!
          </p>
        </div>

        <div class="contact-content">
          <div class="contact-info card">
            <h3>Projektleitung</h3>
            <div class="contact-details">
              <p><strong>FH Oberösterreich Forschungs- & Entwicklungs GmbH</strong></p>
              <p>Campus Hagenberg</p>
              <p><strong>Projektleiter:</strong> Samuel Zühlke, MSc</p>
              <p>
                <a href="mailto:samuel.zuehlke@fh-hagenberg.at" class="contact-link">
                  📧 samuel.zuehlke@fh-hagenberg.at
                </a>
              </p>
            </div>
          </div>
          
          <div class="funding-notice card">
            <h3>Förderhinweis</h3>
            <p>
              Dieses Projekt wird im Rahmen der FFG-Ausschreibung 
              <em>Talente Regional 2024</em> aus Mitteln der Republik Österreich gefördert.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="footer-logo">
            <img src="/kiwi_logo.svg" alt="KIWi Logo" class="footer-logo-img">
            <span class="footer-logo-text">KIWi</span>
          </div>
          <div class="footer-info">
            <p>&copy; 2025 KIWi – KI & Wissenschaft. Alle Rechte vorbehalten.</p>
            <p>Gefördert durch die FFG im Rahmen von Talente Regional 2024.</p>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      activeTab: 0,
      headerColor: this.getRandomHeaderColor(),
      schoolLevels: [
        {
          name: 'Volksschule',
          modules: [
            {
              name: 'Detektiv*innen der KI',
              partner: 'FH OÖ',
              description: 'Spielerisches Entdecken von KI-Grundlagen durch Detektivarbeit'
            },
            {
              name: 'KI oder Ich? Wer hat recht?',
              partner: 'Porsche Informatik',
              description: 'Kritisches Denken über KI-Entscheidungen entwickeln'
            },
            {
              name: 'KI-Geschichten- & Märchenwerkstatt',
              partner: 'RISC',
              description: 'Kreatives Schreiben mit KI-Unterstützung'
            }
          ]
        },
        {
          name: 'Sekundarstufe I',
          modules: [
            {
              name: 'Wie KI dich sieht',
              partner: 'FH OÖ',
              description: 'Verstehen von KI-Bilderkennung und -interpretation'
            },
            {
              name: 'KI-Baumblätterkenner',
              partner: 'RISC',
              description: 'Praktische Anwendung von KI in der Naturerkundung'
            },
            {
              name: 'Was kann KI?',
              partner: 'Rise2Reality',
              description: 'Erkundung der Möglichkeiten und Grenzen von KI'
            },
            {
              name: 'Entdecke das Potenzial von KI',
              partner: 'SCCH',
              description: 'Forschungsnahe Einblicke in KI-Technologien'
            }
          ]
        },
        {
          name: 'Sekundarstufe II',
          modules: [
            {
              name: 'DataDrive',
              partner: 'Bluesource',
              description: 'Datenanalyse und -visualisierung mit KI-Tools'
            },
            {
              name: 'Think Twice: Deepfake & Bias in der KI',
              partner: 'FH OÖ',
              description: 'Kritische Auseinandersetzung mit KI-Ethik und -Risiken'
            },
            {
              name: 'Forschung steckt an',
              partner: 'FH OÖ',
              description: 'Einblicke in aktuelle KI-Forschung und -Entwicklung'
            }
          ]
        }
      ]
    }
  },
  methods: {
    getRandomHeaderColor() {
      const colors = ['var(--kiwi-purple)', 'var(--kiwi-green)', 'var(--kiwi-light-green)'];
      return colors[Math.floor(Math.random() * colors.length)];
    }
  }
}
</script>

<style scoped>
/* Header Styles */
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--kiwi-gray-200);
  z-index: 1000;
}

.nav-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.logo-img {
  height: 40px;
  width: auto;
}


.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-link {
  color: var(--kiwi-dark);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: var(--kiwi-purple);
}

/* Hero Styles */
.hero {
  background: linear-gradient(135deg, var(--kiwi-light-green) 0%, var(--kiwi-white) 100%);
  padding: 8rem 0 4rem;
  min-height: 100vh;
  display: flex;
  align-items: center;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.hero-title {
  margin-bottom: 1.5rem;
}

.text-gradient {
  background: linear-gradient(135deg, var(--kiwi-purple), var(--kiwi-green));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-description {
  font-size: 1.25rem;
  margin-bottom: 2rem;
  color: var(--kiwi-gray-600);
}

.hero-buttons {
  display: flex;
  gap: 1rem;
}

.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.hero-icon {
  width: 300px;
  height: auto;
  animation: float 3s ease-in-out infinite;
}

@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-20px); }
}

/* Section Styles */
.section-header {
  text-align: center;
  margin-bottom: 3rem;
}

.section-description {
  font-size: 1.25rem;
  color: var(--kiwi-gray-600);
  max-width: 800px;
  margin: 0 auto;
}

/* Stats Styles */
.stat-card {
  text-align: center;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--kiwi-purple);
  margin-bottom: 0.5rem;
}

.stat-label {
  color: var(--kiwi-gray-600);
  font-weight: 500;
}

/* Project Details */
.project-details {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.detail-item h4 {
  color: var(--kiwi-purple);
  margin-bottom: 0.5rem;
}

/* Goals Styles */
.goal-card {
  text-align: center;
}

.goal-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

/* Modules Styles */
.modules-tabs {
  margin-bottom: 3rem;
}

.tab-buttons {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 2rem;
}

.tab-btn {
  padding: 0.75rem 1.5rem;
  border: 2px solid var(--kiwi-gray-300);
  background: var(--kiwi-white);
  color: var(--kiwi-gray-600);
  border-radius: 0.5rem;
  cursor: pointer;
  transition: all 0.3s ease;
}

.tab-btn.active {
  border-color: var(--kiwi-purple);
  background: var(--kiwi-purple);
  color: var(--kiwi-white);
}

.module-card h4 {
  color: var(--kiwi-purple);
  margin-bottom: 0.5rem;
}

.module-partner {
  color: var(--kiwi-green);
  font-weight: 500;
  margin-bottom: 1rem;
}

.module-description {
  color: var(--kiwi-gray-600);
}

/* KIWi Day */
.kiwi-day {
  background: linear-gradient(135deg, var(--kiwi-purple), var(--kiwi-purple-alt));
  color: var(--kiwi-white);
  padding: 3rem;
  border-radius: 1rem;
  text-align: center;
}

.kiwi-day h3 {
  margin-bottom: 1rem;
}

/* Partners Styles */
.partners-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 3rem;
  margin-bottom: 3rem;
}

.partner-category h3 {
  color: var(--kiwi-purple);
  margin-bottom: 1.5rem;
  text-align: center;
}

.partner-list {
  display: grid;
  gap: 1rem;
}

.partner-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
  background: var(--kiwi-white);
  border-radius: 0.5rem;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.partner-logo {
  font-size: 2rem;
  width: 60px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--kiwi-gray-100);
  border-radius: 0.5rem;
  flex-shrink: 0;
}

.partner-info {
  flex: 1;
}

.partner-name {
  font-weight: 500;
  margin-bottom: 0.25rem;
}

.partner-role {
  font-size: 0.875rem;
  color: var(--kiwi-gray-600);
  font-style: italic;
}

/* Schools Styles */
.schools-section {
  background: var(--kiwi-white);
  padding: 2rem;
  border-radius: 1rem;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.schools-section h3 {
  color: var(--kiwi-purple);
  margin-bottom: 1.5rem;
  text-align: center;
}

.schools-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
}

.school-item {
  padding: 0.75rem 1rem;
  background: var(--kiwi-gray-50);
  border-radius: 0.5rem;
  text-align: center;
  font-weight: 500;
  border: 2px solid transparent;
  transition: all 0.3s ease;
}

.school-item:hover {
  border-color: var(--kiwi-green);
  background: var(--kiwi-light-green);
}

/* Benefits Styles */
.benefit-card ul {
  list-style: none;
  padding: 0;
}

.benefit-card li {
  padding: 0.5rem 0;
  border-bottom: 1px solid var(--kiwi-gray-200);
}

.benefit-card li:last-child {
  border-bottom: none;
}

.benefit-card li::before {
  content: "✓";
  color: var(--kiwi-green);
  font-weight: bold;
  margin-right: 0.5rem;
}

/* Funding Styles */
.funding-grid {
  margin-top: 2rem;
}

.funding-card h3 {
  color: var(--kiwi-purple);
  margin-bottom: 1rem;
}

/* Contact Styles */
.contact-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 2rem;
}

.contact-info h3 {
  color: var(--kiwi-purple);
  margin-bottom: 1.5rem;
}

.contact-details p {
  margin-bottom: 0.5rem;
}

.contact-link {
  color: var(--kiwi-purple);
  text-decoration: none;
}

.contact-link:hover {
  text-decoration: underline;
}

.funding-notice h3 {
  color: var(--kiwi-green);
  margin-bottom: 1rem;
}

/* Footer Styles */
.footer {
  background: var(--kiwi-dark);
  color: var(--kiwi-white);
  padding: 2rem 0;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.footer-logo-img {
  height: 30px;
  width: auto;
  filter: brightness(0) invert(1);
}

.footer-logo-text {
  font-size: 1.25rem;
  font-weight: 700;
}

.footer-info {
  text-align: right;
}

.footer-info p {
  margin-bottom: 0.25rem;
  font-size: 0.875rem;
  color: var(--kiwi-gray-300);
}

/* Responsive Design */
@media (max-width: 768px) {
  .nav-links {
    display: none;
  }
  
  .hero-content {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .hero-buttons {
    justify-content: center;
  }
  
  .hero-icon {
    width: 200px;
  }
  
  .tab-buttons {
    flex-direction: column;
    align-items: center;
  }
  
  .contact-content {
    grid-template-columns: 1fr;
  }
  
  .footer-content {
    flex-direction: column;
    gap: 1rem;
    text-align: center;
  }
  
  .footer-info {
    text-align: center;
  }
}

@media (max-width: 480px) {
  .hero {
    padding: 6rem 0 2rem;
  }
  
  .hero-buttons {
    flex-direction: column;
  }
  
  .project-details {
    grid-template-columns: 1fr;
  }
  
  .partners-grid {
    grid-template-columns: 1fr;
  }
}
</style>
