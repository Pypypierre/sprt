<script lang="ts">
  import { onMount } from 'svelte';
  import { writable } from 'svelte/store';

  const slides = [
    { image: '/hero/slide_1.jpg', title: 'Titre Slide 1', subtitle: 'Sous-titre 1', objectPosition: 'object-center' },
    { image: '/hero/slide_2_.jpg', title: 'Titre Slide 2', subtitle: 'Sous-titre 2', objectPosition: 'object-[20%_center]' },
    { image: '/hero/slide_3.png', title: 'Titre Slide 3', subtitle: 'Sous-titre 3', objectPosition: 'object-center' },
  ];

  let current = writable(0);

  let interval: ReturnType<typeof setInterval>;

  function startTimer() {
    interval = setInterval(() => {
      current.update(n => (n + 1) % slides.length);
    }, 5000);
  }

  function resetTimer() {
    clearInterval(interval);
    startTimer();
  }

  onMount(() => {
    startTimer();
    return () => clearInterval(interval);
  });

  const goTo = (index: number) => {
    current.set(index);
    resetTimer();
  };

  // swipe logic
  let startX = 0;
  let isDragging = false;
  let offsetX = 0;
  const THRESHOLD = 60;

  const onPointerDown = (e: PointerEvent | TouchEvent) => {
    isDragging = true;
    offsetX = 0;
    startX = 'touches' in e ? e.touches[0].clientX : (e as PointerEvent).clientX;
    resetTimer(); // stop autoplay while user interacts
  };

  const onPointerMove = (e: PointerEvent | TouchEvent) => {
    if (!isDragging) return;
    const x = 'touches' in e ? e.touches[0].clientX : (e as PointerEvent).clientX;
    offsetX = x - startX;
  };

  const onPointerUp = () => {
    if (!isDragging) return;
    isDragging = false;

    if (Math.abs(offsetX) > THRESHOLD) {
      if (offsetX < 0) {
        current.update(n => (n + 1) % slides.length);
      } else {
        current.update(n => (n - 1 + slides.length) % slides.length);
      }
    }
    offsetX = 0;
    resetTimer(); // restart after interaction
  };

  // keyboard
  const onKeyDown = (e: KeyboardEvent) => {
    if (e.key === 'ArrowRight') {
      current.update(n => (n + 1) % slides.length);
      resetTimer();
    }
    if (e.key === 'ArrowLeft') {
      current.update(n => (n - 1 + slides.length) % slides.length);
      resetTimer();
    }
  };
</script>

<section
  class="relative w-full min-h-screen overflow-hidden"
  tabindex="0"
  on:keydown={onKeyDown}
  on:touchstart={onPointerDown}
  on:touchmove={onPointerMove}
  on:touchend={onPointerUp}
  on:mousedown|passive={(e) => onPointerDown(e as unknown as PointerEvent)}
  on:mousemove|passive={(e) => onPointerMove(e as unknown as PointerEvent)}
  on:mouseup|passive={onPointerUp}
  on:mouseleave|passive={onPointerUp}
>
  {#each slides as slide, i}
    <div
      class="absolute inset-0 transition-opacity duration-500"
      class:opacity-100={i === $current}
      class:opacity-0={i !== $current}
      style={i === $current && offsetX !== 0
        ? `transform: translateX(${offsetX}px); transition: none;`
        : ''}
    >
      <img
        src={slide.image}
        alt={slide.title}
        class={`w-full h-full object-cover ${slide.objectPosition}`}
      />
      <div class="absolute inset-0 bg-black/50 flex flex-col items-center justify-center text-center text-white px-4">
        <h1 class="text-4xl md:text-6xl font-bold mb-4">{slide.title}</h1>
        <p class="text-lg md:text-xl">{slide.subtitle}</p>
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
      />
    {/each}
  </div>
</section>
