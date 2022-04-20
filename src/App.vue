<template>
  <div id="app">
    <HeaderComp></HeaderComp>
    <MainComp></MainComp>
  </div>
</template>

<script>
import "bootstrap";
import HeaderComp from "./components/HeaderComp.vue";
import MainComp from "./components/MainComp.vue";

export default {
  name: "App",
  components: {
    HeaderComp,
    MainComp,
  },
};
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
:root {
  --header-color: #2e3a46;
  --body-color: #1e2d3b;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  background-color: var(--body-color);
}

.container {
  width: 62%;
}
</style>
