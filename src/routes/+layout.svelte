<script lang="ts">
	import '../app.css';
	import { onMount } from 'svelte';
	import { goto } from '$app/navigation';
  	import { writable } from 'svelte/store';
	import Loader from '$lib/components/Loader.svelte';

	const scrolled = writable(false);
	const footerVisible = writable(false);
	const isFirstLoad = writable(true);
  	
	const isOpen = writable(false);

	function toggleMobileMenu() {
	  isOpen.update(v => !v);
	}

	async function scrollToValues(event: Event, sectionId: string) {
		event.preventDefault();
		await goto('/');
		const el = document.getElementById(sectionId);
		el?.scrollIntoView({ behavior: 'smooth' });
	}

	function scrollToTop() {
    	window.scrollTo({ top: 0, behavior: 'smooth' });
	}

	onMount(() => {
	const handleScroll = () => {
		scrolled.set(window.scrollY > 20);
	};

	const timer = setTimeout(() => {
      isFirstLoad.set(false);
    }, 1000);

	handleScroll();
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

	$effect(() => {
		if ($isOpen) {
			document.body.style.overflow = 'hidden';
		} else {
			document.body.style.overflow = '';
		}
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
	<header class="bg-transparent mobile:fixed top-0 left-0 w-full z-50 laptop:transition-colors duration-500 transition-opacity text-white px-6 py-4 flex items-center"
		class:laptop:bg-black={$scrolled}
	  	class:laptop:bg-transparent={!$scrolled}
		class:opacity-0={$footerVisible}
		class:opacity-100={!$footerVisible}
	>
		<div class="w-[90%] flex items-center justify-between mx-auto">
			<div class="flex items-center space-x-4">
				 <a href="/" class="block">
					<img src="sprt-logo.png" alt="Logo Sprt" class="h-32 w-auto" />
				</a>
			</div>
			<nav class="hidden laptop:flex space-x-4 text-lg pl-5 tracking-widest font-bold uppercase items-center"> 
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
			<nav class="hidden tablet:flex laptop:hidden">
				<button
					class="flex flex-col justify-center items-center w-10 h-10 relative z-50"
					onclick={toggleMobileMenu}
					aria-label="Toggle menu"
				>
					<span class="block w-6 h-0.5 bg-white transition duration-300"
						class:rotate-45={$isOpen}
						class:translate-y-1.5={$isOpen}></span>
					<span class="block w-6 h-0.5 bg-white my-1 transition duration-300"
				    	class:opacity-0={$isOpen}></span>
					<span class="block w-6 h-0.5 bg-white transition duration-300"
						class:-rotate-45={$isOpen}
						class:-translate-y-1.5={$isOpen}></span>
				</button>
				<button
					type="button"
					aria-label="Close mobile menu overlay"
					class="fixed left-0 right-0 bottom-0 top-36 bg-black/50 backdrop-blur-sm z-40 transition-opacity duration-300"
					class:opacity-100={$isOpen}
					class:opacity-0={!$isOpen}
					class:pointer-events-auto={$isOpen}
					class:pointer-events-none={!$isOpen}
					onclick={() => $isOpen = false}
				></button>
				<div class="absolute flex items-center top-full right-6 mt-4 w-56 bg-[#181818] border border-yellow-400 rounded-lg shadow-lg flex flex-col space-y-4 py-4 px-6 text-right z-50 transform transition-all duration-300 origin-top-right"
					class:opacity-0={!$isOpen}
					class:pointer-events-none={!$isOpen}
					class:scale-100={$isOpen}
					class:opacity-100={$isOpen}
					class:pointer-events-auto={$isOpen}
				>
					<a href="/#concept" onclick={(event: Event) => {$isOpen = false; scrollToValues(event, "concept");}} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Le concept</a>
					<a href="/#values" onclick={(event: Event) => {$isOpen = false; scrollToValues(event, "values");}} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nos valeurs</a>
					<a href="/#who_we_are" onclick={(event: Event) => {$isOpen = false; scrollToValues(event, "who_we_are");}} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Qui sommes nous</a>
					<a href="/contact" onclick={(event: Event) => $isOpen = false} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nous contacter</a>
	    			<div class="flex items-center space-x-4">
						<a href="https://www.instagram.com/sprt.society/" target="_blank">
							<img src="/icons/insta.png" alt="Instagram" class="h-12 w-12" />
						</a>
						<a href="https://www.linkedin.com/company/sprt-society/" target="_blank">
							<img src="/icons/linkedin.png" alt="LinkedIn" class="h-12 w-12" />
						</a>
	    			</div>
				</div>
			</nav>
			<nav class="flex mobile:hidden">
			</nav>
		</div>	
	</header>
	<nav
	class="fixed bottom-0 left-0 right-0 z-50 bg-black text-yellow-400 border-t border-yellow-400 py-2 px-4 rounded-t-xl mobile:hidden"
	class:opacity-0={$footerVisible}
	class:opacity-100={!$footerVisible}
	>
		<div class="flex flex-wrap justify-center items-center gap-x-4 gap-y-1 w-fit max-w-full mx-auto text-center">
			<a href="/#concept" class="text-sm">Concept</a>
			<a href="/#values" class="text-sm">Nos valeurs</a>
			<a href="/#who_we_are" class="text-sm">Qui sommes nous</a>
			<a href="/contact" class="text-sm">Nous contacter</a>
		</div>
	</nav>
{/if}

<main>
	{@render children()}
</main>

<footer id="footer" class="text-white px-6 py-4 flex flex-col items-center pb-5 pt-5">
	<div class="w-[90%] flex items-center justify-between mx-auto pb-10">
		<nav class="flex flex-wrap justify-center md:justify-start gap-x-8 gap-y-4 text-lg tracking-widest pt-10"> 
			<a href="/#concept" onclick={(event: Event) => scrollToValues(event, "concept")} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Le concept</a>
			<a href="/#values" onclick={(event: Event) => scrollToValues(event, "values")} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nos valeurs</a>
			<a href="/#who_we_are" onclick={(event: Event) => scrollToValues(event, "who_we_are")} class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Qui sommes nous</a>
			<a href="/legal_notices" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Mentions légales</a>
			<a href="/downloads/FORMULAIRE-DE-RÉTRACTATION.pdf" target="_blank" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Se rétracter</a>
			<a href="/contact" class="relative pb-0.5 border-transparent hover:border-b-1 hover:border-yellow-400 transition duration-300">Nous contacter</a>
		</nav>		
		<div class="hidden laptop:flex items-center space-x-4">
			 <a href="/" class="block">
				<img src="sprt-logo.png" alt="Logo Sprt" class="h-32 w-auto object-contain" />
			</a>
		</div>
	</div>
	<button 
		onclick={scrollToTop}
		class="mb-5 flex items-center justify-center w-12 h-12 rounded-full border border-[#F9B333] text-[#F9B333] hover:bg-[#F9B333] hover:text-black transition laptop:hidden"
		aria-label="Retour en haut"
	>
		<svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
			<path stroke-linecap="round" stroke-linejoin="round" d="M5 15l7-7 7 7"/>
		</svg>
	</button>
	<div class="w-[95%] h-[1px] bg-[#F9B333] mb-4">
	  <p class="text-base text-center mt-2">
		SPRT 2025. All rights reserved.
	  </p>
	</div>
</footer>