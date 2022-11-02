<script lang="ts">
  import smartContractSections from "$lib/data/content/smartContractsSections.json";

  import TokenPlatformImage from "$lib/assets/images/token_platform.png";
  import SmartContractButton from "$lib/components/button/SmartContractButton.svelte";
  import SmartContractsContent from "./_SmartContractsContent.svelte";

  let activePane = 0;
</script>

<div class="smart-contracts">
  <img class="token-platform" src={TokenPlatformImage} alt="Token platform" />

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
</div>

<style lang="scss">
  .smart-contracts {
    position: relative;

    padding: 100px;
    min-height: 100vh;
    overflow: hidden;

    background-image: url("images/token_platform_background.png");
    background-repeat: no-repeat;
    background-position: cover;
    background-position: bottom right;

    .token-platform {
      position: absolute;
      bottom: -2rem;
      right: 190px;
      width: 540px;
    }

    .showcase-buttons {
      position: absolute;
      bottom: 100px;
      left: 100px;
      display: flex;
      gap: 1rem;
    }
  }
</style>
