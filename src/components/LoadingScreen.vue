<template>
  <div class="loading-screen">Stiamo caricando la tua musica!</div>
</template>

<script>
export default {
  name: "LoadingScreen",
  props: {},
};
</script>

<style scoped lang="scss">
div {
  display: flex;
  justify-content: center;
  align-content: center;
  color: white;
  height: 100vh;
  width: 100vw;
}
</style>
