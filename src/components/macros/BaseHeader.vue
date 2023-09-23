<template>
	<div class="container">
		<i class="fa-solid fa-chess-knight logo"></i>
	</div>
</template>

<script>
export default {
	name: "BaseHeader",
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

	.logo {
		font-size: 2.5rem;
		margin-left: 20px;
		color: rgb(58, 202, 61);
	}
}


</style>
