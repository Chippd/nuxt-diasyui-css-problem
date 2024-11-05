<template>

<div class="p-3">
  <h1 class="text-3xl font-light tracking-wider space-x-7">
    Problem
  </h1>
  <div class="py-5 text-sm main-content">
    <p>
      It appears as though a lot of boilerplate code is added to this page unnecessarily <strong>when the project is built</strong>.
      <br>
      <br>
      Or, to put it another way, it doesn't seem like unused classes are removed from the compiled CSS as they should be.
    </p>
    <p>
      We're following the instructions on the <a class="link" href="https://daisyui.com/docs/install/" target="_blank">DaisyUI install page</a> and have consulted the example Nuxt project on the <a class="link" href="https://stackblitz.com/edit/daisyui-nuxt3?file=package.json" target="_blank">Stackblitz page</a>.
    </p>

    <p>
      When we run the commands for this project:
    </p>
    <div class="mockup-code">
      <pre data-prefix="$"><code>npx nuxi build</code></pre>
      <pre data-prefix="$"><code>npx nuxi preview</code></pre>
    </div>

    <p class="mt-5">
      We see that the index page that is generated is quite heavy (36kb) for the content that is on it.
    </p>
    <figure>
      <img src="/images/size.png" alt="Index page size">
      <figcaption class="text-sm text-gray-400 mt-2">Network tab showing the index page size of 36kb</figcaption>
    </figure>

    <p class="mt-5">
      When we investigate the response preview, we see that there are classes included in the page that are not used. Not only are they not used on this page, but they're not used on any of the pages in the project.
    </p>
    <figure>
      <img src="/images/unnecessary-classes.png" alt="Unused classes">
      <figcaption class="text-sm text-gray-400 mt-2">Response preview showing unused CSS classes in the built output</figcaption>
    </figure>

    <figure>
      <img src="/images/dialog-search.png" alt="Dialog search">
      <figcaption class="text-sm text-gray-400 mt-2">Searching the project for the included classes brings up no results</figcaption>
    </figure>

  </div>
</div>

</template>

<style scoped>
.main-content {
  p {
    @apply py-2 text-gray-100;
  }
}

img {
  @apply w-full rounded-lg shadow-lg outline outline-2 outline-gray-400;
}

figure {
  @apply my-5;
}
</style>
