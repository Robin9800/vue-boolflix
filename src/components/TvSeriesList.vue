<template>
  <div class="container">
      <div class="card" v-for="oneSerie in TvSeries" :key="oneSerie.id">
          <h3>{{oneSerie.name}}</h3>
          <h4>{{oneSerie.original_name}}</h4>
          <p>{{oneSerie.original_language}}</p>
          <p>{{oneSerie.vote_average}}</p>
          <p>{{oneSerie.poster_path}}</p>
      </div>
  </div>
</template>

<script>
export default {
    name: 'TvSeriesList',
    props:{
        tvSeries: Array 
    }
}
</script>

<style>

</style>