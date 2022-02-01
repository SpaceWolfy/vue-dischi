<template>
  <div id="app">
    <header-box />
    <loading-screen v-if="!isLoading" />
    <main-box v-else :dischi="dischi" />
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
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((result) => {
        this.dischi = result.data.response;
        this.isLoading = true;
      });
  },
};
</script>

<style lang="scss">
@import "style/main.scss";
</style>
