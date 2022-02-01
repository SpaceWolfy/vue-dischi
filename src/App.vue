<template>
  <div id="app">
    <header-box @input="filterSelect" />
    <loading-screen v-if="!isLoading" />
    <main-box v-else :dischi="filterGenre" />
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
      filterGenre: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((result) => {
        this.dischi = result.data.response;
        this.isLoading = true;
        this.filterGenre = result.data.response;
      });
  },
  methods: {
    filterSelect(genre) {
      this.filterGenre = this.dischi.filter((genere) => {
        if (genre === "Tutti") {
          return (this.filterGenre = this.dischi);
        } else {
          return genere.genre.includes(genre);
        }
      });
    },
  },
};
</script>

<style lang="scss">
@import "style/main.scss";
</style>
