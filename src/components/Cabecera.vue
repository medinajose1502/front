<template>
  <div>
  <b-navbar type="dark" variant="dark">
    <b-navbar-nav>
      <b-nav-item href="#">Inicio</b-nav-item>

      <!-- Navbar dropdowns -->
      <b-nav-item-dropdown text="Secciones" right>
        <b-dropdown-item href="#">Mini-crud</b-dropdown-item>
        <b-dropdown-item href="#">Gráfico</b-dropdown-item>
        <b-dropdown-item href="#">Tabla</b-dropdown-item>
      </b-nav-item-dropdown>
    </b-navbar-nav>
  </b-navbar>
  <div>

  <b-jumbotron>
    <template v-slot:header>Gestión de inventario</template>

    <template v-slot:lead>
      Esta es una pequeña aplicación para demostrar el uso del framework Vue.js
    </template>

    <hr class="my-4">

    <b-button variant="primary" disabled>By Teamy McTeamface</b-button>
  </b-jumbotron>
</div>
</div>
</template>

<script>

</script>

<style>

</style>