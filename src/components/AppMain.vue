<script>
import CardPokemon from '../components/CardPokemon.vue'
import { store } from '../data/store';
export default {
    components: { CardPokemon },
    data() {
        return store
    }
}
</script>
<template>
    <section class="pokemon height">
        <div class="container-fluid height">
            <div class="row g-4 row-cols-3 row-cols-md-4 row-cols-lg-5">
                <div class="col" v-for="pokemon in pokemons.item" :key="pokemon._id">
                    <CardPokemon :number="pokemon.number" :name="pokemon.name" :type1="pokemon.type1"
                        :image="pokemon.imageUrl" :type2="pokemon.type2" />
                </div>
            </div>
            <div class="d-flex">
                <div class="bouble-large blue mx-2"></div>
                <div class="bouble grey mx-2"></div>
                <div class="bouble yellow mx-2"></div>
                <div class="bouble green mx-2"></div>
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

.bouble {
    width: 50px;
    height: 50px;
    border-radius: 25px;
    border: 5px solid white
}

.bouble-large {
    width: 100px;
    height: 100px;
    border-radius: 50px;
    border: 5px solid white
}

.blue {
    background-color: blue;
}

.grey {
    background-color: grey;
}

.yellow {
    background-color: yellow;
}

.green {
    background-color: green;
}
</style>