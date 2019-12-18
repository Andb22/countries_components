<template lang="html">
  <div>
  <ul>
    <countryListItem v-for="(country, index) in allCountries" :country="country" :key="index">{{country.name}}</countryListItem>
  </ul>
  <select>
    <option disabled value="">Select a Country</option>
    <option v-for="(country, index) in allCountries" :value="country" :key="index">{{country.name}}></option>
  </select>
    </div>

</template>

<script>
import CountryComponent from './CountryComponent.vue'
// on change event in option above.
// triggers a function here
// take the whole country object and pass it to emit event


export default {
  name: 'country-list',
  props: ['allCountries'],
  components: {
    "countryListItem": CountryComponent
  }


}
</script>

<style lang="css" scoped>
</style>
