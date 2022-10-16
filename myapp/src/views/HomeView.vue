<template>
  <div class="home">
    <Welcome msg="Bienvenido!" />
  </div>
</template>

<script>
// @ is an alias to /src
import Welcome from "@/components/Welcome.vue";

export default {
  name: "HomeView",
  components: {
    Welcome,
  },
};
</script>
