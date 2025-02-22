<script>
  import { onMount } from 'svelte';
  import "$lib/css/global.css";

  let darkMode = false;
  let isMenuOpen = false;

  onMount(() => {
    darkMode = localStorage.getItem("darkMode") === "true";
    document.body.classList.toggle("dark-mode", darkMode);
  });

  function toggleDarkMode() {
    darkMode = !darkMode;
    document.body.classList.toggle("dark-mode", darkMode);
    localStorage.setItem("darkMode", darkMode);
  }

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
</script>

<nav class="navbar">
  <a href="/" class="logo">TechConf</a>
  <button class="menu-toggle" on:click={toggleMenu}>
    {isMenuOpen ? "✖" : "☰"}
  </button>
  <ul class="nav-links {isMenuOpen ? 'show' : ''}">
    <li><a href="/">Home</a></li>  <!-- Home Link Added -->
    <li><a href="/speakers">Speakers</a></li>
    <li><a href="/schedule">Schedule</a></li>
    <li><a href="/sponsors">Sponsors</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
  <button class="dark-mode-btn" on:click={toggleDarkMode}>
    {darkMode ? "☀️ Light Mode" : "🌙 Dark Mode"}
  </button>
</nav>

<slot />
