<script lang="ts">
  import { onMount } from "svelte";

  let taglineElement: HTMLSpanElement;

  const lines = [
    "because we are cool coders...",
    "to lead the way in fintech industry...",
    "to build mass adoption technology for new generations...",
    "redefining finance for the economy...",
  ];

  onMount(() => {
    const intervalTime = 100;
    const pauseIterations = 8; // intervalTime * x

    let direction = "forwards";
    let shownLineLength = 0;
    let currentLineIndex = 0;
    let currentLine = lines[currentLineIndex];
    let pausedIterations = 0;

    const intervalRef = setInterval(() => {
      if (shownLineLength === currentLine.length) {
        if (pausedIterations === pauseIterations) {
          direction = "backwards";
          pausedIterations = 0;
        } else {
          pausedIterations++;
        }
      }

      if (shownLineLength < currentLine.length && direction === "forwards") shownLineLength++;
      if (shownLineLength > 0 && direction === "backwards") shownLineLength--;

      taglineElement.innerText = currentLine.slice(0, shownLineLength);

      if (direction === "backwards" && shownLineLength === 0) {
        direction = "forwards";

        if (currentLineIndex < lines.length - 1) currentLineIndex++;
        else currentLineIndex = 0;

        currentLine = lines[currentLineIndex];
      }
    }, intervalTime);

    return () => {
      clearInterval(intervalRef);
    };
  });
</script>

<span bind:this={taglineElement} class="tagline" />

<style lang="scss">
  .tagline {
    align-self: center;

    color: white;

    font-size: 96px;
    font-weight: 700;
    line-height: 94%;
    letter-spacing: -0.055em;

    margin-bottom: 60px;
  }
</style>
