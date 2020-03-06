<template>
  <div>
    <div>
      <b-navbar toggleable="lg" type="dark" variant="primary">
        <b-navbar-brand href="#">Teamy McTeamface</b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-item-dropdown text="Secciones" right>
              <b-dropdown-item href="#add">Añadir producto</b-dropdown-item>
              <b-dropdown-item href="#tab">Tabla</b-dropdown-item>
              <b-dropdown-item href="#chart1">Gráfico 1</b-dropdown-item>
              <b-dropdown-item href="#chart2">Gráfico 2</b-dropdown-item>
              <b-dropdown-item href="#chart3">Gráfico 3</b-dropdown-item>
            </b-nav-item-dropdown>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>

    <div>
      <b-jumbotron>
        <template v-slot:header>El inventario</template>

        <template
          v-slot:lead
        >Esta es una pequeña aplicación para demostrar el uso del framework Vue.js, Bootstrap-vue, Chartsjs-vue, RandomColor</template>

        <hr class="my-4" />

        <b-button variant="primary" disabled>By Teamy McTeamface</b-button>
      </b-jumbotron>
    </div>
  </div>
</template>

<script>
</script>

<style>
</style>