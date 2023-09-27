<template>
	<div class="container">
		<select
			name="genre"
			v-model="dataShared.searchGenre"
		>
			<option value="">Seleziona un genere</option>
			<option value="rock">Rock</option>
			<option value="pop">Pop</option>
			<option value="jazz">Jazz</option>
			<option value="metal">Metal</option>
		</select>
	</div>
</template>

<script>
import dataShared from '@/shared/dataShared';

export default {
	name: "selectGenre",
  data() {
    return {
      dataShared,
    }
  }
};
</script>

<style scoped lang="scss"></style>
