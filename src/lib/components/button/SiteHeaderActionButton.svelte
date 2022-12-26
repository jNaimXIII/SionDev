<script lang="ts">
  export let label: string;
  export let handleClick: (event: MouseEvent) => void = () => {};
</script>

<button on:click={handleClick}>{label}</button>

<style lang="scss">
  button {
    font-family: "Mulish", sans-serif;
    font-size: 20px;
    font-weight: 700;
    color: white;

    padding: 12px 44px;

    transition: all 0.3s ease-in-out;
    background: transparent;
    border: none;

    &:hover {
      cursor: pointer;
      color: #d300ff;
    }
  }
</style>
