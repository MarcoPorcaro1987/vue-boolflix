<template>
  <div class="container cards-cont">
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

<style lang="scss" scoped>
.cards-cont {
  margin-top: 1.875rem;
  color: white;
  ul {
    display: flex;
    flex-wrap: wrap;
    gap: 1.25rem;
    text-align: center;
    li {
      width: calc(100% / 5 - 1.25rem);
      padding: 0.3125rem 0;
    }
  }
}
</style>
