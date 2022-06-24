<template>
  <div id="app">
    <TheHeader></TheHeader>
    <CardsList></CardsList>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import CardsList from "./components/CardsList.vue";


export default {
  name: 'App',
  components: {
    TheHeader,
    CardsList,
  }
}
</script>

<style lang="scss">
@import "./assets/scss/main.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: rgb(30, 45, 59);
  height: 100vh;
}
</style>
