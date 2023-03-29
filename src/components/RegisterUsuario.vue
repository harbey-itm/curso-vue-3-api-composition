<script setup></script>

<template>
  <div class="container">
    <form>
      <div class="mb-3">
        <label for="name" class="form-label">Nombres y Apellidos</label>
        <input type="text" class="form-control" id="name">
      </div>
      <div class="mb-3">
        <label for="email" class="form-label">Correo Electrónico</label>
        <input type="email" class="form-control" id="email" aria-describedby="emailHelp">
      </div>
      <div class="mb-3">
        <label for="password" class="form-label">Contraseña</label>
        <input type="password" class="form-control" id="password">
      </div>
      <div class="mb-3">
        <label for="confirmPassword" class="form-label">Confirmar Contraseña</label>
        <input type="password" class="form-control" id="confirmPassword">
      </div>
      <button type="submit" class="btn btn-primary">Registrar Usuario</button>
      <button type="button" class="btn btn-secondary">Cancelar</button>
    </form>
  </div>
</template>