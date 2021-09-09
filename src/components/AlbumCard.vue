<template>
  <div class="card">
    <img :src="album.poster" :alt="album.title" />
    <h2 class="title">{{ album.title }}</h2>
    <address class="author">{{ album.author }}</address>
    <time :datetime="album.year" class="year">{{ album.year }}</time>
  </div>
</template>

<script>
export default {
  name: 'AlbumCard',
  props: ['album'],
}
</script>

<style scoped lang="scss">
@import "../assets/scss/_album.scss";
</style>