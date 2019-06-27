<template>
	<li v-on:click="handleClick">{{country.name}}</li>
</template>

<script>
import { eventBus } from '../main.js'
export default {
	name: 'list-component',
	props: ["country"],
	methods:{
		handleClick(){
			eventBus.$emit('countryClicked',this.country);
		}
	}
}
</script>

<style scoped>

</style>
