<template>
  <div class="main">
      <FilmList :films="films"/>
  </div>
</template>

<script>
import FilmList from './FilmList.vue'
export default {
    name: 'MainComponent',
    /* 13 In MainComponent definisco la proprietà di films, è un array */
    props:{
        films: Array
    },
    components:{
        FilmList
    }
  }
</script>

<style>
.main{
    height: 75vh;
}
</style>