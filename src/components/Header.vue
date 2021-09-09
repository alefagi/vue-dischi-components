<template>
  <header>
    <div class="container">
      <img src="../assets/images/logo.png" />
      <div>
        <label for="genre">Seleziona un genere: </label>
        <select name="genre" id="genre" v-model="currentGenre" @change="$emit('searchEvent', currentGenre)">
          <option :value="genre" v-for="(genre, index) in reducedGenres" :key="index">{{ genre }}</option>
        </select>
      </div>
    </div>
  </header>  
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      currentGenre: 'All',
      reducedGenres: ['All', 'Rock', 'Pop', 'Jazz', 'Metal'],
    }
  },
}
</script>

<style scoped lang="scss">
@import "../assets/scss/_header.scss";

</style>