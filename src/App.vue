<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
      <nav>
      <RouterLink to="/">Calculator</RouterLink>
         <RouterLink to="/about">about</RouterLink>
         </nav>
        
  </header>

<main>
<RouterView />
</main>
</template>

<style scoped>
   
</style>
