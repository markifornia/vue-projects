<script setup>
  import { ref } from 'vue'

  const current_year = ref('2026')
</script>

<template>
  <footer>
    <p>&copy; {{ current_year }}</p>
  </footer>

</template>

<style scoped>
    footer {
    position: fixed;
    bottom: 0;
    padding-bottom: 20px;
    }
</style>