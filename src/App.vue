<script setup>
import Calculator from './components/Calculator.vue'
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
      <nav>
        <RouterLink to="/">Calculator</RouterLink>
      </nav>
  </header>
<Routerview/>
<main>
<Calculator/>
</main>
</template>

<style scoped>
   
</style>
