<template lang="html">
  <div>
    <label for="select-country">Select a country to view its details: </label>
    <select id="select-country" v-model="country" v-on:change="handleChange">
      <option v-for="country in countries" :value="country">{{country.name}}</option>
    </select>

    <!-- <ul>
      <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
    </ul> -->
  </div>
</template>

<script>
import { eventBus } from '../main.js'
import ListItem from './ListItem.vue'
export default {
  name: 'countries-list',
  props: ['countries', 'country'],
  data(){
    return{
      country: null
    }
  },
  methods: {
    handleChange(){
      eventBus.$emit('country-selected', this.country)
    }
  },
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
