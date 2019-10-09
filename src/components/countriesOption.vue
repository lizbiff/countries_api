<template lang="html">
  <li>
    <span @click="detailIsVisible = !detailIsVisible">{{country.name}}</span>
    <div v-if="detailIsVisible">
      <p>{{ country.capital }}</p>
      <p>{{ country.population }}</p>
    </div>
  </li>
</template>

<script>
export default {
  name: 'countries-option',
  props: ['country'],
  data: () => ({
    detailIsVisible: false
  })
}
</script>

<style lang="css" scoped>
</style>
