<script lang="ts">
  import './app.scss';

  import Figma from './lib/Figma.svelte';
  import Svelte from './lib/Svelte.svelte';
  import Vite from './lib/Vite.svelte';

  // How to send message to parent (Figma)
  parent.postMessage(
    {
      pluginMessage: {
        type: 'start',
      },
    },
    '*',
  );

  const clickPreview = () => {};

  const clickApply = () => {};
</script>

<div
  class="w-full min-h-screen flex flex-col items-center justify-center bg-gray-50"
>
  <div class="flex flex-row justify-center space-x-4 mb-6">
    <div class="p-2">
      <Figma />
    </div>
    <div class="p-2">
      <Svelte />
    </div>
    <div class="p-2">
      <Vite />
    </div>
  </div>

  <div class="flex flex-row justify-center space-x-2">
    <button
      class="px-4 py-2 rounded border border-gray-300 bg-white text-gray-700 hover:bg-gray-100 transition"
      onclick={clickPreview}
    >
      Preview
    </button>
    <button
      class="px-4 py-2 rounded bg-blue-600 text-white hover:bg-blue-700 transition"
      onclick={clickApply}
    >
      Apply
    </button>
  </div>
</div>
