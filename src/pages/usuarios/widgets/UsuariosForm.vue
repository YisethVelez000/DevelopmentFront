<template>
    <div>
      <h2>{{ titulo }} Usuario</h2>
  
      <form @submit.prevent="guardarUsuario">
        <div class="form-group">
          <label for="nombreCompleto">Nombre Completo:</label>
          <input type="text" id="nombreCompleto" v-model="usuario.nombreCompleto" class="form-control">
        </div>
  
        <div class="form-group">
          <label for="correoElectronico">Correo Electrónico:</label>
          <input type="email" id="correoElectronico" v-model="usuario.correoElectronico" class="form-control">
        </div>
  
        <div class="form-group">
          <label for="contrasena">Contraseña:</label>
          <input type="password" id="contrasena" v-model="usuario.contrasena" class="form-control">
        </div>
  
        <div class="form-group">
          <label for="rol">Rol:</label>
          <select id="rol" v-model="usuario.rol" class="form-control">
            <option value="admin">Administrador</option>
            <option value="usuario">Usuario</option>
          </select>
        </div>
  
        <button type="submit" class="btn btn-primary">{{ tituloBoton }}</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      usuario: Object, // Prop para recibir el objeto de usuario a editar o crear
    },
    data() {
      return {
        titulo: 'Crear', // Título del formulario (cambia a "Editar" si se edita)
        tituloBoton: 'Crear Usuario', // Texto del botón de envío
      };
    },
    methods: {
      guardarUsuario() {
        // Implementar la lógica para guardar el usuario (ya sea creando uno nuevo o editando uno existente)
      }
    }
  };
  </script>
  