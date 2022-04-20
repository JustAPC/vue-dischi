<template>
  <div class="card-width mb-3">
    <img :src="poster" alt="" class="pt-3" />
    <h5 style="text-transform: uppercase" class="py-3">{{ title }}</h5>
    <p>{{ author }}</p>
    <p class="pb-3">{{ year }}</p>
  </div>
</template>

<script>
export default {
  name: "SongCard",
  props: {
    poster: String,
    title: String,
    author: String,
    genre: String,
    year: String,
  },
};
</script>

<style scoped lang="scss">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.card-width {
  width: calc((100% / 5) - 34px);
  margin: 0 17px;
  background-color: #2e3a46;
}

img {
  width: 161px;
}

div p {
  color: #5e7780;
}

h5 {
  color: white;
  font-weight: bold;
}
</style>
