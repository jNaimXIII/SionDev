<script lang="ts">
  export let name: string;
  export let handleClick = () => {};
  export let isActive: boolean = false;
  export let styles: {
    border?: string;
    padding?: string;
  } = {
    border: "",
    padding: "",
  };
</script>

<button
  on:click={handleClick}
  style={`
    ${isActive ? "--background:rgba(61, 23, 69, 0.5);" : ""}
    ${styles.border ? `--border:${styles.border};` : ""}
    ${styles.padding ? `--padding:${styles.padding};` : ""}
  `}
>
  {name}
</button>

<style lang="scss">
  button {
    font-family: "Ebrima", sans-serif;
    font-size: 20px;
    line-height: 93.59%;
    letter-spacing: -0.055em;
    color: white;
    padding: var(--padding, 12px 30px);
    background: var(--background, transparent);
    box-shadow: 0px 0px 65px -19px #d300ff;
    border: var(--border, 1px solid rgba(255, 255, 255, 0.3));
    border-radius: 12px;
    transition: all 0.3s ease-out;

    &:hover {
      cursor: pointer;
      background: rgba(61, 23, 69, 0.5);
    }
  }
</style>
