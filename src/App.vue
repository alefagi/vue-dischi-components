<template>
  <div id="app">
    <Header @searchEvent="setCurrentGenre" />
    <main>
      <AlbumContainer :currentGenre="currentGenre"/>
    </main>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import AlbumContainer from './components/AlbumContainer.vue';

export default {
  name: 'App',
  components: {
    Header,
    AlbumContainer,
  },
  data() {
    return {
      currentGenre: 'All',
    }
  },
  methods: {
    setCurrentGenre(currentGenre) {
      this.currentGenre = currentGenre;
    },
  },
}
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
</style>