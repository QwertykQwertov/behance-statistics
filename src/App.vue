<script setup>
import Head from './components/Head.vue'
import Content from './components/Content.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <!-- <HelloWorld msg="Vite + Vue" /> -->
  <Head />
  <Content />
  <Footer />

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
