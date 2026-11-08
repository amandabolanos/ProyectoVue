<script setup>
defineProps({ tarea: { type: Object, required: true }})
defineEmits(['cambiar', 'eliminar'])
</script> 

<template>
  <li>
    <input type="checkbox" :checked="tarea.completa" 
      @change="$emit('cambiar', tarea.id)" />
    <span :class="{ completa: tarea.completa }">{{ tarea.texto }}</span>
    <button @click="$emit('eliminar', tarea.id)">Eliminar</button>
  </li>
</template>

<style scoped>
  .completa {
    text-decoration: line-through;
    color: gray; 
  }

  li {
    grid-column: 1;
    display: grid;
    grid-template-columns: auto 1fr auto;
    align-items: center;
    gap: 8px 10px;
    padding: 14px;
    background: white;
    border: 1px solid #e3e3e3;
    border-radius: 10px;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  }
  
    /* Etiqueta de color debajo del texto */
    li::after {
      content: 'Pendiente';
      grid-column: 2;
      justify-self: start;
      padding: 2px 10px;
      border-radius: 999px;
      background: #fde2c4;
      color: #9a5b13;
      font-size: 12px;
      font-weight: 600;
    }
    li:has(.completa)::after {
      content: 'Completa';
      background: #c9ecd9;
      color: #1f7a4d;
    }
    input[type="checkbox"] {
      appearance: none;
      -webkit-appearance: none;
      width: 18px;
      height: 18px;
      margin: 0;
      border: 1.5px solid #9ca0a4;
      border-radius: 50%;
      cursor: pointer;
    }
    input[type="checkbox"]:checked {
      border-color: #5da283;
      background: #5da283 url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='%23ffffff' stroke-width='3' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpath d='M5 12l5 5 9-10'/%3E%3C/svg%3E") center / 11px no-repeat;
    }
    span {
      font-size: 15px;
    }
    .completa {
      text-decoration: line-through;
      color: #9ca0a4;
    }
    button {
      padding: 4px 10px;
      border: none;
      border-radius: 6px;
      background: #f3f3f3;
      color: #6d6e6f;
      font-size: 12px;
      cursor: pointer;
    }
    button:hover {
      background: #ffe3e3;
      color: #c92a2a;
    }
</style>

