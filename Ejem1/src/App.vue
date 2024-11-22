<script setup>
const msg="hola!";
const n1 = 33;
const h2color="color:blue";
const activo=false;
const objAttr= {
  id: 'contenedor',
  class: 'rojo',
  style:'background-color: green'
}

const laborables=['lunes', 'martes', 'miercoles','jueves']

const tareas = [
  {nombre: 'desayunar', prioridad: 'baja'},
  {nombre: 'estudiar', prioridad: 'media'},
  {nombre: 'pasear', prioridad: 'baja'}
]
</script>

<template>
<h1>Ejemplos interpolacion</h1>
<h2> {{ msg }} n= {{ n1 }}</h2>    
<h2 :style="h2color">{{ msg }}</h2>
<button :disabled="activo">clica</button>
<div v-bind="objAttr">dadada</div>
<h3 :style="h2color">{{ msg.toLocaleUpperCase() }}</h3>
<h3>{{ activo ? "h2 esta activo" : "h2 esta inactivo" }}</h3>

<h3 v-if="activo">muestra h3 activo</h3>
<h3 v-else-if="activo===null">h3 nulo</h3>
<h3 v-else>muestra h3 innactivo</h3>

<h3 v-show="activo===false">Esto desde v-show</h3>
<br>  
<h2>Renderizado de listas</h2>
<ul>
  <li v-for="dia in laborables">
    {{ dia }}
  </li>
</ul>
<br>
<h2>Array de objetos</h2>
<ul>
  <li v-for="(tarea, index) in tareas">
    {{ index }}-{{ tarea.nombre }} - <small>{{ tarea.prioridad }}</small>
  </li>
</ul>
<br>
<h2>Renderizar objetos</h2>
<ul>
  <li v-for="(valor, clave, index) in objAttr">
    {{ index }} - {{ clave }} - {{ valor }}
  </li>
</ul>

</template>

