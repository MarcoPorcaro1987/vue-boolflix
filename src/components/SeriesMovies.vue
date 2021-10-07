<template>
  <div class="container cards-cont">
    <h2>Film</h2>
    <ul>
      <li v-for="(movie, index) in movies" :key="index">
        <Movie :MovieDetails="movie" />
      </li>
    </ul>
    <hr />
    <h2>Serie TV</h2>
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

<style lang="scss" scoped>
.cards-cont {
  margin-top: 1.875rem;
  color: white;
  h2 {
    text-align: center;
  }
  hr {
    margin: 1.25rem 0;
  }
  ul {
    display: flex;
    flex-wrap: wrap;
    gap: 1.25rem;
    text-align: center;
    li {
      width: calc(100% / 5 - 1.25rem);
      padding: 1.25rem 0;
    }
  }
}
</style>
