<template lang="html">
<div>
  <!-- <li v-on:click="handleClick">{{country.name}}</li> -->
  <countryListOption v-on:change="handleChange">{{country}}</countryListOption>
</div>
</template>

<script>

import {eventBus} from '../main.js';

export default {
  name: 'countryListOption',// countryListItem
  props: ['country'],
  methods: {
    handleChange(){ //handleClick
      eventBus.$emit('country-selected', this.country)
      console.log('this country is waow');
    }
  }
}
</script>

<style lang="css" scoped>
</style>
