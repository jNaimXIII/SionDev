<script>
  import ExposureBackgroundParticles from "./_ExposureBackgroundParticles.svelte";
  import ExposureTagline from "./_ExposureTagline.svelte";
</script>

<div class="exposure">
  <ExposureBackgroundParticles />

  <!-- <div class="exposure-section-start" /> -->

  <div class="content">
    <span class="initial">Development blockchain solutions</span>

    <ExposureTagline />

    <span class="signature">siondev ag</span>
  </div>

  <div class="exposure-section-end" />
</div>

<style lang="scss">
  .exposure {
    position: relative;
    background: rgba(109, 30, 30, 0.03);

    .content {
      padding: 72px 244px;

      display: flex;
      flex-direction: column;
      gap: 44px;

      font-family: "Ebrima", sans-serif;

      @media (max-width: 968px) {
        padding: 38px;
      }

      .initial {
        color: #74008c;
        font-size: 36px;
        letter-spacing: -0.055em;
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
      @keyframes background-pan {
        from {
          background-position: 0% center;
        }
        to {
          background-position: -200% center;
        }
      }

      @keyframes background-pan-alt {
        from {
          background-position: -200% center;
        }
        to {
          background-position: 0% center;
        }
      }

      // &-start,
      &-end {
        height: 4px;
      }

      // &-start {
      //   background: linear-gradient(
      //     270deg,
      //     rgba(255, 255, 255, 0.2),
      //     rgba(116, 0, 140, 0.2),
      //     rgba(116, 0, 140, 0.2),
      //     rgba(255, 255, 255, 0.2)
      //   );
      //   background-size: 200%;
      //   animation: background-pan 3s linear infinite;

      //   position: relative;

      //   &::before {
      //     content: "";
      //     position: absolute;
      //     width: 847px;
      //     height: 675px;
      //     max-height: 100%;
      //     top: -100px;
      //     left: -15%;

      //     background: radial-gradient(50% 50% at 50% 50%, rgba(116, 0, 140, 0.08) 0%, rgba(116, 0, 140, 0) 100%);

      //     z-index: -1;

      //     @media (max-width: 968px) {
      //       width: 100%;
      //     }
      //   }
      // }

      &-end {
        background: linear-gradient(
          270deg,
          rgba(116, 0, 140, 0.2),
          rgba(255, 255, 255, 0.2),
          rgba(255, 255, 255, 0.2),
          rgba(116, 0, 140, 0.2)
        );
        background-size: 200%;
        animation: background-pan-alt 3s linear infinite;

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
