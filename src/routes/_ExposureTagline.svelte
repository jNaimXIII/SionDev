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

    type DirectionType = "forwards" | "backwards";
    let direction: DirectionType = "forwards";
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

      const isNextCharSpace = () => {
        if (shownLineLength === 0) return false;

        const nextChar = direction === "forwards" ? shownLineLength + 1 : shownLineLength - 1;

        return currentLine[nextChar] === " ";
      };

      if (shownLineLength < currentLine.length && direction === "forwards") {
        if (isNextCharSpace()) shownLineLength += 2;
        else shownLineLength++;
      }

      if (shownLineLength > 0 && direction === "backwards") {
        if (isNextCharSpace()) shownLineLength -= 2;
        else shownLineLength--;
      }

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
    min-height: 2ch;

    color: white;

    font-size: 38px;
    font-weight: 700;
    line-height: 94%;
    text-align: center;
  }
</style>
