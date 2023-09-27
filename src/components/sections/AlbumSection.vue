<template>
  <div class="container">
    <SearchArea />

    <div class="card-container">
      <AlbumCard
        class="col-12 col-sm-6 col-lg-3"
        v-for="(album, index) in filteredAlbums"
        :key="index"
        :album="album"
      />
    </div>
  </div>
</template>

<script>
import AlbumCard from "../commons/AlbumCard.vue";
import SearchArea from "../commons/SearchArea.vue";
import dataShared from "../../shared/dataShared";
import axios from "axios";

export default {
  name: "AlbumSection",
  components: {
    AlbumCard,
    SearchArea,
  },
  data() {
    return {
      dataShared,
      albums: [],
    };
  },
  computed: {
    filteredAlbums() {
      const searchText = this.dataShared.searchText.toLowerCase();
      const searchGenre = this.dataShared.searchGenre.toLowerCase();

      return this.albums.filter((album) => {
        const titleMatch =
          album.title.toLowerCase().includes(searchText) ||
          searchText === "";

        const genreMatch =
          album.genre.toLowerCase() === searchGenre || searchGenre === "";

        return titleMatch && genreMatch;
      });
    },
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.albums = response.data.response;
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>

<style lang="scss" scoped>
.container {
	display: flex;
	flex-direction: column;

	.card-container {
		display: flex;
		gap: 40px;
		flex-wrap: wrap;
	}
}
</style>
