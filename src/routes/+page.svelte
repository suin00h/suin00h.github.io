<script>
  import { onMount } from 'svelte';
  
  let theme = 'dark';
  
  function toggleTheme() {
    theme = theme === 'dark' ? 'light' : 'dark';
  }
  
  // Smooth scroll to section
  function scrollToSection(id) {
    document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });
  }
</script>

<svelte:head>
  <title>Your Name - Digital Portfolio</title>
</svelte:head>

<div class="app" data-theme={theme}>
  <!-- Header -->
  <header>
    <div class="container">
      <div class="logo">
        <span class="icon">🎨</span>
        <span>Your Name</span>
      </div>
      <nav>
        <button on:click={() => scrollToSection('work')}>Works</button>
        <button on:click={() => scrollToSection('bio')}>Bio</button>
        <button on:click={() => scrollToSection('contact')}>Contact</button>
      </nav>
      <button class="theme-toggle" on:click={toggleTheme} aria-label="Toggle theme">
        {theme === 'dark' ? '☀️' : '🌙'}
      </button>
    </div>
  </header>

  <!-- Hero Section -->
  <section class="hero">
    <div class="container">
      <div class="hero-content">
        <!-- Placeholder for 3D character or illustration -->
        <div class="character">
          <div class="placeholder-char">
            👨‍💻
          </div>
        </div>
        
        <div class="intro-card">
          <p>Hello, I'm a developer based in [Your Location]!</p>
        </div>
        
        <h1>Your Name</h1>
        <p class="subtitle">Developer / Designer / Creator</p>
      </div>
    </div>
  </section>

  <!-- Work Section -->
  <section id="work" class="work">
    <div class="container">
      <h2>Work</h2>
      <div class="work-content">
        <img src="https://via.placeholder.com/100" alt="Profile" class="profile-pic" />
        <div class="work-description">
          <p>
            [Your Name] is a passionate developer based in [Location] with a focus on 
            building creative digital experiences. Skilled in [your key skills], 
            specializing in [your specialization].
          </p>
          <p>
            When not coding, you can find them [your hobbies/interests]. 
            Currently working on [current project].
          </p>
          <button class="cta-button">My portfolio →</button>
        </div>
      </div>
    </div>
  </section>

  <!-- Bio Section -->
  <section id="bio" class="bio">
    <div class="container">
      <h2>Bio</h2>
      <div class="timeline">
        <div class="timeline-item">
          <span class="year">2020</span>
          <span class="event">Started learning web development</span>
        </div>
        <div class="timeline-item">
          <span class="year">2021</span>
          <span class="event">First freelance project</span>
        </div>
        <div class="timeline-item">
          <span class="year">2023</span>
          <span class="event">Joined [Company Name]</span>
        </div>
        <div class="timeline-item">
          <span class="year">2024 to present</span>
          <span class="event">Building amazing products</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Interests Section -->
  <section class="interests">
    <div class="container">
      <h2>I ♥</h2>
      <p>Art, Music, Photography, Coffee, Open Source, Learning</p>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="contact">
    <div class="container">
      <h2>On the web</h2>
      <div class="links">
        <a href="https://github.com/yourusername" target="_blank">
          <span class="icon">💻</span> @yourusername
        </a>
        <a href="https://twitter.com/yourusername" target="_blank">
          <span class="icon">🐦</span> @yourusername
        </a>
        <a href="mailto:your@email.com">
          <span class="icon">✉️</span> your@email.com
        </a>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <div class="container">
      <p>© 2024 Your Name. All Rights Reserved.</p>
    </div>
  </footer>
</div>

