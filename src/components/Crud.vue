<template>
  <div>
    <b-card>
      <b-form @submit="addProducto">
        <b-form-group
          id="input-group-1"
          label="Código:"
          label-for="input-1"
          description="Código del producto."
        >
          <b-form-input
            onkeypress="return solonum(event)"
            id="input-1"
            v-model="id"
            type="text"
            placeholder="Ingrese código"
          ></b-form-input>
        </b-form-group>

        <b-form-group
          id="input-group-1"
          label="Nombre:"
          label-for="input-1"
          description="Nombre del producto."
        >
          <b-form-input
            onkeypress="return sololetra(event)"
            id="input-1"
            v-model="nombre"
            type="text"
            placeholder="Ingrese nombre"
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-3" label="Categoria:" label-for="input-3">
          <b-form-select id="input-3" v-model="categoria" :options="categorias"></b-form-select>
        </b-form-group>

        <b-form-group
          id="input-group-1"
          label="Precio"
          label-for="input-1"
          description="Precio del producto."
        >
          <b-form-input
            onkeypress="return solonum(event)"
            id="input-1"
            v-model.number="precio"
            type="text"
            placeholder="Ingrese el precio"
          ></b-form-input>
        </b-form-group>
        <ul>
          <li v-for="error in errores" v-bind:key="error">{{ error }}</li>
        </ul>
        <b-button type="reset" variant="danger">Limpiar</b-button>
        <br />
        <br />
        <b-button type="submit" variant="primary" value="submit">Agregar producto</b-button>
      </b-form>
    </b-card>
  </div>
</template>


<script>
export default {
  name: "AddProducto",
  data() {
    return {
      id: "",
      nombre: "",
      categoria: "",
      precio: null,

      categorias: ["Celulares", "Monitores", "Computadoras", "Software"],
      errores: []
    };
  },
  methods: {
    addProducto(e) {
      e.preventDefault();
      if (this.id && this.nombre && this.categoria && this.precio) {
        this.errores = [];
        const productoAgregado = {
          id: this.id,
          nombre: this.nombre,
          categoria: this.categoria,
          precio: this.precio
        };
        if (this.id && this.precio)
          this.$emit("producto-registrado", productoAgregado);
        this.id = null;
        this.nombre = null;
        this.categoria = null;
        this.precio = null;
      } else {
        if (this.id.length == 0) this.errores.push("Debe ingresar un código.");
        if (this.nombre.length == 0)
          this.errores.push("Debe ingresar un nombre para el producto.");
        if (this.categoria.length == 0)
          this.errores.push("Debe selecciona una categoria.");
        if (this.precio == null) this.errores.push("Debe ingresar un precio.");
      }
    }
  }
};
</script>
<style>
</style>