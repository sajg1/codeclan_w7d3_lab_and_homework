<template>
	<div class="main-container" id="app">
		<countries-list :countries="countries"></countries-list>
		<country-details :country="selectedCountry"></country-details>
	</div>
</template>

<script>
import CountriesList from './components/CountriesList.vue'
import {eventBus} from './main.js'
import CountryDetails from './components/CountryDetails'

export default {
	name: 'app',
	data(){
		return {
			countries: [],
			selectedCountry: null
		};
	},
	mounted(){
		fetch('https://restcountries.eu/rest/v2/all')
		.then(res => res.json())
		.then( countries => this.countries=countries)

		eventBus.$on('countryClicked', (country) => {
			this.selectedCountry=country;
		})
	},
	components: {
		"countries-list": CountriesList,
		'country-details': CountryDetails
	}
}
</script>

<style>
	.main-container {
		display: flex;
		justify-content: space-between;
	}
</style>
