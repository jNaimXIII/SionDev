<script lang="ts">
  import HeroBackgroundHalo from "./_HeroBackgroundHalo.svelte";
  import Hero from "./_Hero.svelte";
  import Exposure from "./_Exposure.svelte";
  import SmartContracts from "./_SmartContracts.svelte";
  import Metaverse from "./_Metaverse.svelte";
  import HeroBackgroundGrid from "./_HeroBackgroundGrid.svelte";
</script>

<svetle:head>
  <title>SionDev</title>
</svetle:head>

<main>
  <HeroBackgroundGrid />
  <HeroBackgroundHalo />
  <Hero />

  <Exposure />

  <SmartContracts />

  <Metaverse />
</main>

<style lang="scss">
  :global(body) {
    background: black;
  }
</style>