<style>
  :global(body) {
    margin: 0;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  }

  .app {
    min-height: 100vh;
    transition: background-color 0.3s, color 0.3s;
  }

  .app[data-theme='dark'] {
    background-color: #202023;
    color: #ffffff;
  }

  .app[data-theme='light'] {
    background-color: #f0e7db;
    color: #000000;
  }

  .container {
    max-width: 700px;
    margin: 0 auto;
    padding: 0 20px;
  }

  /* Header */
  header {
    padding: 20px 0;
    position: sticky;
    top: 0;
    backdrop-filter: blur(10px);
    z-index: 100;
  }

  .app[data-theme='dark'] header {
    background-color: rgba(32, 32, 35, 0.8);
  }

  .app[data-theme='light'] header {
    background-color: rgba(240, 231, 219, 0.8);
  }

  header .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .logo {
    display: flex;
    align-items: center;
    gap: 8px;
    font-weight: bold;
    font-size: 18px;
  }

  nav {
    display: flex;
    gap: 20px;
  }

  nav button {
    background: none;
    border: none;
    color: inherit;
    cursor: pointer;
    font-size: 16px;
    padding: 8px 12px;
    border-radius: 6px;
    transition: background-color 0.2s;
  }

  nav button:hover {
    background-color: rgba(255, 255, 255, 0.1);
  }

  .theme-toggle {
    background: none;
    border: none;
    font-size: 24px;
    cursor: pointer;
    padding: 8px;
    border-radius: 8px;
    transition: background-color 0.2s;
  }

  .app[data-theme='dark'] .theme-toggle {
    background-color: #fbd38d;
  }

  .app[data-theme='light'] .theme-toggle {
    background-color: #4a5568;
  }

  /* Hero Section */
  .hero {
    padding: 60px 0;
    text-align: center;
  }

  .character {
    margin-bottom: 20px;
  }

  .placeholder-char {
    font-size: 120px;
    animation: float 3s ease-in-out infinite;
  }

  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-20px); }
  }

  .intro-card {
    display: inline-block;
    padding: 12px 20px;
    border-radius: 8px;
    margin-bottom: 20px;
  }

  .app[data-theme='dark'] .intro-card {
    background-color: #2d3748;
  }

  .app[data-theme='light'] .intro-card {
    background-color: #ffffff;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  }

  h1 {
    font-size: 36px;
    margin: 20px 0 10px;
  }

  .subtitle {
    font-size: 16px;
    opacity: 0.8;
  }

  /* Work Section */
  .work {
    padding: 40px 0;
  }

  h2 {
    font-size: 24px;
    margin-bottom: 30px;
    text-decoration: underline;
    text-decoration-thickness: 4px;
    text-underline-offset: 6px;
  }

  .work-content {
    display: flex;
    gap: 30px;
    align-items: flex-start;
  }

  .profile-pic {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  .work-description p {
    margin-bottom: 16px;
    line-height: 1.6;
  }

  .cta-button {
    padding: 10px 20px;
    border-radius: 6px;
    border: none;
    cursor: pointer;
    font-size: 16px;
    font-weight: 500;
    transition: transform 0.2s;
  }

  .app[data-theme='dark'] .cta-button {
    background-color: #81e6d9;
    color: #1a202c;
  }

  .app[data-theme='light'] .cta-button {
    background-color: #319795;
    color: #ffffff;
  }

  .cta-button:hover {
    transform: translateY(-2px);
  }

  /* Bio Section */
  .bio {
    padding: 40px 0;
  }

  .timeline {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .timeline-item {
    display: flex;
    gap: 20px;
  }

  .year {
    font-weight: bold;
    min-width: 120px;
  }

  /* Interests Section */
  .interests {
    padding: 40px 0;
  }

  .interests p {
    line-height: 1.8;
  }

  /* Contact Section */
  .contact {
    padding: 40px 0;
  }

  .links {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .links a {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 12px 16px;
    border-radius: 8px;
    text-decoration: none;
    color: inherit;
    transition: background-color 0.2s;
  }

  .app[data-theme='dark'] .links a:hover {
    background-color: rgba(255, 255, 255, 0.1);
  }

  .app[data-theme='light'] .links a:hover {
    background-color: rgba(0, 0, 0, 0.05);
  }

  /* Footer */
  footer {
    padding: 40px 0;
    text-align: center;
    opacity: 0.6;
    font-size: 14px;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .work-content {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }

    nav {
      display: none;
    }
  }
</style>