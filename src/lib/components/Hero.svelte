<script lang="ts">
  import { onMount } from 'svelte';
  import { writable } from 'svelte/store';

  const slides = [
    {
      image: '/hero/slide_1.jpg',
      title: '190 % réalisés sur 2025',
	  objectPosition: 'object-center'
    },
    {
      image: '/hero/slide_2.jpg',
      title: '300 personnes',
      subtitle: 'Utilisent déjà notre service',
	  objectPosition: 'object-[20%_center]'
    },
    {
      image: '/hero/slide_3.jpg',
      title: '300 nouvelles places à venir',
	  objectPosition: 'object-center'
    },
  ];

  let current = writable(0);

  onMount(() => {
    const interval = setInterval(() => {
      current.update(n => (n + 1) % slides.length);
    }, 5000);
    return () => clearInterval(interval);
  });

  const goTo = (index: number) => current.set(index);
</script>

<section class="relative w-full min-h-screen overflow-hidden">
  {#each slides as slide, i}
    <div
      class="absolute inset-0 transition-opacity duration-1000"
      class:opacity-100={i === $current}
      class:opacity-0={i !== $current}
    >
      <img src={slide.image} alt={slide.title} class="w-full h-full object-cover ${slide.objectPosition}" />
      <div class="absolute inset-0 bg-black/50 flex flex-col items-center justify-center text-center text-white px-4">
        <h1 class="text-4xl md:text-6xl font-bold mb-4">{slide.title}</h1>
        <p class="text-lg md:text-2xl">{slide.subtitle}</p>
      </div>
    </div>
  {/each}

  <div class="absolute bottom-6 left-1/2 -translate-x-1/2 flex space-x-3">
    {#each slides as _, i}
      <button
        on:click={() => goTo(i)}
        class="w-3 h-3 rounded-full transition"
        class:bg-yellow-400={i === $current}
        class:bg-white={i !== $current}
        aria-label={`Aller à la diapositive ${i + 1}`}
      ></button>
    {/each}
  </div>
</section>