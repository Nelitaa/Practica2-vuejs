<template>
  <div></div>
</template>

<script>

export default {
  name: "HomeView",
  components: {
  },
  mounted(){
    window.location.href = `http://localhost:8080/products?id=1`;
},
};
</script>
