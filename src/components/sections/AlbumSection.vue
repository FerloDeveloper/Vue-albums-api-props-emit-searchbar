<template>
	<div class="container">
		<SearchArea @searching="dataShared.searchText" />

		<div class="card-container">
			<AlbumCard
				class="col-12 col-sm-6 col-lg-3"
				v-for="(album, index) in AlbumFiltered"
				:key="index"
				:album="album"
			/>
		</div>
	</div>
</template>

<script>
import AlbumCard from "../commons/AlbumCard.vue";
import SearchArea from "../commons/SearchArea.vue";
import dataShared from "../../shared/dataShared"
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
		AlbumFiltered() {
			return this.albums.filter((album) =>
				album.title.toLowerCase().includes(this.dataShared.searchText.toLowerCase())
			);
		},
	},
	created() {
		axios
			.get("https://flynn.boolean.careers/exercises/api/array/music")
			.then((response) => {
				this.albums = response.data.response;
				// this.AlbumFiltered = response.data.response;
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
