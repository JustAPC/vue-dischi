<template>
  <div>
    <div class="container" v-if="!loadingStatus">
      <InputGenre @performFilteringByGenre="genreFiltering" />
      <InputArtist @performFilteringByArtist="artistFiltering" />
      <div class="row py-4">
        <SongCard
          v-for="(element, i) in filteredSongList"
          :key="i"
          :poster="element.poster"
          :title="element.title"
          :author="element.author"
          :year="element.year"
        />
      </div>
    </div>
    <div v-else class="loading-screen"><LoadingScreen /></div>
  </div>
</template>

<script>
import axios from "axios";
import SongCard from "./partials/SongCard.vue";
import LoadingScreen from "./partials/LoadingScreen.vue";
import InputGenre from "./partials/InputGenre.vue";
import InputArtist from "./partials/InputArtist.vue";

export default {
  name: "MainComp",
  props: {},
  components: {
    SongCard,
    LoadingScreen,
    InputGenre,
    InputArtist,
  },
  data() {
    return {
      songList: [],
      loadingStatus: true,
      filteredGenre: "",
      filteredArtist: "",
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

  methods: {
    genreFiltering(text) {
      this.filteredGenre = text;
    },

    artistFiltering(text) {
      this.filteredByArtist = text;
    },
  },

  computed: {
    filteredSongList() {
      if (this.filteredGenre === "All") {
        return this.songList;
      }

      return this.songList.filter((elm) => {
        return elm.artist.includes(this.filteredGenre);
      });

      else if (this.filteredArtist === "All") {
        return this.songList;
      }

      return this.songList.filter((elm) => {
        return elm.author.includes(this.filteredArtist);
      });
    },
  },
};
</script>

<style scoped lang="scss"></style>
