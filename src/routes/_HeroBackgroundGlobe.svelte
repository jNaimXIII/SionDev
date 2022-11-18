<script lang="ts">
  import { onMount } from "svelte";
  import * as THREE from "three";
  // @ts-ignore
  import GLOBE from "vanta/dist/vanta.globe.min";

  let backgroundElement: HTMLDivElement;

  onMount(() => {
    const globeEffect = GLOBE({
      el: backgroundElement,
      THREE: THREE,
      mouseControls: true,
      touchControls: true,
      gyroControls: false,
      minHeight: window.innerHeight,
      minWidth: window.innerWidth - 100,
      color: 0xffffff,
      color2: 0xffffff,
      backgroundColor: 0x0,
    });

    const handleResize = () => {
      globeEffect.resize();
    };

    window.addEventListener("resize", handleResize);

    return () => {
      globeEffect.destroy();
      window.removeEventListener("resize", handleResize);
    };
  });
</script>

<div class="background" bind:this={backgroundElement} />

<style lang="scss">
  .background {
    opacity: 0.4;
  }
</style>
