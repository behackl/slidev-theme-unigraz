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
    Uni Graz-styled template slides, short title
  </header>
  <footer class="absolute bottom-0 left-4 p-2">
    <logo-unigraz width="60"/>
  </footer>
  <footer 
    v-if="$nav.currentLayout !== 'cover'"
    class="absolute bottom-0 right-4 p-2 opacity-50"
   >{{ $nav.currentPage }}</footer>
</template>