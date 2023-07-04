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
    emits: ['option-change', 'select-submit'],
    methods: {
        resetFilter() {
            this.selectType = "";
            this.$emit('option-change', this.selectType)
        }
    },
}
</script>

<template>
    <div class="container mb-5">
        <select @change="$emit('option-change', selectType)" v-model="selectType" id="inputState"
            class="form-select text-center" placeholder="choose okemon type">
            <option selected v-for="listType of listTypes">{{ listType }}
            </option>
        </select>
        <button @click="resetFilter" class="btn btn-warning mt-2">Annulla</button>
    </div>
</template>

<style scoped>
select {
    border-color: red;
}
</style>