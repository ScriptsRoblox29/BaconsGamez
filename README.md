<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no"/>
<title>Bacons Gamez - Roblox Games Platform</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');
  :root {
    --color-bg-light: #f9f9f9;
    --color-bg-dark: #121212;
    --color-text-light: #222222;
    --color-text-dark: #eee;
    --color-accent: #FF6F61;
    --color-accent-light: #FF8A78;
    --color-accent-dark: #E05B4F;
    --color-white: #fff;
    --color-gray-light: #bbb;
    --color-gray-dark: #444;
    --color-gray-muted: #888;
  }

  body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    background-color: var(--color-bg-dark);
    color: var(--color-text-dark);
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    max-width: 350px;
    margin-left: auto;
    margin-right: auto;
    user-select: none;
    transition: background-color 0.3s, color 0.3s;
  }
  header {
    text-align: center;
    padding: 12px 0 14px 0;
    font-weight: 700;
    font-size: 1.8rem;
    color: var(--color-accent);
    letter-spacing: 2px;
    user-select: none;
  }
  nav {
    display: flex;
    justify-content: space-around;
    background: var(--color-bg-dark);
    border-bottom: 1px solid var(--color-gray-dark);
  }
  nav button {
    background: none;
    border: none;
    padding: 14px 8px;
    font-weight: 600;
    font-size: 1rem;
    color: var(--color-text-dark);
    cursor: pointer;
    transition: color 0.3s ease;
    user-select: none;
    white-space: nowrap;
  }
  nav button.active,
  nav button:hover {
    color: var(--color-accent);
    border-bottom: 3px solid var(--color-accent);
  }

  /* Sections */
  section {
    flex: 1 1 auto;
    overflow-y: auto;
    padding: 14px 12px 24px 12px;
    animation: fadeIn 0.5s ease forwards;
    outline: none;
  }
  @keyframes fadeIn {
    from {opacity: 0; transform: translateY(10px);}
    to {opacity: 1; transform: translateY(0);}
  }

  /* Games Section */
  .games-list {
    display: flex;
    flex-direction: column;
    gap: 18px;
  }
  .game-card {
    background-color: var(--color-gray-dark);
    border-radius: 18px;
    overflow: hidden;
    box-shadow: 0 5px 14px rgba(0,0,0,0.6);
    cursor: pointer;
    transition: transform 0.3s cubic-bezier(.4,0,.2,1), box-shadow 0.3s ease;
    user-select: none;
    text-decoration: none;
    color: inherit;
    display: flex;
    flex-direction: column;
  }
  .game-card:hover,
  .game-card:focus {
    transform: scale(1.06) translateY(-6px);
    box-shadow: 0 12px 24px rgba(255,111,97,0.8);
    outline: none;
  }
  .game-image {
    width: 100%;
    aspect-ratio: 16 / 9;
    object-fit: cover;
    display: block;
    border-bottom: 3px solid var(--color-accent);
    transition: transform 0.6s ease;
  }
  .game-card:hover .game-image,
  .game-card:focus .game-image {
    transform: scale(1.08);
  }
  .game-info {
    padding: 14px 20px;
    color: var(--color-white);
    font-size: 1.2rem;
    font-weight: 700;
    letter-spacing: 0.7px;
    user-select: none;
  }

  /* About Us Section */
  .about-text {
    white-space: pre-wrap;
    color: var(--color-white);
    font-size: 1rem;
    line-height: 1.5;
    letter-spacing: 0.3px;
    max-width: 100%;
  }

  /* Talk To Us Section */
  .talk-container {
    display: flex;
    flex-direction: column;
    gap: 14px;
    -webkit-user-select: text;
  }
  .talk-header {
    color: var(--color-white);
    font-size: 1.65rem;
    font-weight: 700;
    user-select: text;
  }
  label {
    color: var(--color-white);
    font-weight: 600;
    margin-bottom: 4px;
  }
  select, textarea {
    border-radius: 8px;
    border: none;
    padding: 12px 14px;
    font-size: 1rem;
    font-family: 'Poppins', sans-serif;
  }
  select {
    background-color: var(--color-bg-dark);
    color: var(--color-text-dark);
    box-shadow: inset 0 0 6px rgba(255,255,255,0.12);
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
  }
  textarea {
    resize: vertical;
    min-height: 120px;
    max-height: 180px;
    background-color: var(--color-bg-dark);
    color: var(--color-white);
    box-shadow: inset 0 0 8px rgba(255,255,255,0.18);
  }

  button.send-btn {
    align-self: start;
    background-color: var(--color-white);
    color: var(--color-bg-dark);
    border: none;
    font-weight: 700;
    font-size: 1.1rem;
    padding: 14px 36px;
    border-radius: 40px;
    cursor: pointer;
    transition: background-color 0.25s ease, color 0.25s ease;
    user-select: none;
  }
  button.send-btn:disabled {
    background-color: var(--color-gray-dark);
    color: var(--color-gray-light);
    cursor: not-allowed;
  }
  button.send-btn:hover:not(:disabled) {
    background-color: var(--color-accent-light);
    color: var(--color-white);
  }

  /* Small gray disclaimer text below Talk to Us form */
  .disclaimer-text {
    font-size: 0.65rem;
    color: var(--color-gray-muted);
    margin-top: 12px;
    line-height: 1.3;
    user-select: text;
  }
  .disclaimer-text strong {
    color: var(--color-gray-light);
  }

  /* Rules Section */
  .rules-content {
    color: var(--color-white);
    font-size: 0.9rem;
    line-height: 1.5;
  }
  .rules-content ul {
    margin-left: 20px;
    margin-top: 10px;
  }
  .rules-content li {
    margin-bottom: 6px;
  }

  /* Privacy Section */
  .privacy-content {
    color: var(--color-white);
    font-size: 0.95rem;
    line-height: 1.6;
  }
  .privacy-content h3 {
    color: var(--color-accent);
    margin-bottom: 8px;
  }
  .privacy-content p {
    margin-bottom: 12px;
  }

  /* Settings Section */
  .settings-container {
    padding: 10px 6px;
    color: var(--color-white);
    font-size: 1rem;
  }
  .setting-row {
    margin-bottom: 20px;
  }
  label.setting-label {
    font-weight: 600;
    margin-right: 10px;
  }
  select.setting-select {
    font-size: 1rem;
    border-radius: 8px;
    padding: 8px 12px;
    border: none;
    background-color: var(--color-bg-dark);
    color: var(--color-text-dark);
    box-shadow: inset 0 0 6px rgba(255,255,255,0.16);
  }

  /* Dark and Light mode styles */
  body.light {
    background-color: var(--color-bg-light);
    color: var(--color-text-light);
  }
  body.light nav {
    background: var(--color-bg-light);
    border-bottom: 1px solid var(--color-gray-light);
  }
  body.light nav button {
    color: var(--color-text-light);
  }
  body.light nav button.active,
  body.light nav button:hover {
    color: var(--color-accent);
    border-bottom: 3px solid var(--color-accent);
  }
  body.light .game-card {
    background-color: var(--color-gray-light);
    color: var(--color-text-light);
    box-shadow: 0 3px 10px rgba(0,0,0,0.1);
  }
  body.light .game-info {
    color: var(--color-text-light);
  }
  body.light .about-text {
    color: var(--color-text-light);
  }
  body.light .talk-header,
  body.light label,
  body.light .settings-container,
  body.light .rules-content,
  body.light .privacy-content,
  body.light .disclaimer-text {
    color: var(--color-text-light);
  }
  body.light select,
  body.light textarea,
  body.light .setting-select {
    background-color: var(--color-white);
    color: var(--color-text-light);
    box-shadow: inset 0 0 7px rgba(0,0,0,0.15);
  }
  body.light button.send-btn {
    background-color: var(--color-bg-dark);
    color: var(--color-white);
  }
  body.light button.send-btn:hover:not(:disabled) {
    background-color: var(--color-accent-dark);
  }

  /* Scrollbar styling */
  section::-webkit-scrollbar {
    width: 8px;
  }
  section::-webkit-scrollbar-thumb {
    background: var(--color-accent);
    border-radius: 4px;
  }
  /* Responsive tweaks */
  @media (max-width: 350px) {
    header {
      font-size: 1.6rem;
      padding: 10px 0 16px;
    }
    nav button {
      padding: 12px 8px;
      font-size: 1rem;
    }
    button.send-btn {
      font-size: 1rem;
      padding: 12px 28px;
    }
  }
