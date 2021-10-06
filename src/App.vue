<template>
  <div id="app">
    <Header @searching="search" />
    <SeriesMovies :movies="movies" :series="series" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import SeriesMovies from "./components/SeriesMovies.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Header,
    SeriesMovies,
  },
  data() {
    return {
      movies: [],
      series: [],
    };
  },
  methods: {
    search(query) {
      axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            api_key: "50141624ddf0cbc57d2265f68b3291e9",
            query: query,
            language: "it-IT",
          },
        })
        .then((response) => {
          console.log(response.data.results);
          this.movies = response.data.results;
        });
      axios
        .get("https://api.themoviedb.org/3/search/tv", {
          params: {
            api_key: "50141624ddf0cbc57d2265f68b3291e9",
            query: query,
            language: "it-IT",
          },
        })
        .then((response) => {
          console.log(response.data.results);
          this.series = response.data.results;
        });
    },
  },
};
</script>

<style lang="scss"></style>
