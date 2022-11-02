<script lang="ts">
  import SmartContractButton from "$lib/components/button/SmartContractButton.svelte";

  import EthereumLogo from "$lib/assets/images/ethereum.png";
  import BNBLogo from "$lib/assets/images/bnb.png";
  import NFTLogo from "$lib/assets/images/nft.png";
  import PrivateBlockchainLogo from "$lib/assets/images/private_blockchain.png";

  import EthereumBackground from "$lib/assets/images/ethereum_background.png";
  import BNBBackgound from "$lib/assets/images/bnb_background.png";

  import { fade, fly } from "svelte/transition";
  import { backIn } from "svelte/easing";

  export let name: string;
  export let heading: string;
  export let subHeading: string;
  export let body: string;
  export let footer: string;
  export let handleClick = () => {};

  const getBackgroundImage = () => {
    switch (name) {
      case "Ethereum":
        return { logo: EthereumLogo, background: EthereumBackground };
      case "BNB":
        return { logo: BNBLogo, background: BNBBackgound };
      case "NFT":
        return { logo: NFTLogo, background: "" };
      case "Private Blockchain":
        return { logo: PrivateBlockchainLogo, background: "" };
      default:
        return { logo: "", background: "" };
    }
  };
  const { logo, background } = getBackgroundImage();
</script>

<div class="section">
  <span class="topic" in:fly={{ duration: 700, x: 200 }}>Tokenization & Smart Contract</span>
  <h3 class="heading" in:fly={{ duration: 800, x: 220 }}>{heading}</h3>
  <p class="sub-heading" in:fly={{ duration: 900, x: 240 }}>{subHeading}</p>

  <p class="body" in:fly={{ duration: 1000, x: 260 }}>{body}</p>
  <p class="footer" in:fly={{ duration: 1100, x: 280 }}>{footer}</p>

  <div in:fly={{ duration: 1200, x: 300 }}>
    <SmartContractButton
      {handleClick}
      name="Start Here"
      styles={{ border: "1px solid purple", padding: "12px 46px" }}
    />
  </div>
</div>

{#if logo}
  <img class="logo" src={logo} alt={name} in:fade={{ duration: 1400, easing: backIn }} />
{/if}

{#if background}
  <img class="background" src={background} alt={name} in:fade={{ duration: 1000, easing: backIn }} />
{/if}

<style lang="scss">
  .section {
    width: 50%;
    font-family: "Ebrima", sans-serif;
    color: white;

    @media (max-width: 970px) {
      width: 100%;
    }

    .topic {
      font-size: 40px;
      color: #74008c;
      display: block;
      margin-bottom: 30px;
      line-height: 93.59%;
      letter-spacing: -0.055em;

      @media (max-width: 510px) {
        font-size: 34px;
      }
    }

    .heading {
      font-size: 48px;
      font-weight: 700;
      text-transform: uppercase;
      margin-bottom: 30px;
      line-height: 93.59%;

      @media (max-width: 510px) {
        font-size: 44px;
      }
    }

    .sub-heading {
      text-transform: uppercase;
      font-size: 24px;
      color: #8a8888;
      margin-bottom: 33px;
      line-height: 93.59%;
      width: 30ch;

      @media (max-width: 510px) {
        width: 100%;
      }
    }

    .body,
    .footer {
      font-size: 18px;
      line-height: 1.2em;
      letter-spacing: -0.055em;
      color: #c2c0c0;
      width: 422px;

      @media (max-width: 1200px) {
        width: 340px;
      }

      @media (max-width: 970px) {
        width: 100%;
      }
    }

    .body {
      margin-bottom: 2ch;
    }

    .footer {
      margin-bottom: 64px;
    }
  }

  .logo,
  .background {
    position: absolute;
  }

  @keyframes bounce {
    from,
    to {
      transform: translateY(0);
    }

    50% {
      transform: translateY(-2rem);
    }
  }

  .logo {
    right: 200px;
    bottom: 300px;
    width: 500px;
    animation: bounce 4s ease-in-out infinite;
    z-index: 2;

    @media (max-width: 1440px) {
      right: 100px;
    }

    @media (max-width: 1200px) {
      width: 400px;
      right: 120px;
      bottom: 260px;
    }

    @media (max-width: 970px) {
      left: calc(50% - 200px);
    }

    @media (max-width: 510px) {
      width: 70vw;
      left: calc(50% - 35vw);
      bottom: 45vw;
    }
  }

  .background {
    bottom: 0;
    right: 0;
    height: 100%;

    @media (max-width: 970px) {
      z-index: -1;
    }
  }
</style>
