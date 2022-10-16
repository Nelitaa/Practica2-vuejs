<template>
  <app-menu title="MegaDron"></app-menu>
  <router-view />
  <footer style="background-color: Slategrey"></footer>
</template>

<script>
import AppMenu from "@/components/AppMenu.vue";
import AppFooter from "@/components/AppFooter.vue";
export default {
  name: "app",
  data() {
    return {};
  },
  methods: {},
  computed: {},
  mounted() {},
  components: {
    AppMenu,
    AppFooter,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

footer {
  text-align: center;
  padding: 30px 10px;
  margin-top: 50px;
  min-height: 100px;
}
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
}
.producto-relacionado-precio {
  background: orangered;
  color: white;
  text-align: center;
  padding: 10px;
}
</style>
