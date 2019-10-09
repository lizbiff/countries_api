<template lang="html">
  <div class="main-container">
    <h1>Countries</h1>
    <countries-list :countries="countries" />
    <country-detail :selectedCountry="selectedCountry" />
  </div>
</template>

<script>
import { eventBus } from './main'
import countriesList from './components/countriesList'
import countryDetail from './components/countryDetail'

export default {
  components: {
    countriesList,
    countryDetail
  },
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted(){
    fetch("https://restcountries.eu/rest/v2/all")
    .then(response => response.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (selectedCountry) => {
      this.selectedCountry = selectedCountry;
    })
  }
}
</script>

<style lang="css" scoped>
</style>
