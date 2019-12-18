<template lang="html">
  <div>
  <select>
    <option disabled value="">Select a Country</option>
    <option v-for="(country, index) in allCountries" :value="country" :key="index">{{country.name}}></option>
  </select>
  <!-- <ul>
    <countryListItem v-for="(country, index) in allCountries" :country="country" :key="index">{{country.name}}</countryListItem>
  </ul> -->
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
    "countryListOption": CountryComponent
  }


}
</script>

<style lang="css" scoped>
</style>
