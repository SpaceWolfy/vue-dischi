<template>
  <div id="app"><header-box /></div>
</template>

<script>
import axios from "axios";
import HeaderBox from "./components/HeaderBox.vue";

export default {
  name: "App",
  components: { HeaderBox },
  data() {
    return {
      dischi: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((result) => {
        this.dischi = result.data;
      });
  },
};
</script>

<style lang="scss">
@import "style/main.scss";
</style>
