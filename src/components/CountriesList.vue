<template>
	<div>
	<select v-model="selected" v-on:change="handleClick()">
		<option disabled value="">"Please select a country"</option>
		<list-component  v-for="(country,index) in countries" :country="country" :key="index"></list-component>
	</select>

	</div>
</template>

<script>
import {eventBus} from '../main.js'
import ListComponent from './ListComponent.vue'

export default {
	name: 'countries-list',
	data:
	{
		selected: ""
	},
	props: ["countries"],
	components:{
		'list-component': ListComponent
	},
	methods:{
		handleClick(){
			eventBus.$emit('countryClicked',this.selected)
		}
	}
}
</script>

<style scoped>
</style>
