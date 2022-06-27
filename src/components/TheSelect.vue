<template>
    <div class="">
        <div class="form-group d-flex">
            <select v-model="genre" class="form-select" aria-label="Default select example">
                <option selected>Seleziona il genere</option>
                <option v-for="(genere, i) in listaGeneri" :key="i" value="genere">{{ genere }}</option>

            </select>
            <button class="btn btn-outline-light" @click="onSearchClick">Cerca</button>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        listaGeneri: Array
    },
    data() {
        return {
            genre: "",

        }
    },
    methods: {
        onSearchClick() {
            this.$emit('searchGenre', this.genre);
        },

    },

}
</script>

<style lang="scss">
</style>