<template>
  <div id="Navbar">
    <ul>
      <li><img src="../assets/Pokedex.png" alt="" height="7%" width="7%"/> </li>
      <li><router-link to="/">Accueil</router-link></li>
      <li><router-link to="/Pokedex">Pokédex</router-link></li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'Navbar',
}
</script>

<style>

#Navbar ul {
  list-style-type: none;
  overflow: hidden;
  background-color: rgb(41, 84, 223);
  margin:0%;
  padding:0%;

}

#Navbar li {
  float: left;
}

#Navbar li a {
  display: block;
  color: white; 
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

#Navbar li a:hover {
  background-color: rgb(0, 55, 235);
}

</style>