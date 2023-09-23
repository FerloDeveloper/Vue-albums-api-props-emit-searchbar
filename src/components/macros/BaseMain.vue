<template>
	<div class="container">
    <AlbumSection/>
	</div>
</template>

<script>

import AlbumSection from '../sections/AlbumSection.vue'


export default {
	name: "BaseMain",
  components: {
    AlbumSection,
  }
};
</script>

<style scoped lang="scss">

//MIXIN
@import '../../assets/style/mixins.scss';

.container {
  /* background: rgb(23, 23, 52); */
  height: calc(100vh - 80px);
}


</style>