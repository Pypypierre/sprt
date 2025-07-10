<script lang="ts">
	import '../app.css';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" type="image/jpg" href="/favicon.jpg" />
	<link href="https://fonts.googleapis.com/css2?family=Cinzel&display=swap" rel="stylesheet">
	<title>Sprt</title>
</svelte:head>

<header class="w-full bg-black text-white px-6 py-4 flex items-center justify-between">
		<div class="md:ml-8 flex items-center lg:mr-12">
    		<img src="sprt_logo.png" alt="Logo" class="h-35 w-auto" />
  		</div>
		<nav class="hidden md:flex space-x-4 text-lm tracking-widest uppercase items-center mr-8 lg:mr-12"> 
			<a href="/" class="hover:text-yellow-400 transition">Le concept</a>
			<a href="/about" class="hover:text-yellow-400 transition">Nos valeurs</a>
			<a href="/about" class="hover:text-yellow-400 transition">Qui sommes nous</a>
			<a href="/about" class="hover:text-yellow-400 transition">Nous contacter</a>
			<span class="border-l border-gray-500 h-10 mx-4"></span>
    		<div class="flex items-center space-x-4">
    		  <a href="https://www.instagram.com/sprt.society/" target="_blank">
    		    <img src="/icons/insta.png" alt="Instagram" class="h-10 w-10" />
    		  </a>
    		  <a href="https://www.linkedin.com/company/sprt-society/" target="_blank">
    		    <img src="/icons/linkedin.png" alt="LinkedIn" class="h-10 w-10" />
    		  </a>
    		</div>
		</nav>

		<div class="md:hidden"> <!-- mobile menu -->
    		<!-- Ton bouton mobile ici -->
  		</div>
</header>

<main>
	{@render children()}
</main>

<footer>
	<p>&copy; 2025 My Site</p>
</footer>