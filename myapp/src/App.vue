<template>
  <div>
    <app-menu title="MegaDron"></app-menu>
    <router-view />
    <appFooter />
  </div>
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
</style>
