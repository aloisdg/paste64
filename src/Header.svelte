<div class="relative grid place-items-center">
  <div class="absolute overflow-hidden flex justify-items-center items-center background">
    <div class="stripes-wrapper">
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
      <div class="stripe" />
    </div>
    <div class="absolute gradient-mask" />
  </div>

  <header class="relative grid place-items-center">
    <h1
      aria-label="Paste64"
      class="normal-case text-center text-white text-3xl font-bold p-3 tracking-extra-widest"
    >
      ＰΛＳＴΞ ６４
    </h1>
  </header>
</div>

<!-- https://codepen.io/Pterobyte/pen/ppyGZO -->

<!-- https://codepen.io/FelixLuciano/pen/dyoPKKK -->
<style>
  .background {
    width: 200px;
    height: 200px;
    left: calc(50% - 100px);
    border-radius: 50%;
  }

  header {
    width: 100%;
    height: 200px;
  }

  .tracking-extra-widest {
    letter-spacing: 0.25em;
  }

  h1 {
    text-shadow: 1px 1px 0 #ccc, 2px 2px 0 #ccc, 3px 3px 0 #335, 4px 4px 0 #335,
      5px 5px 0 #335, 6px 6px 0 #335, 5px 5px 15px #999;
    font-family: "Geo", Arial;
  }

  .stripes-wrapper {
    width: 200px;
    height: 200px;
    /* filter: drop-shadow(0 0 20px #f29); */
    border-radius: 50%;
    overflow: hidden;
  }

  .stripe {
    width: 100%;
    height: 15px;
    background-color: #f29;
    animation: scroll 1s linear infinite;
  }

  @keyframes scroll {
    from {
      transform: translateY(-30px);
    }
  }

  .stripe + .stripe {
    margin-top: 15px;
  }

  .gradient-mask {
    width: 100%;
    height: 200px;
    /* background: linear-gradient(to bottom, #92f 0%, #f29 100%); */
    mix-blend-mode: multiply;
  }
</style>
