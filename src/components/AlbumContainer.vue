<template>
  <section id="album-container">
    <div v-for="(album, index) in albumList" :key="index">
      <AlbumCard :album="album" v-if="currentGenre === album.genre || currentGenre === 'All'"/>
    </div>
  </section>
</template>

<script>
import axios from 'axios';
import AlbumCard from '../components/AlbumCard.vue';

export default {
  name: 'AlbumContainer',
  components: {
    AlbumCard,
  },
  props: ['currentGenre'],
  data() {
    return {
      albumList: [],
    }
  },
  computed: {
    /* sortedAlbumList() {
      return this.albumList.sort(function(a, b){
        return b.year-a.year});
    }, */
    /* reducedGenres() {
      const reducedGenres = ['All'];
      this.albumList.forEach((album) => {
        if(!reducedGenres.includes(album.genre)) {
          reducedGenres.push(album.genre);
        }
      });
      return reducedGenres;
    }, */
  },
  created() {
    axios
      .get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((res) => {
        this.albumList = res.data.response;
      });
  },
}
</script>

<style scoped lang="scss">
  #album-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
</style>