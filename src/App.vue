<template>
  <div id="app">
    <header-box @input="filterSelect" @inputArtist="filterSelectArtist" />
    <loading-screen v-if="!isLoading" />
    <main-box v-else :dischi="filterForCategory" />
  </div>
</template>

<script>
import axios from "axios";
import HeaderBox from "./components/HeaderBox.vue";
import MainBox from "./components/MainBox.vue";
import LoadingScreen from "./components/LoadingScreen.vue";

export default {
  name: "App",
  components: { HeaderBox, MainBox, LoadingScreen },
  data() {
    return {
      dischi: [],
      isLoading: false,
      filterForCategory: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((result) => {
        this.dischi = result.data.response;
        this.isLoading = true;
        this.filterForCategory = result.data.response;
      });
  },
  methods: {
    filterSelect(genre) {
      this.filterForCategory = this.dischi.filter((genere) => {
        if (genre === "Tutti") {
          return (this.filterForCategory = this.dischi);
        } else {
          return genere.genre.includes(genre);
        }
      });
    },
    filterSelectArtist(author) {
      this.filterForCategory = this.dischi.filter((autore) => {
        if (author === "Tutti") {
          return (this.filterForCategory = this.dischi);
        } else {
          return autore.author.includes(author);
        }
      });
    },
  },
};
</script>

<style lang="scss">
@import "style/main.scss";
</style>
