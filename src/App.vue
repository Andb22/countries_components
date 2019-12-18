<template>

</template>

<script>


export default {
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
  }
  }

</script>

<style>

</style>
