<script lang="ts">
  import { onMount } from "svelte";
  import * as THREE from "three";
  // @ts-ignore
  import HALO from "vanta/dist/vanta.halo.min";

  let backgroundElement: HTMLDivElement;

  onMount(() => {
    const haloEffect = HALO({
      el: backgroundElement,
      THREE: THREE,
      mouseControls: true,
      touchControls: true,
      gyroControls: false,
      minHeight: window.innerHeight,
      minWidth: window.innerWidth - 100,
      backgroundColor: 0x0,
      xOffset: 0.16,
    });

    const handleResize = () => {
      haloEffect.resize();
    };

    window.addEventListener("resize", handleResize);

    return () => {
      haloEffect.destroy();
      window.removeEventListener("resize", handleResize);
    };
  });
</script>

<div class="background" bind:this={backgroundElement} />
