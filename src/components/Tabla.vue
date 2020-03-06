<template>
  <div>
    <br />
    <br />
    <b-form-input id="input-1" v-model="keyword" type="text" placeholder="Buscar"></b-form-input>
    <b-table
      :items="items"
      :fields="fields"
      :keyword="keyword"
      :sort-by.sync="sortBy"
      :sort-desc.sync="sortDesc"
      sort-icon-leftstriped
      hover
    ></b-table>
    <br />
    <br />
  </div>
</template>

<script>
export default {
  props: {
    productos: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      keyword: "",
      sortBy: "id",
      sortDesc: false,
      fields: [
        { key: "id", sortable: true },
        { key: "nombre", sortable: true },
        { key: "precio", sortable: true },
        { key: "categoria", sortable: true }
      ]
    };
  },
  computed: {
    items() {
      return this.keyword
        ? this.productos.filter(
            item =>
              String(item.id).includes(this.keyword) ||
              item.nombre.includes(this.keyword) ||
              String(item.precio).includes(this.keyword) ||
              item.categoria.includes(this.keyword)
          )
        : this.productos;
    }
  }
};
</script>

<style>
</style>