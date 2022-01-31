<template>
  <div class="card-box">
    <img :src="disco.poster" alt="" />

    <h2>{{ disco.title.toUpperCase() }}</h2>

    <div class="name">{{ disco.author }}</div>
    <div class="date">{{ disco.year }}</div>
  </div>
</template>

<script>
export default {
  props: {
    disco: Object,
  },
};
</script>

<style lang="scss" scoped>
.card-box {
  height: 365px;
  width: 200px;
  margin: 10px 20px;
  background-color: #2e3a46;
  display: flex;
  align-items: center;
  flex-direction: column;

  img {
    /* height: 150px; */
    width: 160px;
    margin: 20px 0;
  }

  h2 {
    color: white;
    text-align: center;
    width: 160px;
    font-size: 22px;
    padding-bottom: 25px;
  }

  .name {
    font-size: 19px;
    padding-bottom: 4px;
  }

  .name,
  .date {
    color: #808080;
  }
}
</style>
