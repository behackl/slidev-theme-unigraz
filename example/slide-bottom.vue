<!-- hide the footer from "cover" layout -->
<template>
  <header
    v-if="$nav.currentLayout !== 'cover'"
    class="absolute top-0 right-4 p-2 opacity-50"
  >
    <em>Benjamin Hackl</em>
  </header>
  <header
    v-if="$nav.currentLayout !== 'cover'"
    class="absolute top-0 left-4 p-2 opacity-50"
  >
    Short talk title YEP
  </header>
  <footer class="absolute bottom-0 left-4 p-2">
    <img src="/logo_kfu.jpeg" width="60">
  </footer>
</template>