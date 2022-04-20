<template>
  <div class="container">
    <div class="row py-4">
      <SongCard v-for="(element, i) in songList" :key="i" :poster="element.poster" :title="element.title" :author="element.author" :year="element.year" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import SongCard from "./SongCard.vue";

export default {
  name: "MainComp",
  props: {},
  components: {
    SongCard,
  },
  data() {
    return {
      songList: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.songList = res.data.response;
        console.log(this.songList);
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>

<style scoped lang="scss"></style>
