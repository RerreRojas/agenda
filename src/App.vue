<template>
  <div id="app">
    <h1>Administrador de Citas Médicas</h1>
    <AppointmentForm @agregar="agregarCita" :citas="citas" />
    <hr>
    <AppointmentList :citas="citas" @eliminar="eliminarCita" />
  </div>
</template>
<script>
import AppointmentForm from './components/AppointmentForm.vue';
import AppointmentList from './components/AppointmentList.vue';

export default {
  name: 'App',
  components: {
    AppointmentForm,
    AppointmentList
  },
  data() {
    return {
      citas: []
    };
  },
  methods: {
    agregarCita(nuevaCita) {
      this.citas.push(nuevaCita);
    },
    eliminarCita(index) {
      this.citas.splice(index, 1);
    }
  }
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  margin: 0 auto;
  padding: 20px;
}
h1 {
  text-align: center;
  color: #333;
}
hr {
  margin-top: 20px;
  margin-bottom: 20px;
  border: 0;
  border-top: 1px solid #ccc;
}
</style>
