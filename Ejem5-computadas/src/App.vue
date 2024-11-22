<template>
  <h1>
PROPIEDADES COMPUTADAS
  </h1>
<input type="text" placeholder="nombre" v-model="nombre">
<input type="text" placeholder="apellido" v-model="apellido">
<input type="number" placeholder="birthDate" v-model="birthDate">
<br><br>

<p><Strong>Nombre: {{ nombreCompleto }}</Strong></p>
<p><Strong>Años: {{ edad }}</Strong></p>
</template>

<script setup>
import {ref, computed} from 'vue'

const nombre=ref('')
const apellido=ref('')
const birthDate=ref(2002)

const nombreCompleto=computed(()=>
`${nombre.value}  ${apellido.value}` .toUpperCase()
)

const edad=computed(()=>{
  let actual= new Date().getFullYear();
  return actual-birthDate.value
})

</script>