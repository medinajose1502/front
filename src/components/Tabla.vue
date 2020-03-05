<template>
  <div>
  <br>
  <br>
    <b-table striped hover :items="items"></b-table>
  <br>
  <br>
  </div>

</template>

<script>
  export default {
    data() {
      return {
        items: [
          { codigo: 40, nombre: 'Dickerson', categoria: 'Macdonald', precio: 1000},
          { codigo: 21, nombre: 'Larsen', categoria: 'Shaw', precio: 1000},
          { codigo: 89, nombre: 'Geneva', categoria: 'Wilson', precio: 1000},
          { codigo: 38, nombre: 'Jami', categoria: 'Carney', precio: 1000}
        ]
      }
    }
  }
</script>

<style>

</style>