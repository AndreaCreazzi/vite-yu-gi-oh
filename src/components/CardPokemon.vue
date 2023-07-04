<script>
export default {
    props: {
        number: Number,
        name: String,
        type1: String,
        type2: String,
        image: String
    },
    data() {
        return {}
    }
}
</script>
<template>
    <div class="pokemon-card d-flex justify-content-center align-items-center flex-column mb-3">
        <img :src="image" alt="name">
        <h3>{{ number }}</h3>
        <h4>{{ name }}</h4>
        <p>{{ type1 }}</p>
        <p>{{ type2 }}</p>
    </div>
</template>
<style lang="scss" scoped>
.pokemon-card {
    width: 300px;
    height: 300px;
    background-color: white;
    padding: 50px;
    border-radius: 20px;

    img {
        width: 150px;
        height: 150px;
        margin-bottom: 10px;
    }

    p {
        margin: 0;
    }
}
</style>