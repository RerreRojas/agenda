<template>
    <div>
      <p><strong>Paciente</strong> <br> <br>{{ cita.paciente }} </p>
      <p><strong>Fecha</strong> <br> <br>{{ cita.fecha }} </p>
      <p><strong>Hora</strong> <br> <br> {{ cita.hora }}</p>
      <p><strong>Gravedad</strong> <br> <br> {{ cita.gravedad }}</p>
      <p><strong>Motivo</strong> <br> <br>{{ cita.motivo }}</p>
      <button @click="eliminarCita">Eliminar</button>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      cita: {
        type: Object,
        required: true
      }
    },
    methods: {
      eliminarCita() {
        this.$emit('eliminar');
      }
    }
  };
  </script>
  
  <style scoped>
  /* Estilos personalizados aquí */
  </style>