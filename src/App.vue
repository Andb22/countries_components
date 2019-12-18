<template>
  <div class="main-container">
    <h1>Countries</h1>

      <country-list :allCountries='countries'/>
      <country-detail :country='selectedCountry'/>

  </div>

</template>

<script>
import CountryList from './components/CountryList.vue'
import { eventBus } from './main.js'
import CountryDetail from './components/CountryDetails.vue'


export default {
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

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country
    })
  },
  components: {
    'country-list': CountryList,
    'country-detail': CountryDetail
  }
  }

</script>

<style>
.main-container {
  display: flex;
  justify-content: space-between;
}
</style>
