<template>
  <h1>
    USO SIMPLE DE AXIOS
  </h1>
  <h2>Usuarios de jsonplaceholder
    
  </h2>

  <ul>
    <li v-for="usuario in users" :key="users.id">
      {{ usuario.name }}
    </li>
  </ul>

</template>

<script setup>
import axios from 'axios'
import { ref, onMounted } from 'vue'

const users = ref([])

onMounted(() => {
  cargarUsers();
})

const cargarUsers = async () => {
  try {
    const response = await axios.get('https://jsonplaceholder.typicode.com/users');
    console.log(response);
    users.value = reponse.data;
  }

  catch (error) {
    console.error('Error:,', error)
  }
}
</script>