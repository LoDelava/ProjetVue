<template>
  <div id="Pokemon">

      <div class="block">
        <h2>{{pokemon.data.names[6].name}}</h2>
        <img :src="'https://pokeres.bastionbot.org/images/pokemon/'+pokemon.data.id+'.png'" alt="Avatar" id="Avatar">
      </div>
      <div class="block">
        <h1>Info Pokemon</h1>
        <p>{{pokemon.data.flavor_text_entries[5].flavor_text}}</p>
      </div>
      <div class="block">
        <h1>Statistique</h1>
        <Statistique :pokemon="pokemon"/>
      </div>
  </div>
</template>

<script>


import Statistique from './Statistique.vue'

export default {
  name: 'Pokemon',
  components: {
    
    Statistique
  },
  computed: {
        pokemon() {
          return this.$store.getters.getPokemons[this.$route.params.id-1];
        }
    },
    
}
</script>

<style scoped>
#Pokemon{
  padding: 2%;
  width:90%;
  margin:2%;
  box-shadow: 0 4px 8px 0 rgba(59, 58, 112, 0.2);
  text-align: left;
}

#Pokemon > .block{
  border-radius: 0.2em;
  border: 1px solid rgb(64, 56, 224);
  background-color:#a2c8f7bb ;
  font-family: 'Open Sans', sans-serif;
  color: black;
  margin : 5%;
  padding: 5%;
}

#Avatar{
  width:20%;
  background-color: #f0f0f0;
  margin:20%;
  margin-top: 5%;
  margin-bottom: 5%;
}
</style>