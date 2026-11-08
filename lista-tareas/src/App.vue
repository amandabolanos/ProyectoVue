<script setup>
  import { ref } from 'vue'
  import TareaItem from './components/TareaItem.vue'  

  const nuevaTarea = ref('') 
  const tareas = ref([]) 
  let siguienteId = 1 

  function agregarTarea() { 
    if (nuevaTarea.value.trim() === '') return
      tareas.value.push({
        id: siguienteId++,
        texto: nuevaTarea.value,
        completa: false
      })
      nuevaTarea.value = ''
  }

  function cambiarEstado(id) { 
    const tarea = tareas.value.find(t => t.id === id)
      tarea.completa = !tarea.completa
  } 

  function eliminarTarea(id) {
    tareas.value = tareas.value.filter(t => t.id !== id) 
  }
</script> 

<template>
  <h1>Mis tareas</h1> 

  <form @submit.prevent="agregarTarea">
    <input v-model="nuevaTarea"
          placeholder="Escribe una tarea" />
    <button>Agregar</button> 
  </form>

  <p v-if="tareas.length === 0">
    No hay tareas todavía 
  </p> 
  <ul>
    <TareaItem 
      v-for="tarea in tareas" 
      :key="tarea.id" 
      :tarea="tarea" 
      @cambiar="cambiarEstado" 
      @eliminar="eliminarTarea"
    />
  </ul>

</template>


