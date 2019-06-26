<template>
	<div>
		<h3>Name :{{country.name}}</h3>
		<h3>Subregion: {{country.subregion}}</h3>
		<h3>Population: {{country.population}}</h3>
	</div>
</template>

<script>
export default {
	name: 'country-details',
	props: ["country"]
}
</script>

<style scoped>

</style>


