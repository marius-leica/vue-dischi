<template>
    <div class="bg-dark">
        <div class="container">
            <div class="pt-5 pb-2 px-1">
                <div class="row row-cols-2 row-cols-md-5">
                    <div class="col" v-for="(disc, i) in discsList" :key="i">
                        <TheCard :info="disc"></TheCard>


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



export default {
    name: 'CardsList',

    components: {
        TheCard,
    },
    data() {
        return {
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            discsList: [],
        }
    },
    methods: {
        fetchDiscsList() {
            axios.get(this.apiURL,).then((resp) => {
                this.discsList = resp.data.response;
            })
        }
    },
    mounted() {
        this.fetchDiscsList();
    },
}
</script>

<style lang="scss" scoped>
</style>