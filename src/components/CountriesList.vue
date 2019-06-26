<template>
	<div>
	<select>
		<option disabled value="">"Please select a country"</option>
		<list-component  v-for="(country,index) in countries" :country="country" :key="index"></list-component>
	</select>

	</div>
</template>

<script>
import ListComponent from './ListComponent.vue'

export default {
	name: 'countries-list',
	props: ["countries"],
	components:{
		'list-component': ListComponent
	}
}
</script>

<style scoped>
</style>
