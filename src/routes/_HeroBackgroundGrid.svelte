<script lang="ts">
  import { onMount } from "svelte";
  import * as THREE from "three";

  let gridDOMElement: HTMLDivElement;

  onMount(() => {
    const renderer = new THREE.WebGLRenderer();
    renderer.setSize(gridDOMElement.clientWidth, gridDOMElement.clientHeight);

    gridDOMElement.appendChild(renderer.domElement);

    const scene = new THREE.Scene();

    const camera = new THREE.PerspectiveCamera(45, gridDOMElement.clientWidth / gridDOMElement.clientHeight);

    camera.position.set(1, 0, 7);
    camera.lookAt(-1, 0, 0);

    const gridHelperAB = new THREE.GridHelper(10, 10);
    gridHelperAB.position.set(0, -5, 0);
    scene.add(gridHelperAB);

    const gridHelperBC = new THREE.GridHelper(10);
    gridHelperBC.rotateZ(Math.PI / 2);
    gridHelperBC.position.set(5, 0, 0);
    scene.add(gridHelperBC);

    const gridHelperCD = new THREE.GridHelper(10);
    gridHelperCD.position.set(0, 5, 0);
    scene.add(gridHelperCD);

    const gridHelperDA = new THREE.GridHelper(10);
    gridHelperDA.rotateZ(Math.PI / 2);
    gridHelperDA.position.set(-5, 0, 0);
    scene.add(gridHelperDA);

    let comeCloser = true;

    function animate() {
      if (Math.floor(camera.position.z) === 10) {
        comeCloser = false;
      } else if (Math.floor(camera.position.z) === 4) {
        comeCloser = true;
      }

      if (comeCloser) {
        camera.position.z += 0.006;
      } else {
        camera.position.z -= 0.006;
      }

      renderer.render(scene, camera);
    }

    renderer.setAnimationLoop(animate);

    const resizeListener = function () {
      camera.aspect = gridDOMElement.clientWidth / gridDOMElement.clientHeight;
      camera.updateProjectionMatrix();

      renderer.setSize(gridDOMElement.clientWidth, gridDOMElement.clientHeight);
    };

    window.addEventListener("resize", resizeListener);

    return () => {
      window.removeEventListener("resize", resizeListener);
    };
  });
</script>

<div class="hero-background-grid" bind:this={gridDOMElement} />

<style lang="scss">
  .hero-background-grid {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    z-index: -2;
  }

  :global(canvas) {
    opacity: 0.3;
  }
</style>
