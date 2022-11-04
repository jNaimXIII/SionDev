<script lang="ts">
  // import HeroGlitchHeading from "./_HeroGlitchHeading.svelte";
  import SionDevAGLogo from "$lib/assets/images/siondev_ag.png";
</script>

<div class="content">
  <!-- <HeroGlitchHeading /> -->
  <div class="logo">
    <img class="siondev-logo" src={SionDevAGLogo} alt="SionDev AG" />
  </div>

  <div class="catchphrase">
    <p class="punchline">
      <span class="keywords">revolutionary<br />blockchain</span>
      <span class="focus">ideas</span>
    </p>
    <p class="annotation">Sion developers are fintech addicts</p>
  </div>
</div>

<style lang="scss">
  .content {
    margin-top: 260px;

    display: flex;
    justify-content: space-between;
    align-items: center;

    color: white;
    font-family: "Ebrima", sans-serif;
    letter-spacing: -0.055em;

    @media (max-width: 1500px) {
      flex-direction: column;
      gap: 64px;
    }

    .logo {
      position: relative;
      flex: 1;

      &::before {
        content: "";
        top: -300%;
        left: -50%;
        position: absolute;
        width: 847px;
        height: 675px;
        background: radial-gradient(50% 50% at 50% 50%, rgba(116, 0, 140, 0.5) 0%, rgba(116, 0, 140, 0) 100%);
        opacity: 0.7;
        z-index: -1;
      }

      img {
        max-width: 100%;
      }
    }

    .catchphrase {
      position: relative;
      flex: 1;

      .punchline {
        font-weight: bold;

        .keywords {
          line-height: 93.59%;
          font-size: 96px;

          @media (max-width: 968px) {
            font-size: 64px;
          }

          @media (max-width: 768px) {
            font-size: 44px;
          }
        }

        .focus {
          font-weight: 700;
          font-size: 64px;

          // color: #74008c;

          @media (max-width: 968px) {
            font-size: 34px;
          }
        }
      }

      .annotation {
        color: #a6a6a6;
        letter-spacing: -0.055em;
      }

      &::before {
        content: "";
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-70%, -50%);
        height: 1000px;
        width: 1000px;

        background: radial-gradient(circle, rgba(255, 255, 255, 0.1) 0%, rgba(255, 255, 255, 0) 70%);

        @media (max-width: 968px) {
          width: 500px;
          height: 500px;
        }

        z-index: -1;
      }
    }
  }
</style>
