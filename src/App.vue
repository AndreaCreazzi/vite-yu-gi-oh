<script>
import axios from 'axios';
import { store } from './data/store';
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons'
export default {
  components: { AppHeader, AppMain },
  data() {
    return {
      store
    }
  },
  methods: {
    fetchPokemons(url) {
      axios.get(url).then(res => {
        store.pokemons.item = res.data.docs
      })
    }
  },
  created() {
    this.fetchPokemons(endpoint)
  }
}
</script>
<template>
  <AppHeader />
  <AppMain />
</template>
<style></style>