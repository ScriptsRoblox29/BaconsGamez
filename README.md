<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no"/>
<title>Bacons Gamez - Roblox Games Platform</title>
<link rel="stylesheet" href="styles.css" />
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
    <p class="about-text" id="about-text" tabindex="0"></p>
  </section>

  <!-- Talk to Us Section -->
  <section id="talk-section" class="tab-section" style="display:none;" aria-label="Talk to Us Section" role="tabpanel" tabindex="0">
    <div class="talk-container">
      <div class="talk-header" id="talk-header" tabindex="0"></div>

      <label for="reason-select" id="label-reason"></label>
      <select id="reason-select" aria-labelledby="label-reason" aria-required="true">
        <option value="" disabled selected>Select a reason</option>
        <option value="buy">Buy a game</option>
        <option value="feedback">Feedback</option>
        <option value="bug">Bug</option>
      </select>

      <label for="comments-textarea" id="label-comments"></label>
      <textarea id="comments-textarea" placeholder="Enter your comments here..." aria-labelledby="label-comments" rows="4" required></textarea>

      <button class="send-btn" id="send-btn" aria-label="Send message" disabled>Send</button>

      <div class="disclaimer-text" aria-live="polite"></div>
    </div>
  </section>

  <!-- Rules Section -->
  <section id="rules-section" class="tab-section" style="display:none;" aria-label="Rules Section" role="tabpanel" tabindex="0">
    <div class="rules-content" id="rules-content" tabindex="0"></div>
  </section>

  <!-- Privacy Section -->
  <section id="privacy-section" class="tab-section" style="display:none;" aria-label="Privacy Section" role="tabpanel" tabindex="0">
    <div class="privacy-content" id="privacy-content" tabindex="0"></div>
  </section>

  <!-- Settings Section -->
  <section id="settings-section" class="tab-section" style="display:none;" aria-label="Settings Section" role="tabpanel" tabindex="0">
    <div class="settings-container">
      <div class="setting-row">
        <label for="mode-select" class="setting-label" id="label-mode"></label>
        <select id="mode-select" class="setting-select" aria-labelledby="label-mode">
          <option value="dark" selected>Dark Mode</option>
          <option value="light">Light Mode</option>
          <option value="system">System</option>
        </select>
      </div>
      <div class="setting-row">
        <label for="language-select" class="setting-label" id="label-language"></label>
        <select id="language-select" class="setting-select" aria-labelledby="label-language">
          <option value="en" selected>English</option>
          <option value="es">Spanish</option>
          <option value="pt">Portuguese</option>
        </select>
      </div>
    </div>
  </section>
</div>

<script src="script.js"></script>
</body>
</html>
