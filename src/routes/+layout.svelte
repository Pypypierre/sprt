<script lang="ts">
	import '../app.css';
	import { onMount } from 'svelte';
  	import { writable } from 'svelte/store';

	const scrolled = writable(false);
	onMount(() => {
		const handleScroll = () => {
			scrolled.set(window.scrollY > 20);
		};

		window.addEventListener('scroll', handleScroll);
		return () => window.removeEventListener('scroll', handleScroll);
	});

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" type="image/jpg" href="/favicon.jpg" />
	<link href="https://fonts.googleapis.com/css2?family=Cinzel&display=swap" rel="stylesheet">
	<title>Sprt</title>
</svelte:head>

<header class="fixed top-0 left-0 w-full z-50 transition-colors duration-500 text-white px-6 py-4 flex items-center"
	class:bg-black={$scrolled}
  	class:bg-transparent={!$scrolled}
>
	<div class="w-[90%] flex items-center justify-between mx-auto">
		<div class="flex items-center space-x-4">
			 <a href="/" class="block">
				<img src="sprt-logo.png" alt="Logo Sprt" class="h-32 w-auto" />
			</a>
		</div>
		<nav class="hidden laptop:flex space-x-4 text-lg tracking-widest font-bold uppercase items-center"> 
			<a href="#concept" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Le concept</a>
			<a href="#values" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nos valeurs</a>
			<a href="#Who_we_are" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Qui sommes nous</a>
			<a href="#Contact" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nous contacter</a>
			<span class="border-l border-gray-500 h-13 mx-4"></span>
    		<div class="flex items-center space-x-4">
				<a href="https://www.instagram.com/sprt.society/" target="_blank">
					<img src="/icons/insta.png" alt="Instagram" class="h-12 w-12" />
				</a>
				<a href="https://www.linkedin.com/company/sprt-society/" target="_blank">
					<img src="/icons/linkedin.png" alt="LinkedIn" class="h-12 w-12" />
				</a>
    		</div>
		</nav>		
		<div class="tablet:hidden"> <!-- mobile menu -->
			<!-- Ton bouton mobile ici -->
		</div>
	</div>	
</header>

<main>
	{@render children()}
</main>

<footer class="text-white px-6 py-4 flex items-center">
	<div class="w-[90%] flex items-center justify-between mx-auto">
		<nav class="hidden laptop:flex flex-wrap gap-x-8 gap-y-2 text-lg tracking-widest"> 
			<a href="#concept" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Le concept</a>
			<a href="#values" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nos valeurs</a>
			<a href="#Who_we_are" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Qui sommes nous</a>
			<a href="#Contact" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nous contacter</a>
			<a href="/legal_notices" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Mentions légales</a>
			<a href="/downloads/FORMULAIRE-DE-RÉTRACTATION.pdf" target="_blank" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Se rétracter</a>
			<a href="policies" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Politiques</a>
		</nav>		
		<div class="flex items-center space-x-4">
			 <a href="/" class="block">
				<img src="sprt-logo.png" alt="Logo Sprt" class="h-32 w-auto" />
			</a>
		</div>
	</div>
</footer>