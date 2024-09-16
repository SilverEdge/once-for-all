
<script>
    import { onMount } from 'svelte';

    onMount(() => {
        // Trigger the ESV Cross-Reference Tool script (app.html runs on window.load event, so rerun)
        window.dispatchEvent(new Event('esv-crossref.trigger-linkify'));
    });
</script>

<svelte:head>
   <title>Once For All</title>
</svelte:head>

<h1 class="logo"><a href="/">Once for All</a></h1>

<div class="ylogo"></div>

<nav class="navbar">
    <ul class="nav-links">
        <li><a href="/">Home</a></li>
        <li><a href="about">About</a></li>
        <li><a href="services">Services</a></li>
        <li><a href="contact">Contact</a></li>
    </ul>
</nav>


<slot></slot>

<style>
/* Reset styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
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
}


</style>