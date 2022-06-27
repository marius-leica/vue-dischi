<template>
    <div class="">
        <div class="form-group d-flex">
            <select v-model="genre" class="form-select" aria-label="Default select example">
                <option selected>Seleziona il genere</option>
                <option v-for="(genere, i) in listaGeneri" :key="i" :value="genere">{{ genere }}</option>

            </select>
            <button class="btn btn-outline-light" @click="onSearchClick">Cerca</button>
        </div>
    </div>
</template>

<script>
import { state } from "../store";

export default {
    // props: {
    //     listaGeneri: Array
    // },
    data() {
        return {
            genre: "",

        }
    },
    computed: {
        listaGeneri() {
            return state.listaGeneri;
        }
    },
    methods: {
        onSearchClick() {
            state.genereSelezionato = this.genre;
        },

    },

}
</script>

<style lang="scss">
</style>