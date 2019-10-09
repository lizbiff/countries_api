<template lang="html">
<div>
  <select @change="changeSelect" v-model="countrySelected">
    <option disabled value="">Select country</option>
    <option v-for="(country, index) in countries" :value="country">{{ country.name }}</option>
  </select>
</div>
</template>

<script>
import countriesOption from './countriesOption'
import { eventBus } from '../main'

export default {
  name: 'countries-list',
  props: ['countries'],
  data: () => ({
    countrySelected: ""
  }),
  components: {
    "countries-option": countriesOption
  },
  methods: {
    changeSelect() {
      eventBus.$emit('country-selected', this.countrySelected)
      console.log(this.countrySelected)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
