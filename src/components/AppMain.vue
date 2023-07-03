<script>
import CardPokemon from '../components/CardPokemon.vue'
import { store } from '../data/store';
export default {
    components: { CardPokemon },
    data() {
        return {
            store
        }
    }
}
</script>
<template>
    <section class="pokemon height">
        <div class="container-fluid height">
            <div class="row g-4 row-cols-3 row-cols-md-4 row-cols-lg-5">
                <div class="col" v-for="pokemon in store.pokemons.item" :key="pokemon._id">
                    <CardPokemon :number="pokemon.number" :name="pokemon.name" :type="pokemon.type1"
                        :image="pokemon.imageUrl" />
                </div>
            </div>
        </div>
    </section>
</template>
<style scoped>
.pokemon {
    background-color: red;
}

.height {
    height: 100vh;
}
</style>