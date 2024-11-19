<template>
  <div class="calculator">
    <div class="display">enter value here {{ expression }}</div>
   
    <form @submit.prevent="calculate">
      <div>
        <v-btn icon="$vuetify" type="button" @click.add="expression += '+'">+</v-btn>
        <v-btn icon="$vuetify"  type="button" @click.minus="expression += '-'">-</v-btn>
        <v-btn icon="$vuetify"  type="button" @click.muitiply="expression += '*'">*</v-btn>
        <v-btn icon="$vuetify" type="button" @click.divide="expression += '/'">/</v-btn>
      </div>
      <div>
        <v-btn icon="$vuetify"  type="button" @click.stop="expression += '.'">.</v-btn>
        <v-btn icon="$vuetify"  type="button" @click.stop="expression += '9'">9</v-btn>
        <v-btn icon="$vuetify"  type="button" @click.stop="expression += '8'">8</v-btn>
        <v-btn icon="$vuetify"  type="button" @click.stop="expression += '7'">7</v-btn>
      </div>
      <div>
        <v-btn icon="$vuetify"  type="button" @click.stop="expression += '6'">6</v-btn>
        <v-btn icon="$vuetify"  type="button" @click.stop="expression += '5'">5</v-btn>
        <v-btn icon="$vuetify"  type="button" @click.stop="expression += '4'">4</v-btn>
        <v-btn icon="$vuetify"  type="button" @click.stop="expression += '3'">3</v-btn>
      </div>
      <div>
        <v-btn icon="$vuetify"  type="button" @click.stop="expression += '2'">2</v-btn>
        <v-btn icon="$vuetify"  type="button" @click.stop="expression += '1'">1</v-btn>
        <v-btn icon="$vuetify"  type="button" @click.stop="expression += '0'">0</v-btn>
        <v-btn icon="$vuetify"  type="submit">=</v-btn>
      </div>
      <div>
        <v-btn icon="$vuetify"  type="button"  @click.stop="expression = ''">Clear</v-btn>
      </div>
    </form>
  </div>
</template>

<script setup>
import { evaluate } from "mathjs";

import {ref} from  'vue'
const expression = ref("");
function calculate() {
  try {
    expression.value = evaluate(expression.value); // Update the reactive variable
  } catch (error) {
    expression.value = "Error"; // Handle invalid expressions
  }
}
</script>

<style scoped>
.calculator{
  text-align:center; 
  width:500px;
  height:500px;
  border:1px solid black;
  background-color:white;
}
.clear-button {
  width: 90px;
}
.display{
  color:black;
  text-align:center;
  font-family:bold,
}
</style>

