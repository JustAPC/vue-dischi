<template>
  <div>
    <div class="container" v-if="!loadingStatus">
      <div class="row py-4">
        <SongCard v-for="(element, i) in songList" :key="i" :poster="element.poster" :title="element.title" :author="element.author" :year="element.year" />
      </div>
    </div>
    <div v-else class="loading-screen"><LoadingScreen /></div>
  </div>
</template>

<script>
import axios from "axios";
import SongCard from "./SongCard.vue";
import LoadingScreen from "./LoadingScreen.vue";

export default {
  name: "MainComp",
  props: {},
  components: {
    SongCard,
    LoadingScreen,
  },
  data() {
    return {
      songList: [],
      loadingStatus: true,
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.songList = res.data.response;
        console.log(this.songList);
        this.loadingStatus = false;
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>

<style scoped lang="scss"></style>
