<script lang="ts">
  export let author: string;
  export let base0: string;
  import Header from "./Header.svelte";
  import Displayer from "./Displayer.svelte";
  import Footer from "./Footer.svelte";

  // https://github.com/zenorocha/clipboard.js
  const copyToClipboard = (text: string) => {
    let input = document.createElement("input");
    document.body.appendChild(input);
    input.value = text;
    input.select();
    document.execCommand("copy", false);
    input.remove();
  }

  let base64 = base0;

  document.onpaste = function (event) {
    const items = (event.clipboardData || event.originalEvent.clipboardData)
      .items;
    console.log(JSON.stringify(items)); // will give you the mime types
    for (let index in items) {
      var item = items[index];
      if (item.kind === "file") {
        var blob = item.getAsFile();
        var reader = new FileReader();
        reader.onload = function (event) {
          base64 = event.target.result as string;
          // document.querySelector('#thumbnail').src = base64
        };
        reader.readAsDataURL(blob);
      }
    }
  };
</script>

<Header />

<main class="p-2 grid grid-rows-auto-1-auto gap-4 max-w-screen-lg mx-auto">
  <section class="row-span-1">
    <h1 class="tracking-wider text-center">
      Paste your image anywhere in the page,<br />
      Then copy its base64 representation!
    </h1>
  </section>
  <section class="rounded-lg waves row-span-2 grid place-items-center">
      <img class="max-h-64" alt="thumbnail" src={base64} />
  </section>

  <section class="grid gap-4 row-span-3">
    <Displayer {base64} label="Copy as base64" click={_ => copyToClipboard(base64)} />
    <Displayer
      base64={`![](${base64})`}
      label="Copy as Markdown"
      click={_ => copyToClipboard(`![](${base64})`)}
    />
    <Displayer
      base64={`[]: ${base64}`}
      label="Copy as split Markdown"
      click={_ => copyToClipboard(`[]: ${base64}`)}
    />
    <Displayer
      base64={`<img src="${base64}"/>`}
      label="Copy as HTML"
      click={_ => copyToClipboard(`<img src="${base64}"/>`)}
    />
  </section>
</main>

<Footer {author} />

<style global lang="postcss">
@tailwind base;
@tailwind components;
@tailwind utilities;

.grid-rows-auto-1-auto {
  grid-template-rows: auto 1fr auto;
}

.waves {
  background:
    linear-gradient(135deg, transparent 21px, #f29 22px, #f29 24px, transparent 24px, transparent 67px, #f29 67px, #f29 69px, transparent 69px),
    linear-gradient(225deg, transparent 21px, #f29 22px, #f29 24px, transparent 24px, transparent 67px, #f29 67px, #f29 69px, transparent 69px) 0 64px;
  background-size: 64px 128px;
}
</style>