</style>
</head>
<body>
<header id="header-title" tabindex="0">Bacons Gamez</header>
<nav role="navigation" aria-label="Primary navigation">
  <button class="tab-button active" data-tab="games" id="tab-games" aria-controls="games-section" aria-selected="true" role="tab">Games</button>
  <button class="tab-button" data-tab="about" id="tab-about" aria-controls="about-section" aria-selected="false" role="tab">About Us</button>
  <button class="tab-button" data-tab="talk" id="tab-talk" aria-controls="talk-section" aria-selected="false" role="tab">Talk to Us</button>
  <button class="tab-button" data-tab="rules" id="tab-rules" aria-controls="rules-section" aria-selected="false" role="tab">Rules</button>
  <button class="tab-button" data-tab="privacy" id="tab-privacy" aria-controls="privacy-section" aria-selected="false" role="tab">Privacy</button>
  <button class="tab-button" data-tab="settings" id="tab-settings" aria-controls="settings-section" aria-selected="false" role="tab">Settings</button>
</nav>

<div class="container" role="tabpanel" tabindex="0">
  <!-- Games Section -->
  <section id="games-section" class="tab-section" aria-label="Games Section" role="tabpanel" tabindex="0">
    <div class="games-list" id="games-list" aria-live="polite" aria-relevant="additions"></div>
  </section>

  <!-- About Section -->
  <section id="about-section" class="tab-section" style="display:none;" aria-label="About Us Section" role="tabpanel" tabindex="0">
    <p class="about-text" id="about-text" tabindex="0">
      I started creating games so that people could have fun. We began making games in 2022. At first, our games didn’t get much attention, so we created even more games to improve and grow. Our passion drives us to keep making engaging experiences for everyone to enjoy!
    </p>
  </section>

  <!-- Talk to Us Section -->
  <section id="talk-section" class="tab-section" style="display:none;" aria-label="Talk to Us Section" role="tabpanel" tabindex="0">
    <div class="talk-container">
      <div class="talk-header" id="talk-header" tabindex="0">Tell us what you want.</div>

      <label for="reason-select" id="label-reason">Choose a Reason</label>
      <select id="reason-select" aria-labelledby="label-reason" aria-required="true">
        <option value="" disabled selected>Select a reason</option>
        <option value="buy">Buy a game</option>
        <option value="feedback">Feedback</option>
        <option value="bug">Bug</option>
      </select>

      <label for="comments-textarea" id="label-comments">Comments</label>
      <textarea id="comments-textarea" placeholder="Enter your comments here..." aria-labelledby="label-comments" rows="4" required></textarea>

      <button class="send-btn" id="send-btn" aria-label="Send message" disabled>Send</button>

      <div class="disclaimer-text" aria-live="polite">
        After publishing the message, <strong>you agree with the rules.</strong>
      </div>
    </div>
  </section>

  <!-- Rules Section -->
  <section id="rules-section" class="tab-section" style="display:none;" aria-label="Rules Section" role="tabpanel" tabindex="0">
    <div class="rules-content" id="rules-content" tabindex="0">
      <h2>Rules</h2>
      <ul>
        <li>No exploits of any kind are allowed here.</li>
        <li>No messages breaking Roblox rules or violating them.</li>
        <li>No spam is permitted here.</li>
        <li>We do not accept people who turn our games into pay-to-win or break the game, or who cannot build, make UIs, or write code properly.</li>
        <li>Follow all Roblox rules.</li>
      </ul>
    </div>
  </section>

  <!-- Privacy Section -->
  <section id="privacy-section" class="tab-section" style="display:none;" aria-label="Privacy Section" role="tabpanel" tabindex="0">
    <div class="privacy-content" id="privacy-content" tabindex="0">
      <h2>Privacy Policy</h2>
      <p>We will never publish, share, or sell your data, passwords, or any personal information on the Internet.</p>
      <p>Our commitment to your privacy is absolute. All submitted information is treated with the utmost confidentiality.</p>
      <p>We do not store your data beyond what is necessary to send your message, and that is handled securely.</p>
      <p>Your trust is important to us, and we strictly adhere to privacy best practices to keep your information safe.</p>
      <p>If you have any concerns or questions about your privacy, please feel free to contact us.</p>
    </div>
  </section>

  <!-- Settings Section -->
  <section id="settings-section" class="tab-section" style="display:none;" aria-label="Settings Section" role="tabpanel" tabindex="0">
    <div class="settings-container">
      <div class="setting-row">
        <label for="mode-select" class="setting-label" id="label-mode">Theme Mode:</label>
        <select id="mode-select" class="setting-select" aria-labelledby="label-mode">
          <option value="dark" selected>Dark Mode</option>
          <option value="light">Light Mode</option>
          <option value="system">System</option>
        </select>
      </div>
      <div class="setting-row">
        <label for="language-select" class="setting-label" id="label-language">Language:</label>
        <select id="language-select" class="setting-select" aria-labelledby="label-language">
          <option value="en" selected>English</option>
          <option value="es">Spanish</option>
          <option value="pt">Portuguese</option>
        </select>
      </div>
    </div>
  </section>
