<template>
  <div class="container">
    <card-box v-for="(disco, index) in dischi" :key="index" :disco="disco" />
  </div>
</template>

<script>
import CardBox from "./CardBox.vue";
export default {
  components: { CardBox },
  props: {
    dischi: Array,
  },
};
</script>

<style lang="scss" scoped>
.container {
  width: 1200px;
  margin: 70px auto;
  display: flex;

  flex-wrap: wrap;
}
</style>
