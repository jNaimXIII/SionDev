<script lang="ts">
  import * as THREE from "three";
  // @ts-ignore
  import HALO from "vanta/dist/vanta.halo.min";

  function vanta(node: HTMLElement) {
    // @ts-ignore
    HALO({
      el: node,
      THREE: THREE,
      color: 0xfff,
      xOffset: 0.16,
      mouseControls: true,
      touchControls: true,
      gyroControls: true,
      minHeight: window.innerHeight,
      minWidth: window.innerWidth,
      backgroundColor: 0x0,
    });
  }
</script>

<div class="background" use:vanta />

<style lang="scss">
  .background {
    top: 0;
    left: 0;
    z-index: -1;
  }
</style>
