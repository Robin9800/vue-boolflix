<template>
  <div class="container">
      <div class="card" v-for="film in films" :key="film.id">
          <h3>{{film.title}}</h3>
          <h4>{{film.original_title}}</h4>
          <p>{{film.original_language}}</p>
          <p>{{film.vote_average}}</p>
      </div>
  </div>
</template>

<script>
export default {
    name: 'FilmList',
    props:{
        films: Array,
    }
}
</script>

<style>
.container{
    max-width: 1200px;
}
.card{
    width: 50px;
    height: 80px;
    padding: 0.5rem;
    text-align: center;
    border: 1px solid black;
}
</style>