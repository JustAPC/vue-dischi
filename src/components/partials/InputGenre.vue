<template>
  <div>
    <div id="genre-selector">
      <form>
        <span class="text-white me-3">Choose a genre:</span>
        <select
          v-model="selectedGenre"
          class="me-3"
          @click.prevent="$emit('performFilteringByGenre', selectedGenre)"
        >
          <option disabled value="all">Choose a genre</option>
          <option>All</option>
          <option>Rock</option>
          <option>Pop</option>
          <option>Jazz</option>
          <option>Metal</option>
        </select>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "InputGenre",
  props: {},
};
</script>

<style scoped lang="scss">
#genre-selector {
  position: absolute;
  top: 20px;
  right: 5px;
}
</style>
