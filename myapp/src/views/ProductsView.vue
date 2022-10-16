<template>
  <div class="container">
    <div class="row">
      <h3>Dron LU3 MAX GPS 8K HD</h3>
    </div>
    <div class="row">
      <div class="col-12 col-sm-6 col-md-4">
        <img
          src="https://ae01.alicdn.com/kf/Sc3cc58f2a441419f970cc01f9e5358fbw/Dron-LU3-MAX-GPS-8K-HD-profesional-con-c-mara-Dual-card-n-autoestabilizador-Motor-sin.jpg_Q90.jpg_.webp"
          alt=""
          width="100%"
        />
      </div>
      <div class="col-12 col-sm-6 col-md-8">
        <h6>
          Dron LU3 MAX GPS 8K HD profesional con <b>cámara Dual</b> cardán
          autoestabilizador, Motor sin escobillas para evitar obstáculos,
          cuadricóptero plegable
        </h6>
        <div
          class="p-3 mb-2 text-white"
          style="background: orangered; color: white; font-weight: bold"
        >
          Precio: 620 BOB
        </div>
        <h5>Color</h5>
        <div>
          <div
            class="color-box clic"
            style="background: red"
            @click="pickColor(color)"
          ></div>
          <div
            class="color-box clic"
            style="background: blue"
            @click="pickColor(color)"
          ></div>
          <div
            class="color-box clic"
            style="background: black"
            @click="pickColor(color)"
          ></div>
          <div
            class="color-box clic"
            style="background: yellow"
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
export default {
  name: "productView",
  data() {
    return {
      pedido: {
        id: null,
        cantidad: 1,
        color: null,
      },
      infoValid: false,
    };
  },
  methods: {
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
  mounted() {},
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
