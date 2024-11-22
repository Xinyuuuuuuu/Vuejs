<template>
  <h1>
    "EDICION DE LISTA DE NOTAS (COMPUTED)"
  </h1>
  <form @submit.prevent="addnota">
    <input type="text" placeholder="nota" v-model="nota" @keydown.enter="addNota">

    <button type="submit">Crear</button>
  </form>

  <h2>Listado de tablas</h2>
  <ul>
    <li v-for="(nota, index) in notas" :key="nota.id">
      <input type="text" v-model="nota.text" :disabled="!nota.editando">
      <button @click="editNota(nota)">{{ nota.editando? 'confirmar':'editar' }}</button>
      <button @click="deleteNota(index)">Eliminar</button>
    </li>
  </ul>
</template>

<script setup>
import {ref} from 'vue';
let inabilitado="true";
const notas=ref([]);
const newNota=ref('');
//const deshabilitado=ref(true)

const addNota = ()=>{
  notas.value.push({
    id:Date.now(),
    text: newNota.value,
    editandi: false
  });
  newNota.value ='';
}

const deleteNota= (index) =>{
  notas.value.splice(index,1);
}

const editNota= (nota) => {
  nota.editando =!nota.editando;
}
</script>