<script>
export default {
    data() {
        return {
            selectType: "",
            listTypes: [
                "Bug",
                "Dark",
                "Dragon",
                "Electric",
                "Fairy",
                "Fighting",
                "Fire",
                "Flying",
                "Ghost",
                "Grass",
                "Ground",
                "Ice",
                "Normal",
                "Poison",
                "Psychic",
                "Rock",
                "Steel",
                "Water"
            ]
        }
    },
    emits: ['option-change'],
}
</script>

<template>
    <div class="container mb-5">
        <select @change="$emit('option-change', selectType)" v-model="selectType" id="inputState"
            class="form-select text-center">
            <option value="">Gotta catch'em all!</option>
            <option v-for="listType of listTypes">{{ listType }}
            </option>
        </select>
    </div>
</template>

<style scoped>
select {
    border-color: red;
}
</style>