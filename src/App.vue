<template>
  <div id="app">
    <Nav />
    <Cards class="card" v-for="data in datas" :key="data.id" :data="data" />

  </div>
</template>

<script>
import Nav from "./components/Nav.vue";
import Cards from "./components/Cards.vue";
import data from "../exo-ressources/data.json";
export default {
    name: "App",
    components: { Nav, Cards },
    data() {
        return {
            datas :data
        };
    },
    mounted() {
        console.log(this.datas);
    }
}
</script>

<style lang="sass">
@import url('https://fonts.google.com/specimen/Spartan')

body 
  font-family: 'Spartan', sans-serif
  background-color: #f5f5f5
  font-weight: 700
  font-size: 15px
  span
    color: hsl(180, 29%, 50%)
  .card
    margin-top:35px
</style>
