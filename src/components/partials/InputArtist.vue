<template>
  <div id="artist-selector">
    <form>
      <span class="text-white me-3">Choose an artist:</span>
      <select
        v-model="selectedArtist"
        class="me-3"
        @click.prevent="$emit('performFilteringByArtist', selectedArtist)"
      >
        <option disabled value="all">Choose an artist</option>
        <option>All</option>
        <option>Bon Jovi</option>
        <option>Queen</option>
        <option>Sting</option>
        <option>Steve Gadd Band</option>
        <option>Iron Maiden</option>
        <option>Eric Clapton</option>
        <option>Deep Purple</option>
        <option>Metallica</option>
        <option>Dave Weckl</option>
        <option>Michael Jacjson</option>
      </select>
    </form>
  </div>
</template>

<script>
export default {
  name: "InputArtist",
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
#artist-selector {
  position: absolute;
  top: 20px;
  right: 40%;
}
select {
  padding: 5px 0;
}
</style>
