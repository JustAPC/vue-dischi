<template>
  <div>
    <div class="loading-screen"><LoadingScreen /></div>
    <div class="container">
      <div class="row py-4">
        <SongCard v-for="(element, i) in songList" :key="i" :poster="element.poster" :title="element.title" :author="element.author" :year="element.year" />
      </div>
    </div>
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
    };
  },
  created() {
    this.loadScreen();

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

  methods: {
    loadScreen: function () {
      let loadingScreen = document.getElementsByClassName("loading-screen");
      if (this.songList.length != this.res.data.response.length) {
        loadingScreen.style.display = "block";
      } else {
        loadingScreen.style.display = "none";
      }
    },
  },
};
</script>

<style scoped lang="scss"></style>
