<template>
  <div class="container"><card-box /></div>
</template>

<script>
import CardBox from "./CardBox.vue";
export default {
  components: { CardBox },
};
</script>

<style lang="scss" scoped>
.container {
  width: 1200px;
  margin: 80px auto;
  display: flex;
  flex-wrap: wrap;
}
</style>
