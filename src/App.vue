<template>
  <TestHome />
</template>

<script>
import TestHome from "./views/TestHome.vue";
export default {
  name: "App",
  components: {
    TestHome,
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
  margin-top: 60px;
}
</style>
