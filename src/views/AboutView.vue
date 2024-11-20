<script setup>
import { ref } from 'vue';

const valid = ref(false);
const firstname = ref('');
const lastname = ref('');
const email = ref('');

const nameRules = [
  (value) => {
    if (value) return true;
    return "Name is required.";
  },
  (value) => {
    if (value?.length <= 10) return true;
    return "Name must be less than 10 characters.";
  },
];

const emailRules = [
  (value) => {
    if (value) return true;
    return "E-mail is required.";
  },
  (value) => {
    if (/.+@.+\..+/.test(value)) return true;
    return "E-mail must be valid.";
  },
];

function showAlert() {
  if (firstname.value && lastname.value && email.value) {
    alert("Your data is submitted");
  } else {
    alert("Please fill out all fields.");
  }
}
</script>

<template>
  <v-form v-model="valid" @submit.prevent>
    <v-container class="container">
      <v-row>
        <v-col cols="12" md="4" >
          <v-text-field v-model="firstname" :counter="10" :rules="nameRules" label="First name" required ></v-text-field>
        </v-col>

        <v-col cols="12" md="4">
          <v-text-field v-model="lastname" :counter="10" :rules="nameRules" label="Last name" required></v-text-field>
        </v-col>

        <v-col cols="12"md="4" >
          <v-text-field v-model="email" :rules="emailRules" label="E-mail" required ></v-text-field>
        </v-col>
      </v-row>
    </v-container>
    <v-btn @click="showAlert">sumbit</v-btn>
  </v-form>
</template>

<style>
.container{
     background-color: #181818;
}
</style>
