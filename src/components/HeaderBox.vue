<template>
  <header>
    <img
      src="https://upload.wikimedia.org/wikipedia/commons/1/19/Spotify_logo_without_text.svg"
      alt=""
    />

    <select v-model="selected" @click="$emit('input', selected)">
      <option disabled value="">Seleziona un genere</option>
      <option>Tutti</option>
      <option>Rock</option>
      <option>Pop</option>
      <option>Jazz</option>
      <option>Metal</option>
    </select>
  </header>
</template>

<script>
export default {
  data() {
    return {
      selected: "",
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: #2e3a46;
  height: 70px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;

  img {
    height: 45px;
    background-color: #191716;
    border-radius: 50%;
  }

  select {
    background-color: #1e2d3b;
    border: 2px solid #1ed760;
    padding: 5px;
    color: white;
    outline: none;
    cursor: pointer;
  }
}
</style>
