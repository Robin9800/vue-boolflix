<template>
  <div class="header">
    <h1>BOOLFLIX</h1>
    <!--Associamo all'input, attraverso la direttiva Vue "v-model", textTosearch-->
    <input v-model="textToSearch" type="text" placeholder="Ricerca per titolo">
    <!--Tramite la direttiva @click associo al button la funzione "search" che andrò a
    valorizzare nei methods-->
    <button @click="search">Cerca!</button>
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
    },
    methods:{
        /*La funzione invierà ciò che verrà scritto in textToSearch
        al genitore nell'App.vue che sta ascoltando*/
        search(){
            //'search' è il nome dell'evento
            this.$emit('search', this.textToSearch)
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
  margin: 20px auto 10px auto;
  color: #e50914;
  align-self: center;
}
.header input,button{
  align-self: center;
  width: 120px;
}
</style>