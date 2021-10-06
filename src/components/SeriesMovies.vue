<template>
  <div class="container">
    <ul>
      <li v-for="(movie, index) in movies" :key="index">
        <Movie :MovieDetails="movie" />
      </li>
    </ul>
    <ul>
      <li v-for="(serie, index) in series" :key="index">
        <Serie :SerieDetails="serie" />
      </li>
    </ul>
  </div>
</template>

<script>
import Movie from "./Movie.vue";
import Serie from "./Serie.vue";

export default {
  name: "SeriesMovies",
  props: ["movies", "series"],
  components: {
    Movie,
    Serie,
  },
};
</script>

<style lang="scss" scoped></style>
