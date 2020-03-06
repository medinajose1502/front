<template>
  <div>
  <br>
  <br>
    <b-form-input id="input-1" v-model="keyword" type="text" placeholder="Buscar"></b-form-input>
    <b-table :items="items" :fields="fields" :keyword="keyword" :sort-by.sync="sortBy" :sort-desc.sync="sortDesc" sort-icon-leftstriped hover></b-table>
  <br>
  <br>
  </div>

</template>

<script>
  export default {
    data() {
      return {
        keyword: '',
        sortBy: 'id',
        sortDesc: false,
        fields: [
          { key: 'id', sortable: true },
          { key: 'nombre', sortable: true },
          { key: 'precio', sortable: true },
          { key: 'categoria', sortable: true }
        ],
        data: [
          { id: '1', nombre: 'Dell G5SE', precio: '900', categoria: 'Computadoras' },
          { id: '2', nombre: 'Samsung Galaxy S20', precio: '1400', categoria: 'Celulares' },
          { id: '3', nombre: 'Asus RoG Swift', precio: '2500', categoria: 'Monitores' },
          { id: '4', nombre: 'Windows 10 Pro', precio: '100', categoria: 'Software' }
        ]
      }
    },
    computed: 
    {
        items() 
        {
            return this.keyword ? this.data.filter(item => String(item.id).includes(this.keyword) ||
             item.nombre.includes(this.keyword) || String(item.precio).includes(this.keyword) ||
              item.categoria.includes(this.keyword)) : this.data
        }
  }
}
</script>

<style>

</style>