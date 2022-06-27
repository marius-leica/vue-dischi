<template>
    <div>
        <nav class="navbar navbar-expand-lg p-0 flex-shrink-0">
            <div class="d-flex justify-space-betwen w-100 align-items-center">
                <a class="navbar-brand py-2" href="#">
                    <img :src="require('../assets/spotify_logo.jpg')" alt="spotify logo" width="70" height="70" />
                </a>

                <TheSelect class="ms-auto" @searchGenre="$emit('searchGenre', $event)">
                </TheSelect>

            </div>
        </nav>
    </div>
</template>

<script>

import TheSelect from "./TheSelect.vue";
export default {
    name: 'TheHeader',
    components: {
        TheSelect,
    },
    // props: {
    //     listaGeneri: Array
    // },


    // methods: {
    //     filtreGenre(genre) {
    //         this.$emit('selectGenre', genre);
    //     }
    // },
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/main.scss";

.navbar {
    background-color: $grey_color;
    flex-shrink: 0;
}
</style>