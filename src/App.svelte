<script lang="ts">
  import "./app.scss";

  //import Global CSS from the svelte boilerplate
  //contains Figma color vars, spacing vars, utility classes and more
  import { GlobalCSS } from "figma-plugin-ds-svelte";

  //import some Svelte Figma UI components
  import { Button } from "figma-plugin-ds-svelte";
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
    <Button on:click={clickPreview} variant="secondary mr-xsmall"
      >Preview</Button
    >
    <Button on:click={clickApply}>Apply</Button>
  </div>
</div>
