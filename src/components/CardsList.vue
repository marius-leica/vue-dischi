<template>
    <div class="bg-dark p-5">

        <div class="container flex-grow-1">
            <div class="pt-5 pb-2 px-1">
                <div class="alert alert-info"> genere attivo: {{ genereSelezionato }}</div>
                <div class="row row-cols-2 row-cols-md-5">
                    <div class="col" v-for="(disc, i) in filteredDiscs" :key="i">
                        <TheCard class="h-100" :disc="disc"></TheCard>


                    </div>
                </div>
                <div>

                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
import TheCard from "./TheCard.vue";
import { state } from "../store";



export default {
    name: 'CardsList',
    components: {
        TheCard,
    },
    // props: {
    //     searchGenre: String
    // },
    data() {
        return {
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            /**
             *  @type {{author: string, genre: string, poster: string, title: string, year: string}[] }
             
             */
            discsList: [],
        }
    },
    computed: {
        filteredDiscs() {
            if (!state.genereSelezionato) {
                return this.discsList;
            }
            return this.discsList.filter(disc => {
                return disc.genre === state.genereSelezionato;
            });
        },
        genereSelezionato() {
            return state.genereSelezionato;
        },
    },
    methods: {
        fetchDiscsList() {
            axios.get(this.apiURL,).then((resp) => {
                this.discsList = resp.data.response;
                state.listaGeneri = this.listaGeneri();
                // this.$emit("genresUpdated", this.listaGeneri())
            })
                .catch(() => {
                    alert("Errore");
                })
        },
        listaGeneri() {
            const lista = [];
            this.discsList.forEach((disc) => {
                if (!lista.includes(disc.genre)) {
                    lista.push(disc.genre);
                }
            });
            return lista;
            /* adesso vogliamo passare questo dato con EMIT a app.vue e da li con PROP a TheHeader.vue e poi TheSearch.vue */
        }
    },



    mounted() {
        this.fetchDiscsList();
    },
}
</script>

<style lang="scss" scoped>
.row {
    row-gap: 1rem;
}
</style>