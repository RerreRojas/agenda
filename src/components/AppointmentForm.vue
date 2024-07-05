<template>
  <div>
      <form @submit.prevent="agregarCita">
        <div>
          <label :class="{ 'rojo': !paciente }">Paciente:</label>
          <input type="text" v-model="paciente" required>
        </div>
        <div>
          <label :class="{ 'rojo': !fecha }">Fecha:</label>
          <input type="date" v-model="fecha" required>
        </div>
        <div>
          <label :class="{ 'rojo': !hora }">Hora:</label>
          <input type="time" v-model="hora" required>
        </div>
        <div>
          <label :class="{ 'rojo': !gravedad }">Gravedad:</label>
          <select v-model="gravedad" required>
            <option value="">Seleccionar</option>
            <option value="Baja">Baja</option>
            <option value="Media">Media</option>
            <option value="Alta">Alta</option>
          </select>
        </div>
        <div>
          <label :class="{ 'rojo': !motivo }">Motivo:</label>
          <textarea v-model="motivo" required></textarea>
        </div>
        <button type="submit" :disabled="!formularioCompleto">Agregar</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        paciente: '',
        fecha: '',
        hora: '',
        gravedad: '',
        motivo: ''
      };
    },
    props: {
      citas: {
        type: Array,
        required: true
      }
    },
    computed: {
      formularioCompleto() {
        return (
          this.paciente &&
          this.fecha &&
          this.hora &&
          this.gravedad &&
          this.motivo
        );
      }
    },
    methods: {
      agregarCita() {
        const nuevaCita = {
          paciente: this.paciente,
          fecha: this.fecha,
          hora: this.hora,
          gravedad: this.gravedad,
          motivo: this.motivo
        };
        this.$emit('agregar', nuevaCita);
        this.limpiarFormulario();
      },
      limpiarFormulario() {
        this.paciente = '';
        this.fecha = '';
        this.hora = '';
        this.gravedad = '';
        this.motivo = '';
      }
    }
  };
  </script>
  
  <style scoped>
  .rojo {
    color: red;
  }
  </style>
  