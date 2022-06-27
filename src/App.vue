<template>
  <div id="app">
    <TheHeader :lista-generi="listaGeneri" @searchGenre="onSearchGenre"></TheHeader>
    <CardsList @genresUpdated="onGenresUpdate" :search-genre="searchGenre"></CardsList>
  </div>
</template>

<script>

import CardsList from "./components/CardsList.vue";
import TheHeader from "./components/TheHeader.vue";



export default {
  name: 'App',
  components: { CardsList, TheHeader, },
  data() {
    return {
      listaGeneri: [],
      searchGenre: "",
    }

  },
  methods: {
    onGenresUpdate(listaGeneri) {
      console.log("listaGeneri: ", listaGeneri);
      this.listaGeneri = listaGeneri;
    },
    onSearchGenre(genre) {
      console.log("genre: ", genre);
      this.searchGenre = genre;
    },
  },
}
</script>

<style lang="scss">
@import "./assets/scss/main.scss";
</style>