</div>

<script>
  // Games data
  const gamesData = [
    {
      title: "Doors but classic",
      image: "https://tr.rbxcdn.com/6847aac179e04d8dc44e9647a28410ec/768/432/Image/Png",
      url: "https://www.roblox.com/games/100924853968864/Doors-but-classic",
    },
    {
      title: "Retro Menu - Explore and Play (WORKING)",
      image: "https://tr.rbxcdn.com/1e7a4549a461c36ee1116d3ee4f82ae4/768/432/Image/Png",
      url: "https://www.roblox.com/games/133671644438595/Retro-Menu-Explore-and-Play-WORKING",
    },
    {
      title: "Each Server Has an Owner",
      image: "https://tr.rbxcdn.com/41f6a2bba3c3cf0a0a034f8656807231/768/432/Image/Png",
      url: "https://www.roblox.com/games/74283855134306/each-server-has-an-owner",
    }
  ];

  // Translations dictionary including new pages rules & privacy
  const translations = {
    en: {
      header: "Bacons Gamez",
      tabs: { games: "Games", about: "About Us", talk: "Talk to Us", rules: "Rules", privacy: "Privacy", settings: "Settings" },
      aboutText: "I started creating games so that people could have fun. We began making games in 2022. At first, our games didn’t get much attention, so we created even more games to improve and grow. Our passion drives us to keep making engaging experiences for everyone to enjoy!",
      talkHeader: "Tell us what you want.",
      labelReason: "Choose a Reason",
      reasonOptions: { buy: "Buy a game", feedback: "Feedback", bug: "Bug" },
      labelComments: "Comments",
      sendButton: "Send",
      disclaimerText: "After publishing the message, you agree with the rules.",
      rulesTitle: "Rules",
      rulesList: [
        "No exploits of any kind are allowed here.",
        "No messages breaking Roblox rules or violating them.",
        "No spam is permitted here.",
        "We do not accept people who turn our games into pay-to-win or break the game, or who cannot build, make UIs, or write code properly.",
        "Follow all Roblox rules."
      ],
      privacyTitle: "Privacy Policy",
      privacyContent: [
        "We will never publish, share, or sell your data, passwords, or any personal information on the Internet.",
        "Our commitment to your privacy is absolute. All submitted information is treated with the utmost confidentiality.",
        "We do not store your data beyond what is necessary to send your message, and that is handled securely.",
        "Your trust is important to us, and we strictly adhere to privacy best practices to keep your information safe.",
        "If you have any concerns or questions about your privacy, please feel free to contact us."
      ],
      settings: {
        themeLabel: "Theme Mode:",
        themeDark: "Dark Mode",
        themeLight: "Light Mode",
        themeSystem: "System",
        languageLabel: "Language:",
        languageEnglish: "English",
        languageSpanish: "Spanish",
        languagePortuguese: "Portuguese"
      },
      alerts: {
        selectReason: "Please select a reason.",
        enterComments: "Please enter comments."
      }
    },
    es: {
      header: "Bacons Gamez",
      tabs: { games: "Juegos", about: "Sobre Nosotros", talk: "Contáctanos", rules: "Reglas", privacy: "Privacidad", settings: "Configuración" },
      aboutText: "Comencé a crear juegos para que la gente pudiera divertirse. Empezamos a hacer juegos en 2022. Al principio, nuestros juegos no tuvieron mucha atención, así que creamos aún más juegos para mejorar y crecer. ¡Nuestra pasión nos impulsa a seguir creando experiencias atractivas para que todos disfruten!",
      talkHeader: "Dinos lo que quieres.",
      labelReason: "Elige una razón",
      reasonOptions: { buy: "Comprar un juego", feedback: "Comentarios", bug: "Error" },
      labelComments: "Comentarios",
      sendButton: "Enviar",
      disclaimerText: "Después de publicar el mensaje, aceptas las reglas.",
      rulesTitle: "Reglas",
      rulesList: [
        "No se permiten exploits de ningún tipo aquí.",
        "No se permiten mensajes que rompan o violen las reglas de Roblox.",
        "No se permite spam aquí.",
        "No aceptamos personas que conviertan nuestros juegos en pay-to-win o rompan el juego, o que no puedan construir, hacer interfaces o escribir código correctamente.",
        "Sigue todas las reglas de Roblox."
      ],
      privacyTitle: "Política de Privacidad",
      privacyContent: [
        "Nunca publicaremos, compartiremos o venderemos tus datos, contraseñas o cualquier información personal en Internet.",
        "Nuestro compromiso con tu privacidad es absoluto. Toda la información enviada se trata con la máxima confidencialidad.",
        "No almacenamos tus datos más allá de lo necesario para enviar tu mensaje, y eso se maneja de forma segura.",
        "Tu confianza es importante para nosotros, y seguimos estrictamente las mejores prácticas de privacidad para mantener tu información segura.",
        "Si tienes alguna preocupación o pregunta sobre tu privacidad, no dudes en contactarnos."
      ],
      settings: {
        themeLabel: "Modo de tema:",
        themeDark: "Modo oscuro",
        themeLight: "Modo claro",
        themeSystem: "Sistema",
        languageLabel: "Idioma:",
        languageEnglish: "Inglés",
        languageSpanish: "Español",
        languagePortuguese: "Portugués"
      },
      alerts: {
        selectReason: "Por favor, selecciona una razón.",
        enterComments: "Por favor, ingresa comentarios."
      }
    },
    pt: {
      header: "Bacons Gamez",
      tabs: { games: "Jogos", about: "Sobre Nós", talk: "Fale Conosco", rules: "Regras", privacy: "Privacidade", settings: "Configurações" },
      aboutText: "Comecei a criar jogos para que as pessoas pudessem se divertir. Começamos a fazer jogos em 2022. No começo, nossos jogos não tiveram muita atenção, então criamos ainda mais jogos para melhorar e crescer. Nossa paixão nos impulsiona a continuar fazendo experiências envolventes para todos aproveitarem!",
      talkHeader: "Diga-nos o que você quer.",
      labelReason: "Escolha um motivo",
      reasonOptions: { buy: "Comprar um jogo", feedback: "Feedback", bug: "Bug" },
      labelComments: "Comentários",
      sendButton: "Enviar",
      disclaimerText: "Após publicar a mensagem, você concorda com as regras.",
      rulesTitle: "Regras",
      rulesList: [
        "Nenhum tipo de exploit é permitido aqui.",
        "Nenhuma m
