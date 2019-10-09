<template lang="html">
  <div>
    <label for="select-country">Select a country to view its details: </label>
    <select id="select-country">
      <option :value="country" v-for="country in countries">{{country.name}}</option>
    </select>
    <!-- <ul>
      <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
    </ul> -->
  </div>
</template>

<script>
import ListItem from './ListItem.vue'
export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
