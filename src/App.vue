<template>
  <div id="app">
    <Nav />
    <div class="flit">
      <Fliter class="fliter" :ajout="ajout" />
      <Cards class="card"  v-for="data in datas" :key="data.id" :data="data" @tags="add" />
    </div>
  </div>
</template>

<script>
import Nav from "./components/Nav.vue";
import Cards from "./components/Cards.vue";
import data from "../exo-ressources/data.json";
import Fliter from "./components/Fliter.vue";
export default {
  name: "App",
  components: { Nav, Cards, Fliter },
  data() {
    return {
      datas: data,
      ajout: []
    };
  },
  methods: {
    add(value) {
      this.ajout = value;
      console.log(value);
    }
  },
  computed: {


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
  position: relative
  .fliter
    position: absolute
    top: 120px
    left: 180px
  span
    color: hsl(180, 29%, 50%)
  .card
    margin-top: 35px
  // .flit
  //     display: flex
  //     flex-direction: column
  //     justify-content: center
  //     align-items: center
</style>
