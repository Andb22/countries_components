<template lang="html">
  <div>
  <ul>
    <li v-for="(country, index) in allCountries" :country="country" :key="index">{{country.name}}</li>
  </ul>
    </div>

</template>

<script>


export default {
  name: 'country-list',
  props: ['allCountries'],


}
</script>

<style lang="css" scoped>
</style>
