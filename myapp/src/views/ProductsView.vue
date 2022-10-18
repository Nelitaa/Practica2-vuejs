<template>
  <div class="container">
    <div class="row">
      <h3> {{pageProduct?.nombre}}</h3>
    </div>
    <div class="row">
      <div class="col-12 col-sm-6 col-md-4">
        <img
          :src="pageProduct?.imagen"
          alt=""
          class="img-fluid"
        />
      </div>
      <div class="col-12 col-sm-6 col-md-8">
        <h6>
         {{pageProduct?.descripcion}}
        </h6>
        <div
          class="p-3 mb-2 text-white"
          style="background: orangered; color: white; font-weight: bold"
        >
          Precio: {{ pageProduct?.precio }} BOB
        </div>
        <h5>Color</h5>

        <div>
          <div
            v-for="color in pageProduct?.colores"
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
  </div>
  <RelatedProductsView class="container" />
</template>

<script>
import RelatedProductsView from "@/components/RelatedProductsView.vue";
import axios from "axios";

export default {
  name: "productView",
  data() {
    return {
      productos: [],
      pedido: {
        id: null,
        cantidad: 1,
        color: null,
      },
      pageProduct: null,
      infoValid: false,
    };
  },
  methods: {
    getProductos() {
      axios({
          method: "get",
          url: "http://localhost:3333/productos",
      })
          .then(response => {
              this.productos = response.data;
              const productFound = this.productos.find(
                  (product) => product.id == this.$route.query.id
              );
              if(!productFound) {
                this.pageProduct = this.productos[0];
              } else {
                this.pageProduct = productFound;
              }
              this.pedido.id = this.pageProduct.id;
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
      // log color variable
      console.log(color);
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
