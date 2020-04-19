<template>
  <div id="Pokedex">
        <div class="contenu">
          <p>Liste des pokemons</p>
          <div v-if="pokemons == undefined">
            <h1> Chargement</h1>
          </div>

          <div v-else class="card" v-for="pokemon in pokemons" :key="pokemon.id">
              <router-link :to="{path:'Pokedex/'+pokemon.id}">
                      <img :src="'https://pokeres.bastionbot.org/images/pokemon/'+pokemon.data.id+'.png'" alt="Avatar" style="width:100%">
                      <div class="container">
                          <h><b>N°{{pokemon.data.id}}</b></h>
                          <p>{{pokemon.data.names[6].name}}</p>
                      </div>
              </router-link>
          </div>

        </div>
  </div>
</template>

<script>

export default {
  name: 'Pokedex',
  
  computed: {
    pokemons() {
      return this.$store.getters.getPokemons;
    },
  }, 
  methods: {
    
  } 
}
</script>

<style>

.card {
  box-shadow: 0 4px 8px 0 rgba(24, 40, 184, 0.2);
  transition: 0.3s;
  width: 15%;
  margin:1%;
  float:left;
  text-decoration: none;
}
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(28, 49, 190, 0.575);
}
.container {
  padding: 2px 16px;
  background-color: rgb(117, 57, 145);
  color:white;
}

.contenu{
  width: 68%;
  margin-left: auto;
  margin-right: auto;
}

b{
  border-radius: 12px;
  text-align: left;
}
</style>