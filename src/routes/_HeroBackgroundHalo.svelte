<script lang="ts">
  import { onMount } from "svelte";
  import * as THREE from "three";
  // @ts-ignore
  import HALO from "vanta/dist/vanta.halo.min";

  let backgroundElement: HTMLDivElement;

  onMount(() => {
    const exposureElement = document.getElementById("exposure");
    const exposureElementHeight = exposureElement?.clientHeight || 0;

    let haloEffect: any;

    haloEffect = HALO({
      el: backgroundElement,
      THREE: THREE,
      mouseControls: true,
      touchControls: true,
      gyroControls: false,
      minHeight: window.innerHeight + exposureElementHeight,
      minWidth: window.innerWidth - 100,
      backgroundColor: 0x0,
      xOffset: 0.16,
      yOffset: 0.115,
      forceAnimate: true,
    });

    const handleResize = () => {
      haloEffect.destroy();

      haloEffect = HALO({
        el: backgroundElement,
        THREE: THREE,
        mouseControls: true,
        touchControls: true,
        gyroControls: false,
        minHeight: window.innerHeight + exposureElementHeight,
        minWidth: window.innerWidth - 100,
        backgroundColor: 0x0,
        xOffset: 0.16,
        forceAnimate: true,
      });
    };

    window.addEventListener("resize", handleResize);

    return () => {
      window.removeEventListener("resize", handleResize);
    };
  });
</script>

<div class="background" bind:this={backgroundElement} />

<style lang="scss">
  .background {
    position: relative;
    // z-index: 2;
  }

  :global(canvas.vanta-canvas) {
    opacity: 0.3;
  }
</style>
