
<script>
    import { onMount } from 'svelte';
    import 'hamburgers/dist/hamburgers.css';

    onMount(() => {
        // Trigger the ESV Cross-Reference Tool script (app.html runs on window.load event, so rerun)
        window.dispatchEvent(new Event('esv-crossref.trigger-linkify'));
    });

    let isMenuActive = false;
</script>

<svelte:head>
   <title>Once For All</title>
</svelte:head>

<h1 class="logo"><a href="/">Once for All</a></h1>

<div class="ylogo"></div>

<div class="fixednavbar"></div>

<nav class="navbar">
    <ul class="nav-links">
        <li><a href="/">Home</a></li>
        <li><a href="posts">Posts</a></li>
        <li><a href="about">About</a></li>
        <li><a href="contact">Contact</a></li>
    </ul>
</nav>

<button class="{isMenuActive ? 'hamburger hamburger--squeeze is-active' : 'hamburger hamburger--squeeze'}" type="button" on:click={() =>isMenuActive = !isMenuActive}>
    <span class="hamburger-box">
      <span class="hamburger-inner"></span>
    </span>
  </button>

<div ></div>
<!-- Side menu that slides in from the left -->
<div class="{isMenuActive ? 'menu-vert open' : 'menu-vert'}">
    <br>
    <br>
    <ul>
      <li><a href="/" on:click={() =>isMenuActive = !isMenuActive}>Home</a></li>
      <li><a href="/about" on:click={() =>isMenuActive = !isMenuActive}>About</a></li>
      <li><a href="/" on:click={() =>isMenuActive = !isMenuActive}>Services</a></li>
      <li><a href="/" on:click={() =>isMenuActive = !isMenuActive}>Contact</a></li>
    </ul>
  </div>

<slot></slot>

<style>

/* Reset styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.hamburger {
    position: fixed;
    top:16px;
    right:50px;
    z-index: 2;
    visibility: hidden;
}

.hamburger:hover{
    opacity: 1;
}

.hamburger-inner, .hamburger-inner::before, .hamburger-inner::after{
    background-color: white !important;
}
.hamburger-inner, .hamburger-inner::before, .hamburger-inner::after{
    background-color: white !important;
}

.logo {
    position: fixed;
    top:13px;
    left:40px;
    opacity: 95%;
    cursor: pointer;
    z-index: 2;
}

.logo a {
    color: white;
    text-decoration: none;
}

.logo:hover {
    opacity: 100%;
}

.ylogo:hover {
    opacity: 100%;
}

.ylogo {
    position: fixed;
    top:18px;
    right:40px;
    opacity: 50%;
    cursor: pointer;
    height: 50px;
    width: 100px;
    background-size: contain;
    background-repeat: no-repeat;
    z-index: 2;
    background-image: url('../yt_logo_mono_dark.png');
}

.navbar {
    background-color: #333;
    padding: 12px 0;
    font-family: Arial, sans-serif;
    position: fixed;
    width: 100%;
    z-index: 1;
}

.fixednavbar {
    background-color: #333;
    font-family: Arial, sans-serif;
    position: fixed;
    width: 100%;
    z-index: 1;
    height:60px;
}

.nav-links {
    display: flex;
    justify-content: center; /* Center the links horizontally */
    list-style: none; /* Remove default list styling */
}

.nav-links li {
    margin: 0 15px; /* Space between each link */
}

.nav-links a {
    display: block;
    color: white;
    text-decoration: none;
    padding: 10px 20px;
    background-color: #444;
    border-radius: 4px;
    transition: background-color 0.3s; /* Smooth transition for hover effect */
}

.nav-links a:hover {
    background-color: #555;
}

 /* Basic styling */
 .menu-vert {
    position: fixed;
    top: 0;
    left: -260px; /* Hidden off-screen */
    width: 260px;
    height: 100%;
    background-color: #333;
    color: white;
    transition: left 0.3s ease; /* Smooth slide effect */
    padding: 20px;
    z-index: 1;
  }

  /* Menu visible when menuOpen is true */
  .menu-vert.open {
    left: 0; /* Slide in the menu */
  }

  .menu-vert ul {
    list-style: none;
    padding: 0;
  }

  .menu-vert ul li {
    padding: 15px 0;
    border-bottom: 1px solid #444;
  }

  .menu-vert ul li a {
    color: white;
    text-decoration: none;
  }

@media (max-width: 768px) {
    .nav-links {
        flex-direction: column; /* Stack links vertically on smaller screens */
    }

    .nav-links li {
        margin: 10px 0; /* Adjust spacing for vertical stack */
    }
    .navbar {
        visibility: hidden;
    }
    .hamburger {
        visibility:visible;
    }
    .ylogo{
        visibility: hidden;
    }
}

</style>