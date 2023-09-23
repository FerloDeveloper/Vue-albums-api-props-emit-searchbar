<template>
  <div class="container">
    <img :src="album.poster" alt="Poster">
    <h2>{{ album.title }}</h2>
    <h4>{{ album.author }}</h4>
    <h5>{{ album.year }}</h5>
    <h6>{{ album.genre }}</h6>
  </div>
</template>

<script>
export default {
  name: 'AlbumCard',
  props: {
    album: Object,
  },
};
</script>

<style lang="scss" scoped>
.container {

  background: pink;
  width: 20%;
  padding: 15px;



  img{
    width: 100%;
  } 
}
</style>