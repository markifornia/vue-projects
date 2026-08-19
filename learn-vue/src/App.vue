<script setup>

  import { ref } from 'vue'

  const name = ref('Mark')

  import Header from '@/components/Header.vue'
  import Footer from '@/components/Footer.vue'
</script>

<template>
  <Header />
  <main>
    <h1>Hello, {{ name }}!</h1>
    <p>
      I'm about to learn
      <a href="https://vuejs.org/" target="_blank">Vue.js</a>!
    </p>
  </main>

  <Footer />
</template>

<style scoped>

main h1 {
  display: block;
}

main a {
  color: #42B883;
}
</style>