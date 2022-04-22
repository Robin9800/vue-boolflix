<template>
  <div id="app">
    <!-- 5 Inserisco l'evento 'search' nel component genitore
    e lo valorizzo con una funzione che specificherò nei methods in App.vue-->
    <HeaderComponent @search='searching'/>
    <!-- 14 Collego la props 'films' al mainComponent
    nell''App.vue' premettendo i ':'alla props. La props sarà associato a 'films'
    contenuto nei data di App.vue (faccio la stessa cosa per le serie tv)-->
    <MainComponent :films='arrayFilms' :tvSeries='arrayTvSeries'/>
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
      apiKey: '7b0221641cd6cccd42ea4445b3c56e3d',
      // 11 Inserisco nei data 'films' inizializzato ad array vuoto
      arrayFilms: [],
      arrayTvSeries: []
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
        query: textToSearch,
        language: "it-IT"
      }
      /* 10 Con queste riga di codice chiedo ad axios di prendere il valore
      di apiUrl + movie e i valori dei paramentri (params) */
      axios.get(this.apiUrl + 'movie', {params}).then((response)=>{
        console.log(response);
        /* 12 Se lo stato del response è positivo allora l'array film otterrà
        del risultato di response.data*/
        if(response.status === 200){
          this.arrayFilms = response.data.result
        }
      }),
      axios.get(this.apiUrl + 'tv', {params}).then((response)=>{
        console.log(response);
        if(response.status === 200){
          this.arrayTvSeries = response.data.result
        }
      })
    }
  }
}
</script>

<style>

</style>
