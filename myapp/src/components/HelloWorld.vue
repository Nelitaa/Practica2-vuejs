<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>

  <div class="container">
    <div class="row">
      <h3>S6S Mini GPS Drones</h3>
    </div>
    <div class="row">
      <div class="col-12 col-sm-6 col-md-4">
        <img
          src="https://ae01.alicdn.com/kf/S00eb0e55c14f47e2bbf828a92ecd5515U/S6S-Mini-GPS-Drones-150g-Drone-4K-Profesional-HD-Dual-Camera-5G-WIFI-FPV-Brushless-Folding.jpg_Q90.jpg_.webp"
          alt=""
          width="100%"
        />
      </div>
      <div class="col-12 col-sm-6 col-md-8">
        <h6>
          S6S Mini GPS Drones 150g Drone 4K Profesional HD Dual Camera 5G WIFI
          FPV Brushless Folding Quadcopter RC Dron Helicopter Toys
        </h6>
        <div
          class="p-3 mb-2 text-white"
          style="background: orangered; color: white; font-weight: bold"
        >
          Precio: 350 BOB
        </div>
        <h5>Color</h5>
        <div>
          <div class="color-box clic" style="background: red"></div>
          <div class="color-box clic" style="background: blue"></div>
          <div class="color-box clic" style="background: black"></div>
        </div>
        <h5>Cantidad</h5>
        <div class="quantity">
          <button>-</button>
          <div>1</div>
          <button>+</button>
        </div>
        <div class="buy-box">
          <button type="button" class="btn btn-primary">Comprar</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
