# Agenda tu hora al médico

## Descripción
Este proyecto es un administrador de citas médicas desarrollado con Vue.js. Permite a los usuarios agregar y eliminar citas mediante un formulario interactivo y una lista de citas.

### Estructura del Proyecto
El proyecto está compuesto por los siguientes archivos principales:

* App.vue: Componente principal que maneja el estado y la lógica de las citas.
* AppointmentForm.vue: Componente de formulario para agregar nuevas citas.
* AppointmentList.vue: Componente para listar y eliminar citas.
* AppointmentCard.vue Componente que contiene las cards

### App.vue

Este es el archivo principal del proyecto. Se encarga de mantener el estado global de las citas y de coordinar los componentes secundarios.

### AppointmentForm.vue

Este componente contiene el formulario para agregar nuevas citas. Emite un evento agregar con los datos de la nueva cita cuando se envía el formulario.

### AppointmentList.vue

Este componente se encarga de mostrar la lista de citas y proporcionar la funcionalidad para eliminarlas. Cada cita se muestra con sus detalles y un botón para eliminarla.

