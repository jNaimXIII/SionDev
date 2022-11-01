<script lang="ts">
  import Hero from "./_Hero.svelte";
  import Exposure from "./_Exposure.svelte";
    import SmartContracts from "./_SmartContracts.svelte";
</script>

<svetle:head>
  <title>SionDev</title>
</svetle:head>

<main>
  <Hero />

  <Exposure />

  <SmartContracts />
</main>

<style lang="scss">
  :global(body) {
    background: #111;
  }
</style>
