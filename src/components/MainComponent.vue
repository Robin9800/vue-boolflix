<template>
  <div class="main">
      <FilmList :films="films"/>
      <TvSeriesList :tvSeries="tvSeries"/>
  </div>
</template>

<script>
import FilmList from './FilmList.vue';
import TvSeriesList from './TvSeriesList.vue'
export default {
    name: 'MainComponent',
    /* 13 In MainComponent definisco la proprietà di films, è un array */
    props:{
        films: Array,
        tvSeries: Array
    },
    components:{
        FilmList,
        TvSeriesList
    }
  }
</script>

<style>
.main{
    height: 75vh;
}
</style>