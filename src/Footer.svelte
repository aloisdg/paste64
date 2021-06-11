<script lang="ts">
  export let author: string;
</script>

<footer class="w-full flex justify-center items-center py-2">
  made with <a href="https://svelte.dev/" title="svelte"><img
    class="mx-1 w-4 h-4"
    src="https://svelte.dev/favicon.png"
    alt="svelte logo"
  /></a>
  by
  <a
    class="block py-2 transition-colors duration-200 hover:text-grey-600 text-grey-800 ml-1 font-medium"
    href="https://aloisdg.netlify.app/"
    title="aloisdg's blog">{author}</a
  >
</footer>
