<template>
	<div class="container">
		<i class="fa-solid fa-chess-knight logo"></i>
		<p v-if="dataShared.searchText">Stai cercando: {{dataShared.searchText}}</p>
		<i class="fa-solid fa-chess-knight logo"></i>
	</div>
</template>

<script>
import dataShared from '@/shared/dataShared';


export default {
	name: "BaseHeader",
	data(){
		return {
			dataShared
		}
	}
};
</script>

<style scoped lang="scss">
//MIXIN
@import "../../assets/style/mixins.scss";

.container {
	height: 5rem;
	background: rgb(78, 78, 78);
	display: flex;
	align-items: center;
	justify-content: space-between;

	.logo {
		font-size: 2.5rem;
		margin-left: 20px;
		color: rgb(58, 202, 61);
	}
}



</style>
