<template>
  <header class="d-flex mb-5">
    <i class="fa-brands fa-spotify spotify-logo rounded-circle mt-2"></i>
  </header>
</template>

<script>
export default {
  name: "HeaderComp",
  props: {},
};
</script>

<style scoped lang="scss">
header {
  height: 70px;
  background-color: var(--header-color);
}

.spotify-logo {
  color: #1ed760;
  background-color: black;
  font-size: 2.9em;
  position: absolute;
  top: 2px;
  left: 20px;
}
</style>
