<template>
  <h1>
    REACTIVIDAD
  </h1>
  <p >Contador:{{ contador }}</p>
  <button @click="incrementar">+</button>
  <button @click="disminuir">-</button>
  <button @click="reset">Reset</button>
</template>

<script setup>
import { ref, computed } from 'vue';

const count = ref(0);

function incrementar() {
  contador.value++;
}

const disminuir = () => {
  contador.value--;
};

const reset = () => {
  contador.value = 0;
};

// Computed para determinar la clase según el valor del contador
const contadorColor = computed(() => {
  return contador.value < 0 ? 'negativo' : 'positivo';
});
</script>

<style scoped>
/* Estilo para el contador positivo o cero */
.positivo {
  color: green;
  font-weight: bold;
}

/* Estilo para el contador negativo */
.negativo {
  color: red;
  font-weight: bold;
}

button:hover {
  background-color: #e0e0e0;
}
</style>