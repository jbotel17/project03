<script setup>
import { ref } from "vue";

const contacts = ref([]);
    const name = ref("");
    const phone = ref("")

    const addContact = () => {
      if (!name.value.trim() || !phone.value.trim()) {
        alert("Please enter both name and phone number.");
        return;
      }
      contacts.value.push({ name: name.value, phone: phone.value });
      name.value = "";
      phone.value = "";
    };

    const deleteContact = (index) => {
      contacts.value.splice(index, 1);
    };

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
  
  <h2>Saved Contacts</h2>

  <ul>
      <li v-for="(contact, index) in contacts" :key="index">
        {{ contact.name }} - {{ contact.phone }}
        <button class="deleteBtn" @click="deleteContact(index)"></button>
      </li>
    </ul>

</div>

</template>
