<script lang="ts">
  import smartContractSections from "$lib/data/content/smartContractsSections.json";

  import TokenPlatformImage from "$lib/assets/images/token_platform.png";
  import SmartContractButton from "$lib/components/button/SmartContractButton.svelte";
  import SmartContractsContent from "./_SmartContractsContent.svelte";

  let activePane = 0;
</script>

<div class="smart-contracts">
  {#each smartContractSections as section, paneIndex}
    {#if activePane === paneIndex}
      <SmartContractsContent {...section} />
    {/if}
  {/each}

  <div class="showcase-buttons">
    {#each smartContractSections as section, paneIndex}
      <SmartContractButton
        name={section.name}
        handleClick={() => (activePane = paneIndex)}
        isActive={activePane === paneIndex}
      />
    {/each}
  </div>

  <img class="token-platform" src={TokenPlatformImage} alt="Token platform" />
</div>

<style lang="scss">
  .smart-contracts {
    position: relative;

    padding: 100px;
    height: 1000px;
    overflow: hidden;

    background-image: url("images/token_platform_background.png");
    background-repeat: no-repeat;
    background-position: cover;
    background-position: bottom right;

    @media (max-width: 970px) {
      height: 1600px;
      background: none;
    }

    @media (max-width: 768px) {
      padding: 60px;
      background: none;
    }

    @media (max-width: 576px) {
      padding: 40px;
    }

    @media (max-width: 375px) {
      padding: 1rem;
    }

    .token-platform {
      position: absolute;
      bottom: 0;
      right: 190px;
      width: 530px;

      @media (max-width: 1440px) {
        right: 90px;
      }

      @media (max-width: 1200px) {
        width: 440px;
      }

      @media (max-width: 970px) {
        right: 50%;
        transform: translateX(50%);
      }

      @media (max-width: 510px) {
        width: calc(100% - 60px);
      }
    }

    .showcase-buttons {
      position: absolute;
      bottom: 100px;
      left: 100px;
      display: flex;
      gap: 1rem;

      z-index: 1;

      @media (max-width: 970px) {
        position: initial;
        margin-top: 6rem;
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        grid-template-rows: repeat(2, 1fr);
      }

      @media (max-width: 375px) {
        grid-template-rows: repeat(4, 1fr);
        grid-template-columns: 1fr;
      }
    }
  }
</style>
