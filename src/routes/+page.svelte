<script lang="ts">
  import Exposure from "./_Exposure.svelte";
  import Hero from "./_Hero.svelte";
</script>

<svetle:head>
  <title>SionDev</title>
</svetle:head>

<main>
  <Hero />

  <Exposure />
</main>

<style lang="scss">
  :global(body) {
    background: #111;
  }
</style>
