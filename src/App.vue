<template>
  <div id="app">

    <Cabecera></Cabecera>

    <b-container>
      <b-row>
        <b-col>
          <b-alert show variant="primary">Agregar productos</b-alert>
        </b-col>
    </b-row>
      <b-row>
        <b-col></b-col>
        <b-col>
          <AddProducto v-on:producto-registrado="addProducto" id="add"></AddProducto>
          <br />
          <br />
        </b-col>
        <b-col></b-col>
      </b-row>

      <b-row>
        <b-col>
          <b-alert show variant="primary">Tabla de productos</b-alert>
        </b-col>
      </b-row>
      <Tabla v-bind:productos="productos" id="tab"></Tabla>

      <hr class="my-4" />


      <b-row>
        <b-col>
          <b-alert show variant="primary">Sección de Dashboard</b-alert>
        </b-col>
      </b-row>

      <b-row>
        <b-col>
          <div>
            <b-alert show variant="primary">Gráfica de dona</b-alert>
            <Grafico ref="skills_chart" :chart-data="chartData" :options="options" id="chart"></Grafico>
            <br />
            <br />
            <br />
          </div>
        </b-col>
        <b-col>
          <div>
            <b-alert show variant="primary">Gráfica de linea</b-alert>
            <Grafico2 ref="skills_chart" :chart-data="chartData" :options="options" id="chart2"></Grafico2>
            <br />
            <br />
            <br />
          </div>
        </b-col>
        <b-col>
          <div>
            <b-alert show variant="primary">Gráfica de barra</b-alert>
            <Grafico3 ref="skills_chart" :chart-data="chartData" :options="options" id="chart3"></Grafico3>
            <br />
            <br />
            <br />
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Cabecera from "./components/Cabecera.vue";
import AddProducto from "./components/Crud.vue";
import Grafico from "./components/Grafico.vue";
import Grafico2 from "./components/Grafico2.vue";
import Grafico3 from "./components/Grafico3.vue";
import Tabla from "./components/Tabla.vue";
import randomColor from "randomcolor";
const options = {
  responsive: true,
  maintainAspectRatio: false,
  animation: {
    animateRotate: false
  }
};

export default {
  name: "App",
  components: {
    Cabecera,
    AddProducto,
    Grafico,
    Grafico2,
    Grafico3,
    Tabla
  },

  data() {
    return {
      productos: [],
      options,
      cel: 0,
      mon: 0,
      com: 0,
      soft: 0,
      chartData: {
        labels: ["Celulares", "Monitores", "Computadoras", "Software"],
        datasets: [
          {
            backgroundColor: [
              randomColor(),
              randomColor(),
              randomColor(),
              randomColor()
            ],
            data: [this.cel, this.mon, this.com, this.soft]
          }
        ]
      }
    };
  },
  methods: {
    addProducto(productoAgregado) {
      this.productos = [...this.productos, productoAgregado];

    this.calcValorTotalInventario()

      let chartData = 
      {
        labels: ["Celulares", "Monitores", "Computadoras", "Software"],
        datasets: [
          {
            backgroundColor: [
              randomColor(),
              randomColor(),
              randomColor(),
              randomColor()
            ],
            data: [this.cel, this.mon, this.com, this.soft]
          }
        ]
      }

      this.chartData = chartData;
    },
    calcValorTotalInventario()
    {
      this.cel= 0
      this.mon = 0
      this.com = 0
      this.soft = 0

      for (let index = 0; index < this.productos.length; index++) {
        const element = this.productos[index];
        if(element.categoria == 'Celulares')
          this.cel += element.precio
        else if
        (element.categoria == 'Monitores')
          this.mon += element.precio
        else if
        (element.categoria == 'Computadoras')
          this.com += element.precio
        else
          this.soft += element.precio
      }
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

/* Si desean quitar el patrón: */
background-color: #fff;
background-image:
linear-gradient(90deg, transparent 79px, #abced4 79px, #abced4 81px, transparent 81px),
linear-gradient(#eee .1em, transparent .1em);
background-size: 100% 1.2em;
/* Borrar hasta aquí */
}
</style>
