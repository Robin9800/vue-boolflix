<template>
  <div class="header">
    <h1>BOOLFLIX</h1>
    <!--Associamo all'input, attraverso la direttiva Vue "v-model", textTosearch-->
    <input v-model="textToSearch" type="text" placeholder="Ricerca per titolo">
    <button>Cerca!</button>
  </div>
</template>

<script>
export default {
    name: 'HeaderComponent',
    data(){
      return{
        /*Inizializzaimo la costante, che rappresenterà ciò che l'user scriverà nella
        barrad di ricerca, a stringa vuota*/
        textToSearch:''
      }
    }
}
</script>

<style>
.header{
  display: flex;
  flex-direction: column;
  background-image: url("../../public/img/background.png");
  height: 30vh;
}
.header h1{
  font-size: 100px;
  color: #e50914;
  align-self: center;
}
.header input,button{
  align-self: center;
  width: 120px;
}
</style>