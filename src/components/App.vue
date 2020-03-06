<template>
  <div id="app">
    <Cabecera></Cabecera>
    <b-container>
      <b-row>
        <b-col></b-col>
        <b-col>
          <AddProducto v-on:producto-registrado="addProducto"></AddProducto>
        </b-col>
        <b-col></b-col>
      </b-row>

      <Tabla :productos="productos"></Tabla>
      <Grafico :productos="productos"></Grafico>
    </b-container>
  </div>
</template>

<script>
import Cabecera from "./components/Cabecera.vue";
import AddProducto from "./components/Crud.vue";
import Grafico from "./components/Grafico.vue";
import Tabla from "./components/Tabla.vue";

export default {
  name: "App",
  components: {
    Cabecera,
    AddProducto,
    Grafico,
    Tabla
  },

  data() {
    return {
      productos: []
    };
  },

  methods: {
    addProducto(productoAgregado) {
      this.productos = [...this.productos, productoAgregado];
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
