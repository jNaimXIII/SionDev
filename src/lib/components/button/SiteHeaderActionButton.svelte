<script lang="ts">
  export let label: string;
  export let handleClick: (event: MouseEvent) => void = () => {};
</script>

<button on:click={handleClick}>{label}</button>

<style lang="scss">
  button {
    font-family: "Ebirma", sans-serif;
    font-size: 16px;
    color: white;

    padding: 12px 44px;

    background: rgba(61, 23, 69, 0.5);
    box-shadow: 0px 0px 65px -19px #d300ff;
    border: 0.5px solid white;
    border-radius: 12px;

    transition: all 0.3s ease-in-out;

    &:hover {
      cursor: pointer;
      background: rgba(106, 38, 120, 0.5);
    }
  }
</style>
