<template>
  <h1>VACIO

  </h1>
  <button v-on:click="mensajeConsola">
    Pulsame
  </button>
  <button @click="mensajeConsola">
    Pulsame otro
  </button>
  <form>
    <input type="text" @keydown="teclaPulsado">
    <input type="submit" @keydown.enter="submitPulsado">
  </form>

<button @click="mensajeConsola2('Este mensaje va como parametro')">Click izq</button>
<button @click.middle="mensajeCentral">Click central</button>
<button @click.right.prevent="mensajeDerecho">Click derecho</button>
</template>

<script setup>
const mensajeConsola = () => {
  alert("Has dado click al boton");
}
function teclaPulsado(event) {
  console.log(event.key);
}

const submitPulsado = () => {
  alert("clicaste al submit");
}

const mensajeConsola2 = () => {
  alert("Has dado click al boton izquierdo");
}

const mensajeCentral = () => {
  alert("Has dado click al boton central");
}
const mensajeDerecho = () => {
  alert("Has dado click al boton derecho");
}
</script>