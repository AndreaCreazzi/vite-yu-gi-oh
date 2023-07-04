<script>
import axios from 'axios';
import { store } from './data/store';
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import SelectFilter from './components/SelectFilter.vue';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons'
export default {
  components: { AppHeader, AppMain, SelectFilter },
  data() {
    return {
      store,
      filteredType: "",
    }
  },
  methods: {
    fetchPokemons(url) {
      axios.get(url).then(res => {
        store.pokemons.item = res.data.docs
      })
    },
    pokemonType(option) {
      this.filteredType = option
      if (this.filteredType === "") {
        return this.fetchPokemons(endpoint)
      } else {
        const filteredEndpoint = `${endpoint}?eq[type1]=${this.filteredType}`
        this.fetchPokemons(filteredEndpoint)
      }
    }
  },
  created() {
    this.fetchPokemons(endpoint)
  }
}
</script>
<template>
  <AppHeader />
  <SelectFilter @option-change="pokemonType" />
  <AppMain />
</template>
<style></style>