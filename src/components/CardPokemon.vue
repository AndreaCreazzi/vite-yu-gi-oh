<script>
export default {
    props: {
        number: Number,
        name: String,
        type: String,
        image: String
    },
    data() {
        return {}
    }
}
</script>
<template>
    <div class="pokemon-card  d-flex justify-content-center align-items-center flex-column">
        <img :src="image" alt="name">
        <h1>{{ number }}</h1>
        <h4>{{ name }}</h4>
        <p>{{ type }}</p>
    </div>
</template>
<style scoped>
img {
    width: 100px;
    height: 100px;
}

.pokemon-card {
    width: 300px;
    height: 300px;
    background-color: white;
    padding: 50px;
}
</style>