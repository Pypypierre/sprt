<script>
  export let show = false;
</script>

{#if show}
  <div class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-70 z-50 w-full h-full transition-opacity duration-1000">
    <img src="/sprt-logo.png" alt="Loading..." class="w-[30%] tablet:w-[20%] mx-auto animate-fade-in-out" />
  </div>
{/if}