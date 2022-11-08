<script lang="ts">
  import MetaverseBackgroundImage from "$lib/assets/images/metaverse_background.png";
  import MetaverseBackgroundOverlay from "$lib/assets/images/metaverse_background_overlay.png";
  import MetaverseBackgroundVideo from "$lib/assets/videos/metaverse_background.mp4";
  import MetaverseHeading from "$lib/assets/images/metaverse_heading.png";
  import MetaverseSubHeading from "$lib/assets/images/metaverse_sub_heading.png";
</script>

<div class="metaverse">
  <video class="video" autoplay loop muted src={MetaverseBackgroundVideo}>
    <track kind="captions" />
  </video>

  <img src={MetaverseBackgroundImage} alt="Overlay" class="overlay" />
  <img src={MetaverseBackgroundOverlay} alt="Sprite" class="sprite" />

  <img src={MetaverseHeading} alt="Metaverse heading" class="heading" />
  <img src={MetaverseSubHeading} alt="Metaverse sub-heading" class="sub-heading" />

  <div class="gradient-overlay" />
</div>

<div class="metaverse-content">
  <p>
    The Metaverse offers the possibility of connecting with the world, sharing one's art, tokenizing and re-evaluating
    the property, increasing earnings exponentially.
  </p>

  <p>
    We are able to digitize any reality and bring it to the Metaverse, creating a circulating economy thanks to
    Tokenization in order to benefit and create value for every member of your community.
  </p>
</div>

<style lang="scss">
  .metaverse {
    position: relative;
    overflow: hidden;

    .video {
      position: absolute;
      width: 100%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -32%);
      z-index: -1;
    }

    .overlay {
      width: 100%;
      display: block;
    }

    .sprite {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      display: block;

      z-index: 2;
    }

    .heading {
      position: absolute;
      top: 50%;
      left: 50%;

      display: block;

      transform: translate(-50%, -20%);

      width: 64%;
    }

    .sub-heading {
      position: absolute;

      position: absolute;
      top: 54%;
      left: 58%;

      display: block;

      width: 24%;
    }

    .gradient-overlay {
      position: absolute;
      top: 0;
      left: 0;
      inset: 0;

      background: linear-gradient(180deg, #000000 0%, rgba(0, 0, 0, 0) 48.91%, #030303 100%);
    }
  }

  .metaverse-content {
    width: 70%;
    max-width: 1000px;

    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;

    margin: auto;
    margin-bottom: 20px;

    p {
      font-family: "Ebrima", sans-serif;
      font-size: 20px;
      line-height: 26px;
      letter-spacing: -5%;
      color: #c2c0c0;
      text-align: center;
    }
  }
</style>
