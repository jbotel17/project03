<script setup>
import { ref } from "vue";

const contacts = ref([]);
    const name = ref("");
    const phone = ref("")


</script>

<template>
<div class="container">
  <h1>Contact List</h1>

  <div class="form-group">
    <label for="name">Name:</label>
    <input v-model="name" type="text" id="name" placeholder="Enter Name">

    <label for="phone">Phone Number:</label>
    <input v-model="phone" type="text" id="phone" placeholder="Enter Phone Number">

    <button @click="addContact">Add Contact</button>
  </div>  

</div>


</template>
