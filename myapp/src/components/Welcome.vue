<template>
  <div class="container">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: "Hello",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  margin-top: 20%;
  text-align: Center;
  height: 40vh;
}
</style>
