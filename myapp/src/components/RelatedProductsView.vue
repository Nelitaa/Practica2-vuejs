<template>
  <div class="container">
    <div class="row">
      <h4>Productos relacionados</h4>
    </div>
    <div class="row">
      <div class="col">
        <div class="card" style="width: 18rem">
          <div class="card-body">
            <h5 class="card-title">KF102</h5>
            <img
              src="https://ae01.alicdn.com/kf/Hd59f72dd965d467dbbd499275a70b1d4z/Dron-plegable-KF102-con-Gps-8K-c-mara-Dual-HD-2-ejes-card-n-Motor-sin.jpg_Q90.jpg_.webp"
              alt=""
              width="100%"
            />
            <p class="card-text">
              Dron plegable KF102 con Gps, 8K, cámara Dual HD, 2 ejes, cardán,
              Motor sin escobillas, fotografía aérea, 1200M de distancia,
              novedad de 2022
            </p>
            <div class="producto-relacionado-precio">Precio:1180 BOB</div>
            <div>
              <div>
                <div class="color-box" style="background: orange"></div>
                <div class="color-box" style="background: blue"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card" style="width: 18rem">
          <div class="card-body">
            <h5 class="card-title">KBDFA-Dron E888 RC</h5>
            <img
              src="https://ae01.alicdn.com/kf/S947d9284b5ea4531a1bec599a09a1f49K/KBDFA-Dron-E888-RC-cuadric-ptero-profesional-FPV-4K-HD-fotograf-a-a-rea-evitaci-n.jpg_Q90.jpg_.webp"
              alt=""
              width="100%"
            />
            <p class="card-text">
              KBDFA-Dron E888 RC, cuadricóptero profesional FPV, 4K
              HD,fotografía aérea, evitación de obstáculos, helicóptero,
              juguetes de distancia
            </p>
            <div class="producto-relacionado-precio">Precio:154 BOB</div>
            <div>
              <div>
                <div class="color-box" style="background: black"></div>
                <div class="color-box" style="background: midnightblue"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card" style="width: 18rem">
          <div class="card-body">
            <h5 class="card-title">Dron Profesional 4K con GPS</h5>
            <img
              src="https://ae01.alicdn.com/kf/S552326188797415ab6c729f850ab2639R/Dron-Profesional-4K-con-GPS-8K-c-mara-HD-3-ejes-card-n-antivibraci-n-evitaci.jpg_Q90.jpg_.webp"
              alt=""
              width="100%"
            />
            <p class="card-text">
              Dron Profesional 4K con GPS, 8K, cámara HD, 3 ejes, cardán
              antivibración, evitación de obstáculos, fotografía aérea,
              Quadcopter, nuevo
            </p>
            <div class="producto-relacionado-precio">Precio:1800 BOB</div>
            <div>
              <div>
                <div class="color-box" style="background: teal"></div>
                <div class="color-box" style="background: blue"></div>
                <div class="color-box" style="background: slategrey"></div>
                <div class="color-box" style="background: navy"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "RelatedProductsView",
  data() {
    return {};
  },
  methods: {},
  computed: {},
  mounted() {},
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
h2 {
}
</style>
