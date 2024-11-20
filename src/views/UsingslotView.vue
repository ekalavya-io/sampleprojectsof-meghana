<script setup>
import Card from '../components/Card.vue'
</script>

<template>
<v-col cols="12" md="4">
<v-Card>
  <template v-slot:title>
   Bookname:TOM JONES
  </template>
   <template v-slot:subtitle>
   Author:HENRY FEILDING
  </template>
   <template v-slot:text>
   based on true story
  </template>
</v-Card>
</v-col>
<v-col cols="12" md="4">
<v-Card>
  <template v-slot:title>
   Bookname:OLIVER TWIST
  </template>
   <template v-slot:subtitle>
   Author:CHARLES
  </template>
   <template v-slot:text>
   based on true story
  </template>
</v-Card>
</v-col>
</template>