<template>
	<div class="container">
    <selectGenre/>
    <AlbumSection/>
	</div>
</template>

<script>

import AlbumSection from '../sections/AlbumSection.vue'
import selectGenre from '../particles/selectGenre.vue'


export default {
	name: "BaseMain",
  components: {
    AlbumSection,
    selectGenre,
  }
};
</script>

<style scoped lang="scss">

//MIXIN
@import '../../assets/style/mixins.scss';


</style>