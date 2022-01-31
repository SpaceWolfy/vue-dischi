<template>
  <div id="app">
    <loading-screen :isLoading="isLoading" />
    <div v-if="!isLoading">
      <header-box />
      <main-box :dischi="dischi" />
    </div>
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
      isLoading: true,
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((result) => {
        this.dischi = result.data.response;
      });

    setTimeout(() => {
      this.isLoading = false;
    }, 3000);
  },
};
</script>

<style lang="scss">
@import "style/main.scss";
</style>
