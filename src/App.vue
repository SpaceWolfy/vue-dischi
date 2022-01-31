<template>
  <div id="app">
    <header-box />
    <main-box :dischi="dischi" />
  </div>
</template>

<script>
import axios from "axios";
import HeaderBox from "./components/HeaderBox.vue";
import MainBox from "./components/MainBox.vue";

export default {
  name: "App",
  components: { HeaderBox, MainBox },
  data() {
    return {
      dischi: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((result) => {
        this.dischi = result.data.response;
      });
  },
};
</script>

<style lang="scss">
@import "style/main.scss";
</style>
