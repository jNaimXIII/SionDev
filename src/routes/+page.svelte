<script lang="ts">
  import SiteHeader from "$lib/components/global/SiteHeader.svelte";
  import HeroBackgroundGrid from "./_HeroBackgroundGrid.svelte";
</script>

<svetle:head>
  <title>SionDev</title>
</svetle:head>

<main>
  <div class="hero">
    <HeroBackgroundGrid />

    <SiteHeader />

    <div class="content">
      <h1 class="site-heading">siondev ag</h1>

      <div class="catchphrase">
        <p class="punchline">
          <span class="keywords">revolutionary<br />blockchain</span>
          <span class="focus">ideas</span>
        </p>
        <p class="annotation">Sion developers are fintech addicts</p>
      </div>
    </div>
  </div>

  <div class="exposure">
    <div class="exposure-section-start" />

    <div class="content">
      <span class="initial">Development blockchain solutions</span>
      <span class="tagline">because we are cool coders...</span>
      <span class="signature">siondev ag</span>
    </div>

    <div class="exposure-section-end" />
  </div>
</main>

<style lang="scss">
  :global(body) {
    background: #111;
  }

  .hero {
    min-height: 100vh;
    padding: 100px;

    display: flex;
    flex-direction: column;

    @media (max-width: 968px) {
      padding: 16px;
    }

    .content {
      margin-top: 260px;

      display: flex;
      justify-content: space-between;
      align-items: center;

      & > * {
        flex: 1;
      }

      color: white;
      font-family: "Ebrima", sans-serif;
      letter-spacing: -0.055em;

      @media (max-width: 1500px) {
        flex-direction: column;
        gap: 64px;
      }

      .site-heading {
        font-size: 128px;
        position: relative;

        @media (max-width: 968px) {
          font-size: 96px;
        }

        @media (max-width: 532px) {
          font-size: 66px;
        }

        &::before {
          content: "";
          position: absolute;
          width: 847px;
          height: 675px;
          top: 50%;
          transform: translate(-60%, -50%);

          background: radial-gradient(50% 50% at 50% 50%, rgba(116, 0, 140, 0.5) 0%, rgba(116, 0, 140, 0) 100%);

          @media (max-width: 768px) {
            width: 500px;
          }

          z-index: -1;
        }
      }

      .catchphrase {
        position: relative;

        .punchline {
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

            color: #74008c;

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
  }

  .exposure {
    .content {
      padding: 152px 244px;

      display: flex;
      flex-direction: column;

      font-family: "Ebrima", sans-serif;

      @media (max-width: 968px) {
        padding: 38px;
      }

      .initial {
        color: #74008c;
        font-size: 36px;
        letter-spacing: -0.055em;

        margin-bottom: 40px;
      }

      .tagline {
        align-self: center;

        color: white;

        font-size: 96px;
        font-weight: 700;
        line-height: 94%;
        letter-spacing: -0.055em;

        margin-bottom: 60px;
      }

      .signature {
        align-self: flex-end;

        color: #ffffff;

        font-size: 40px;
        font-weight: 700;
        letter-spacing: -0.055em;
      }
    }

    &-section {
      &-start,
      &-end {
        height: 4px;
      }

      &-start {
        background: linear-gradient(270deg, rgba(255, 255, 255, 0.2) 0%, rgba(116, 0, 140, 0.2) 100%);
        position: relative;

        &::before {
          content: "";
          position: absolute;
          width: 847px;
          height: 675px;
          top: -100px;
          left: -15%;

          background: radial-gradient(50% 50% at 50% 50%, rgba(116, 0, 140, 0.08) 0%, rgba(116, 0, 140, 0) 100%);

          z-index: -1;

          @media (max-width: 968px) {
            width: 100%;
          }
        }
      }

      &-end {
        background: linear-gradient(270deg, rgba(116, 0, 140, 0.2) 0%, rgba(255, 255, 255, 0.2) 100%);

        position: relative;

        &::after {
          content: "";
          position: absolute;
          width: 750px;
          height: 729px;
          top: -740px;
          right: 0;

          background: radial-gradient(50% 50% at 50% 50%, rgba(116, 0, 140, 0.08) 0%, rgba(116, 0, 140, 0) 100%);

          z-index: -1;

          @media (max-width: 968px) {
            width: 100%;
          }
        }
      }
    }
  }
</style>
