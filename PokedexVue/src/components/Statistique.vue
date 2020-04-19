<template>
    <div id="stats">
        <table>
            <tr>
                <td>Points de Vie</td>
                <td>{{pokemon.details.stats[5].base_stat}}</td>
                
            </tr>
            <tr>
                <td>Attaque</td>
                <td>{{pokemon.details.stats[4].base_stat}}</td>
                
            </tr>
            <tr>
                <td>Attaque Spé</td>
                <td>{{pokemon.details.stats[2].base_stat}}</td>
                
            </tr>

            <tr>
                <td>Défense</td>
                <td>{{pokemon.details.stats[3].base_stat}}</td>
                
            </tr>
            
            <tr>
                <td>Defense Spé</td>
                <td>{{pokemon.details.stats[1].base_stat}}</td>
                
            </tr>
            <tr>
                <td>Vitesse</td>
                <td>{{pokemon.details.stats[0].base_stat}}</td>
               
            </tr>
            <tr>
                <td>Type(s)</td>
                <td v-for="type in pokemon.details.types" :key="type">{{type.type.name}}</td>
               
            </tr>
            <tr>
                <td>Taille</td>
                <td>{{pokemon.details.height/10}} m</td>
            </tr>
            <tr>
                <td>Poids</td>
                <td>{{pokemon.details.weight/10}} Kg</td>
            </tr>
        </table>
    </div>
</template>

<script>


export default {
  name: 'Statistique',
  props: {
      pokemon : Object
  }
      
}
</script>

<style scoped>

table td{
    padding: auto;
    background-color: rgb(175, 189, 250);
    border-color: black;
    border-width: 1em;
}



</style>