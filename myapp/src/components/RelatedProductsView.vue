<template>
  <div class="container">
    <div class="row">
      <h4>Productos relacionados</h4>
    </div>
    <div class="row">
      <div
        v-for="product in prod"
        :key="product.id"
        class="col"
        style="cursor: pointer "
        @click="redirect(product.id)"
      >
      <div class="card" style="width: 18rem">
        <div class="card-body">
            <h5 class="card-title">{{ product.nombre }}</h5>
            <img
              :src="product.imagen"
              :alt="product.id"
              class="img-fluid"
            />
            <p class="card-text">
              {{ product.descripcion }}
            </p>
            <div  class="producto-relacionado-precio">Precio:{{ product.precio }} BOB</div>
            <div>
              <div>
                <div
                  v-for="color in product.colores"
                  :key="color"
                  class="color-box"
                  :style="{ backgroundColor: color }"
                ></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "RelatedProductsView",
  props: ['prod'],
  data() {
    return {
    };
  },
  methods: {
    redirect(id) {
      window.location.href = `http://localhost:8080/products/${id}`;
    }
  },
  computed: {},
  mounted() {
  },
  components: {},
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
