<template>
  <div id="app">
    <!-- 5 Inserisco l'evento 'search' nel component genitore
    e lo valorizzo con una funzione che specificherò nei methods in App.vue-->
    <HeaderComponent @search='searching'/>
    <MainComponent/>
</div>
 
</template>

<script>
import MainComponent from './components/MainComponent.vue'
import HeaderComponent from './components/HeaderComponent.vue'
// 7 Importo axios e specifico gli indirizzi nel 'data()'
import axios from 'axios';

export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent,
  },
  data(){
    return {
      /*8 Inserisco nei data apiUrl e Apikey per poter fare la
      chiamata al sito dei film e serie */
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiKey: '7b0221641cd6cccd42ea4445b3c56e3d'
    }
  },
  methods:{
    /* 6 La funzione avrà come parametro ciò che verrà inserito in
    "textToSearch" */
    searching(textToSearch){
      /* 9 Definisco, con una costante, i paramentri richiesti dalla
      documentazione sul sito "themoviedb" */
      const params ={
        api_key: this.apiKey,
        query: textToSearch
      }
      axios.get(this.apiUrl + 'movie', {params}).then((response)=>{
        console.log(response);
      })
    }
  }
}
</script>

<style>

</style>
