<template>
    <div>
      <h1>Users</h1>
      
      <ul>
        <li>{{ users.data.name }}</li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  import axios from 'axios';
  
  const users = ref([]);
  
  onMounted(async () => {
    try {
      const response = await axios.get('https://api.agify.io/?name=enal');
      users.value = response;
    } catch (error) {
      console.error('Error fetching users:', error);
    }
  });
  </script>
  