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
          { codigo: 40, nombre: 'Dell G5SE', categoria: 'Computadoras', precio: 1000},
          { codigo: 21, nombre: 'Samsung Galaxy S20', categoria: 'Celulares', precio: 1000},
          { codigo: 89, nombre: 'Asus RoG Swift', categoria: 'Monitores', precio: 1000},
          { codigo: 38, nombre: 'Windows 10', categoria: 'Software', precio: 1000}
        ]
      }
    }
  }
</script>

<style>

</style>