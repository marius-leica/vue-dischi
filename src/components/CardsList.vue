<template>
    <div class="bg-dark">
        <div class="container">
            <div class="pt-5 pb-2 px-1">
                <div class="row">
                    <div class="col-md-2" v-for="(comic, i) in comicsList" :key="i">
                        <TheCard :comic-title="comic.series" :url-img="comic.thumb" :comic-price="comic.price"
                            :comic-type="comic.type"></TheCard>
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



export default {
    name: 'CardsList',
    components: {
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