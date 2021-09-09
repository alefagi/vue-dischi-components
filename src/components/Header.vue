<template>
  <header>
        <div class="container">
          <img src="../assets/images/logo.png" />

          <div>
            <label for="genre">Seleziona un genere: </label>
            <select name="genre" id="genre" @change="setCurrentGenre">
              <option :value="genre" v-for="(genre, index) in reducedGenres" :key="index">{{ genre }}</option>
            </select>
          </div>
        </div>
      </header>  
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style>
@import "../assets/scss/_header.scss";

</style>