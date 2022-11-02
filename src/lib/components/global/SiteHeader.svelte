<script lang="ts">
  import { fly } from "svelte/transition";
  import Fa from "svelte-fa/src/fa.svelte";
  import { faBars } from "@fortawesome/free-solid-svg-icons";
  import SiteHeaderActionButton from "../button/SiteHeaderActionButton.svelte";
  import { onMount } from "svelte";

  const links = [
    { name: "About", url: "" },
    { name: "Tokenization & Smart Contract", url: "" },
    { name: "Auditing", url: "" },
    { name: "Research & Development", url: "" },
    { name: "Metaverse", url: "" },
    { name: "Contact Details", url: "" },
  ];

  let isMenuToggled = false;
  const toggleMobileMenu = () => {
    if (isMenuToggled) {
      isMenuToggled = false;
    } else {
      isMenuToggled = true;
    }
  };

  onMount(() => {
    if (window.innerWidth >= 1376) isMenuToggled = true;

    const checkMenuVisibility = () => {
      if (window.innerWidth >= 1376) isMenuToggled = true;
      else isMenuToggled = false;
    };

    window.addEventListener("resize", checkMenuVisibility);

    return () => {
      window.removeEventListener("resize", checkMenuVisibility);
    };
  });
</script>

<button class="mobile-toggle" on:click={toggleMobileMenu}>
  <Fa icon={faBars} color="#a600c9" />
</button>

{#if isMenuToggled}
  <header transition:fly={{ y: 100 }}>
    <nav>
      {#each links as link}
        <a href={link.url}>{link.name}</a>
      {/each}
    </nav>

    <SiteHeaderActionButton label="Contact Us" />
  </header>
{/if}

<style lang="scss">
  .mobile-toggle {
    display: none;
    background: none;
    border: none;
    font-size: 2rem;

    &:hover {
      cursor: pointer;
    }

    @media (max-width: 1376px) {
      display: block;
      position: absolute;
      top: 2rem;
      right: 2rem;
    }
  }

  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 64px;

    @media (max-width: 1376px) {
      flex-direction: column;
      overflow: hidden;
      padding: 100px 0px;
    }

    nav {
      display: flex;
      gap: 64px;

      @media (max-width: 1376px) {
        flex-direction: column;
        text-align: center;
        gap: 36px;
      }

      a {
        font-family: "Ebrima", sans-serif;
        text-decoration: none;
        color: white;
        position: relative;

        &::after {
          content: "";
          height: 3px;

          position: absolute;
          bottom: -12px;
          left: 50%;
          transform: translateX(-50%);

          background: #a600c9;
          border-radius: 4px;

          width: 0px;
          transition: all 0.3s ease-in-out;
        }

        &:hover {
          &::after {
            width: 90%;
          }
        }
      }
    }
  }
</style>
