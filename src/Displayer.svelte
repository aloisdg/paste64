<script lang="ts">
  export let base64: string;
  export let label: string;
  export let click: svelte.JSX.MouseEventHandler<HTMLButtonElement>;
</script>

<div class="grid grid-cols-1-auto gap-1">
  <div class="overflow-hidden rounded-lg bg-indigo-700">
    <pre
      class="scrollbar-none overflow-ellipsis overflow-x-auto p-6 text-sm leading-snug text-neon-50 bg-neon-900 bg-opacity-75">
                  <code>
                      {base64}
                  </code>
              </pre>
  </div>
  <button class="btn ml-2" type="button" on:click={click} title={label}>copy</button>
</div>

<style lang="postcss">
.btn {
  @apply rounded-lg flex-shrink-0 bg-neon-500 text-neon-50 text-base font-semibold py-2 px-4 shadow-md hover:bg-neon-600 focus:outline-none focus:ring-2 focus:ring-neon-500 focus:ring-offset-2 focus:ring-offset-neon-200;
}

.grid-cols-1-auto {
  grid-template-columns: 1fr auto;
}

.scrollbar-none::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
.scrollbar-none {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;  /* Firefox */
}
</style>
