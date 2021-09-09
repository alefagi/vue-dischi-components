<template>
  <div id="app">
    <Header />
    <main>
      <AlbumContainer>
        <AlbumCard />
      </AlbumContainer>
    </main>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import AlbumContainer from './components/AlbumContainer.vue';
import AlbumCard from './components/AlbumCard.vue';


export default {
  name: 'App',
  components: {
    Header,
    AlbumContainer,
    AlbumCard,
  }
}
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
</style>
