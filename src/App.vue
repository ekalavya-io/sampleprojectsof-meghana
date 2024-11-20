<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Card from './components/Card.vue'
</script>

<template>
  <header>
      <nav>
      <RouterLink to="/">Calculator</RouterLink>
         <RouterLink to="/about">about</RouterLink>
         <RouterLink to="/slot">slot</RouterLink>
         </nav>
        
  </header>

<main>
<RouterView />
</main>
</template>

<style scoped>
   
</style>
