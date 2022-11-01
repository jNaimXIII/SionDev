<script lang="ts">
  import SmartContractButton from "$lib/components/button/SmartContractButton.svelte";
  import EthereumLogo from "$lib/assets/images/ethereum.png";
  import EthereumBackground from "$lib/assets/images/ethereum_background.png";

  export let heading: string;
  export let subHeading: string;
  export let body: string;
  export let footer: string;
  export let handleClick = () => {};
</script>

<div class="section">
  <span class="topic">Tokenization & Smart Contract</span>
  <h3 class="heading">{heading}</h3>
  <p class="sub-heading">{subHeading}</p>

  <p class="body">{body}</p>
  <p class="footer">{footer}</p>

  <SmartContractButton {handleClick} name="Start Here" styles={{ border: "1px solid purple", padding: "12px 46px" }} />
</div>

<div class="banner">
  <img class="logo" src={EthereumLogo} alt="Ethereum" />
  <img class="background" src={EthereumBackground} alt="Ethereum background" />
</div>

<style lang="scss">
  .section {
    width: 50%;
    font-family: "Ebrima", sans-serif;
    color: white;

    .topic {
      font-size: 40px;
      color: #74008c;
      display: block;
      margin-bottom: 30px;
      line-height: 93.59%;
      letter-spacing: -0.055em;
    }

    .heading {
      font-size: 48px;
      font-weight: 700;
      text-transform: uppercase;
      margin-bottom: 30px;
      line-height: 93.59%;
    }

    .sub-heading {
      text-transform: uppercase;
      font-size: 24px;
      color: #8a8888;
      margin-bottom: 33px;
      line-height: 93.59%;
      width: 30ch;
    }

    .body,
    .footer {
      font-size: 20px;
      line-height: 93.59%;
      letter-spacing: -0.055em;
      color: #c2c0c0;
      width: 422px;
    }

    .body {
      margin-bottom: 2ch;
    }

    .footer {
      margin-bottom: 64px;
    }
  }

  .banner {
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
      bottom: 360px;
      width: 500px;
      animation: bounce 4s ease-in-out infinite;
    }

    .background {
      bottom: 0;
      right: 0;
      height: 100%;
    }
  }
</style>
