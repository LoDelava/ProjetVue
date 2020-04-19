<template>
  <div id="app">
    <Navbar/>
    <router-view/>
  </div>
</template>

<script>

import axios from 'axios';
import Navbar from './components/Navbar.vue';


export default {
  name: 'App',
  created() {
    this.getAll();
   
  },
  components: {
    Navbar,
  },
  methods: {
    getAll() {  
      let nb_pokemon = 807;
      let pokemonList = [];   
      for(let idx =1; idx <= nb_pokemon; idx++){ 
        axios.get(`https://pokeapi.co/api/v2/pokemon-species/${idx}/`)
        .then(response=>{
          pokemonList[response.data.id-1]={
              id:response.data.id,
              data:response.data
          };
        })
        .catch(error =>{
            console.log(error);
        })
      }
      for(let idx =1; idx <= nb_pokemon; idx++){ 
        axios.get(`https://pokeapi.co/api/v2/pokemon/${idx}/`)
          .then(response=>{
            pokemonList[response.data.id-1].details = response.data;
          })
          .catch(error =>{
            console.log(error);
          })
      }
      this.$store.commit('setPokemons',pokemonList);
    },
    
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
  width: 100%;
}


</style>
