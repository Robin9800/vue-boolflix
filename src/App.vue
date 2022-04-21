<template>
  <div id="app">
    <!--Inserisco l'evento 'search' nel component genitore
    e lo valorizzo con una funzione che specificherà nei methods in App.vue-->
    <HeaderComponent @search='doSearch'/>
    <MainComponent/>
</div>
 
</template>

<script>
import MainComponent from './components/MainComponent.vue'
import HeaderComponent from './components/HeaderComponent.vue';

export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent,
  },
  methods:{
    /*La funzione avrà come parametro ciò che verrà inserito in
    "textToSearch" */
    doSearch(textToSearch){
      console.log(textToSearch);
    }
  }
}
</script>

<style>

</style>
