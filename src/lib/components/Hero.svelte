<script lang="ts">
  import emblaCarouselSvelte from 'embla-carousel-svelte';
  import Autoplay from 'embla-carousel-autoplay';

  const images = [
    { src: "/hero/slide_1.jpg", alt: "Slide 1", title: "190 % réalisés sur 2025" },
    { src: "/hero/slide_2.jpg", alt: "Slide 2", title: "300 personnes", subtitle: "Utilisent déjà notre service"},
    { src: "/hero/slide_3.jpg", alt: "Slide 3", title: "300 nouvelles places à venir" },
  ];

  let emblaApi: any;
  let selectedIndex = 0;

  const options = { loop: true };
  const plugins = [Autoplay({ delay: 5000, stopOnInteraction: false })];

  function onInit(event: CustomEvent) {
    emblaApi = event.detail;
    updateSelectedIndex();
    emblaApi.on('select', updateSelectedIndex);
  }

  function updateSelectedIndex() {
    if (emblaApi) {
      selectedIndex = emblaApi.selectedScrollSnap();
    }
  }

  function scrollTo(index: number) {
    if (emblaApi) emblaApi.scrollTo(index);
  }

  function scrollPrev() {
    if (emblaApi) emblaApi.scrollPrev();
  }

  function scrollNext() {
    if (emblaApi) emblaApi.scrollNext();
  }
</script>

<section class="w-full h-[100svh] relative overflow-hidden p-0">
  <div class="embla h-full" use:emblaCarouselSvelte={{ options, plugins }} on:emblaInit={onInit}>
    <div class="embla__container h-full">
      {#each images as image, index (index)}
        <div class="embla__slide relative h-full">
          <img 
            src={image.src} 
            alt={image.alt}
            class="w-full h-full object-cover"
          />
          <div class="absolute inset-0 bg-black/30"></div>
          
          <div class="absolute inset-0 flex flex-col items-center justify-center text-white text-center px-4">
            <h2 class="text-4xl font-bold text-6xl mb-4">
              {image.title}
            </h2>
			{#if image.subtitle?.length }
				<p class="text-lg md:text-3xl">
					{image.subtitle}
				</p>
			{/if}
          </div>
        </div>
      {/each}
    </div>
  </div>

  <button
    on:click={scrollPrev}
    class="hidden md:block absolute left-4 top-1/2 -translate-y-1/2 bg-white/80 text-black hover:text-white hover:bg-black p-3 rounded-full shadow-lg transition z-10"
    aria-label="Previous"
  >
    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"/>
    </svg>
  </button>

  <button
    on:click={scrollNext}
    class="hidden md:block absolute right-4 top-1/2 -translate-y-1/2 bg-white/80 text-black hover:text-white hover:bg-black p-3 rounded-full shadow-lg transition z-10"
    aria-label="Next"
  >
    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
    </svg>
  </button>

  <div class="absolute bottom-4 left-1/2 -translate-x-1/2 flex gap-2 z-10">
    {#each images as _, index}
      <button
        on:click={() => scrollTo(index)}
        class="w-3 h-3 rounded-full transition {selectedIndex === index ? 'bg-white' : 'bg-white/50 hover:bg-white/75'}"
        aria-label={`Aller à la slide ${index + 1}`}
      ></button>
    {/each}
  </div>
</section>

<style>
  .embla {
    overflow: hidden;
  }
  .embla__container {
    display: flex;
  }
  .embla__slide {
    flex: 0 0 100%;
    min-width: 0;
  }
</style>