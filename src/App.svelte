<script lang="ts">
  import "./app.scss";

  import Figma from "./lib/Figma.svelte";
  import Svelte from "./lib/Svelte.svelte";
  import Vite from "./lib/Vite.svelte";

  // How to send message to parent (Figma)
  parent.postMessage(
    {
      pluginMessage: {
        type: "start",
      },
    },
    "*"
  );

  const clickPreview = () => {};

  const clickApply = () => {};
</script>

<div class="wrapper p-xxsmall flex column">
  <div class="flex row justify-content-center">
    <div class="p-xsmall">
      <Figma />
    </div>
    <div class="p-xsmall">
      <Svelte />
    </div>
    <div class="p-xsmall">
      <Vite />
    </div>
  </div>

  <div class="flex p-xxsmall mb-xsmall justify-content-center">
    <button class="button button--secondary mr-xsmall" onclick={clickPreview}
      >Preview</button
    >
    <button class="button button--primary" onclick={clickApply}>Apply</button>
  </div>
</div>
