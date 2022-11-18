<script lang="ts">
  import SiteHeader from "$lib/components/global/SiteHeader.svelte";
  // import HeroBackgroundGrid from "./_HeroBackgroundGrid.svelte";
  import HeroBackgroundParticles from "./_HeroBackgroundParticles.svelte";
  import HeroContent from "./_HeroContent.svelte";
</script>

<div class="hero">
  <SiteHeader />

  <!-- <HeroBackgroundGrid /> -->
  <HeroBackgroundParticles />

  <HeroContent />
</div>

<style lang="scss">
  .hero {
    position: relative;
    overflow: hidden;
    min-height: 100vh;
    padding: 100px;

    display: flex;
    flex-direction: column;

    @media (max-width: 968px) {
      padding: 16px;
    }
  }
</style>
