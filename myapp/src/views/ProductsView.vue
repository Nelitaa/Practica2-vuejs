<template>
  <div class="container">
    <div class="row">
      <h3> {{ producto.nombre }}</h3>
    </div>
    <div class="row">
      <div class="col-12 col-sm-6 col-md-4">
        <img
          :src="producto.imagen"
          :alt="producto.id"
          class="img-fluid"
        />
      </div>
      <div class="col-12 col-sm-6 col-md-8">
        <h6 v-html="producto.descripcion"></h6>
        <div
          class="p-3 mb-2 text-white"
          :style="configuracionPagina.precioEstilos"
        >
          Precio: {{ producto.precio }} BOB
        </div>
        <h5>Color</h5>

        <div>
          <div
            v-for="color in producto.colores"
            :key="color"
            class="color-box clic"
            :style="{ backgroundColor: color }"
            @click="pickColor(color)"
          ></div>
        </div>
        <h5>Cantidad</h5>
        <div class="quantity">
          <button @click="decrementar()">-</button>
          <div>{{ this.pedido.cantidad }}</div>
          <button @click="incrementar()">+</button>
        </div>
        <div class="buy-box">
          <button
            type="button"
            class="btn btn-primary"
            @click.once="comprar()"
            :disabled="isDisabled"
          >
            Comprar
          </button>
        </div>
      </div>
    </div>
    <RelatedProductsView class="container" :prod="this.productos.filter( product => product.id !== this.producto.id)"/>
  </div>
</template>

<script>
import RelatedProductsView from "@/components/RelatedProductsView.vue";
import axios from "axios";

export default {
  name: "productView",
  data() {
    return {
      producto: {},
      productos: [],
      pedido: {
        id: null,
        cantidad: 1,
        color: null,
      },
      infoValid: false,
      configuracionPagina: {
          precioEstilos: "background: orangered; color: white; font-weight: bold"
      },
    };
  },
  methods: {
    getProductos() {
      axios({
          method: "get",
          url: "http://localhost:3333/productos/",
      })
        .then(response => {
            this.productos = response.data;
            this.producto = this.productos[this.$route.params.id-1];
            this.pedido.id = this.producto.id;
        })
        .catch(e => console.log(e));
    },
    comprar: function () {
      alert(
        ` Id producto es: ${this.pedido.id}\n La cantidad es: ${this.pedido.cantidad}\n El color seleccionado es: ${this.pedido.color}`
      );
    },
    incrementar: function () {
      this.pedido.cantidad++;
    },
    decrementar: function () {
      if (this.pedido.cantidad === 0) return;
      this.pedido.cantidad--;
    },
    pickColor: function (color) {
      if (color) this.pedido.color = color;
    },
  },
  computed: {
    isDisabled: function () {
      return !(this.pedido.cantidad > 0 && this.pedido.color);
    },
  },
  mounted() {
    this.getProductos()
  },
  components: {
    RelatedProductsView,
  },
};
</script>

<style scoped>
.color-box {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin: 7px;
  display: inline-block;
}

.clic {
  cursor: pointer;
}

.quantity button {
  border-radius: 50%;
  display: inline-block;
  width: 30px;
}
.quantity div {
  text-align: center;
  min-width: 30px;
  display: inline-block;
  font-weight: bold;
}
.buy-box {
  margin: 20px;
}
.container {
  margin-top: 50px;
  text-align: left;
}
.producto-relacionado-precio {
  background: orangered;
  color: white;
  text-align: center;
  padding: 10px;
}
</style>
