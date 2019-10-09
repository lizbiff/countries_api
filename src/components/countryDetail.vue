<template lang="html">
  <div v-if="selectedCountry">
    {{ selectedCountry.name }}
    {{ selectedCountry.capital }}
    {{ selectedCountry.population }}
  </div>
</template>

<script>
export default {
  props: ['selectedCountry']
}
</script>

<style lang="css" scoped>
</style>
