<template>
  <header>
    <img
      src="https://upload.wikimedia.org/wikipedia/commons/1/19/Spotify_logo_without_text.svg"
      alt=""
    />
    <div>
      <select v-model="selected" @change="$emit('input', selected)">
        <option disabled value="">Seleziona un genere</option>
        <option>Tutti</option>
        <option>Rock</option>
        <option>Pop</option>
        <option>Jazz</option>
        <option>Metal</option>
      </select>

      <select v-model="author" @change="$emit('inputArtist', author)">
        <option disabled value="">Seleziona un artista</option>
        <option>Tutti</option>
        <option>Bon Jovi</option>
        <option>Queen</option>
        <option>Sting</option>
        <option>Steve Gadd Band</option>
        <option>Iron Maiden</option>
        <option>Eric Clapton</option>
        <option>Deep Purple</option>
        <option>Metallica</option>
        <option>Dave Weckl</option>
        <option>Michael Jacjson</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      selected: "",
      author: "",
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
  div {
    select {
      background-color: #1e2d3b;
      border: 2px solid #1ed760;
      margin-left: 20px;
      padding: 5px;
      color: white;
      outline: none;
      cursor: pointer;
    }
  }
}
</style>
