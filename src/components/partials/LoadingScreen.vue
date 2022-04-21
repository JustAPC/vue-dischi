<template>
  <h1 class="loading-screen">Stiamo caricando la tua musica!</h1>
</template>

<script>
export default {
  name: "LoadingScreen",
  props: {},
};
</script>

<style scoped lang="scss">
h1 {
  display: flex;
  justify-content: center;
  align-content: center;
  color: white;
  height: 100vh;
  width: 100vw;
  position: absolute;
  top: 50%;
  left: 0%;
}
</style>
