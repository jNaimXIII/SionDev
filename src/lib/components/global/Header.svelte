<script lang="ts">
  import Button from "../button/Button.svelte";

  const links = [
    { name: "About", url: "" },
    { name: "Tokenization & Smart Contract", url: "" },
    { name: "Auditing", url: "" },
    { name: "Research & Development", url: "" },
    { name: "Contact Details", url: "" },
  ];
</script>

<header>
  <nav>
    {#each links as link}
      <a href={link.url}>{link.name}</a>
    {/each}
  </nav>

  <Button label="Contact Us" />
</header>

<style lang="scss">
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  nav {
    display: flex;
    gap: 64px;

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
</style>
