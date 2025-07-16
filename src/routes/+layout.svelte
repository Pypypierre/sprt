<script lang="ts">
	import '../app.css';
	import { onMount } from 'svelte';
	import { goto } from '$app/navigation';
  	import { writable } from 'svelte/store';
	import Loader from '$lib/components/Loader.svelte';

	const scrolled = writable(false);
	const footerVisible = writable(false);
	const isFirstLoad = writable(true);

	async function scrollToValues(event: Event, sectionId: string) {
		event.preventDefault();
		await goto('/');
		const el = document.getElementById(sectionId);
		el?.scrollIntoView({ behavior: 'smooth' });
	}
	onMount(() => {
	const handleScroll = () => {
		scrolled.set(window.scrollY > 20);
	};

	const timer = setTimeout(() => {
      isFirstLoad.set(false);
    }, 1000);

	window.addEventListener('scroll', handleScroll);

	const footer = document.getElementById('footer');

	const observer = new IntersectionObserver(
		(entries) => {
		entries.forEach(entry => {
			footerVisible.set(entry.isIntersecting);
		});
		},
		{ threshold: 0.5 }
	);

	if (footer) {
		observer.observe(footer);
	}

	return () => {
		window.removeEventListener('scroll', handleScroll);
		if (footer) observer.unobserve(footer);
		clearTimeout(timer);
	};
	});
	let { children } = $props();
</script>

<Loader show={!!$isFirstLoad} />

<svelte:head>
	<link rel="icon" type="image/jpg" href="/favicon.jpg" />
	<link href="https://fonts.googleapis.com/css2?family=Cinzel&display=swap" rel="stylesheet">
	<title>Sprt</title>
</svelte:head>

{#if !$isFirstLoad}
	<header class="fixed top-0 left-0 w-full z-50 transition-colors duration-500 transition-opacity text-white px-6 py-4 flex items-center"
		class:bg-black={$scrolled}
	  	class:bg-transparent={!$scrolled}
		class:opacity-0={$footerVisible}
		class:opacity-100={!$footerVisible}
	>
		<div class="w-[90%] flex items-center justify-between mx-auto">
			<div class="flex items-center space-x-4">
				 <a href="/" class="block">
					<img src="sprt-logo.png" alt="Logo Sprt" class="h-32 w-auto" />
				</a>
			</div>
			<nav class="hidden laptop:flex space-x-4 text-lg tracking-widest font-bold uppercase items-center"> 
				<a href="/#concept" onclick={(event: Event) => scrollToValues(event, "concept")} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Le concept</a>
				<a href="/#values" onclick={(event: Event) => scrollToValues(event, "values")} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nos valeurs</a>
				<a href="/#who_we_are" onclick={(event: Event) => scrollToValues(event, "who_we_are")} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Qui sommes nous</a>
				<a href="/contact" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nous contacter</a>
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
			</div>
		</div>	
	</header>
{/if}

<main>
	{@render children()}
</main>

<footer id="footer" class="text-white px-6 py-4 flex flex-col items-center pb-5 pt-5">
	<div class="w-[90%] flex items-center justify-between mx-auto pb-10">
		<nav class="flex flex-wrap gap-x-8 gap-y-2 text-lg tracking-widest pt-10"> 
			<a href="/#concept" onclick={(event: Event) => scrollToValues(event, "concept")} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Le concept</a>
			<a href="/#values" onclick={(event: Event) => scrollToValues(event, "values")} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nos valeurs</a>
			<a href="/#who_we_are" onclick={(event: Event) => scrollToValues(event, "who_we_are")} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Qui sommes nous</a>
			<a href="/legal_notices" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Mentions légales</a>
			<a href="/downloads/FORMULAIRE-DE-RÉTRACTATION.pdf" target="_blank" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Se rétracter</a>
			<a href="/contact" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nous contacter</a>
		</nav>		
		<div class="flex items-center space-x-4">
			 <a href="/" class="block">
				<img src="sprt-logo.png" alt="Logo Sprt" class="h-32 w-auto object-contain" />
			</a>
		</div>
	</div>
	<div class="w-[95%] h-[1px] bg-[#F9B333] mb-4">
	  <p class="text-base text-center mt-2">
		SPRT 2025. All rights reserved.
	  </p>
	</div>
</footer>