<template>
  <div class="card container">
    <div class="img-cont">
      <img
        v-if="MovieDetails.poster_path != null"
        :src="'https://image.tmdb.org/t/p/w154' + MovieDetails.poster_path"
      />
      <img v-else src="../assets/img/movie-poster-coming-soon.png" alt="" />
    </div>
    <h4>{{ MovieDetails.title }}</h4>
    <h5>Titolo originale: {{ MovieDetails.original_title }}</h5>
    <p>Lingua: <lang-flag :iso="MovieDetails.original_language" /></p>
    <div>
      <i
        v-for="n in 5"
        :key="n"
        class="fa-star"
        :class="n <= vote() ? 'fas' : 'far'"
      ></i>
    </div>
  </div>
</template>

<script>
import LangFlag from "vue-lang-code-flags";
import "@fortawesome/fontawesome-free/js/all.js";

export default {
  name: "Movie",
  props: ["MovieDetails"],
  components: {
    LangFlag,
  },
  methods: {
    vote: function () {
      return Math.ceil(this.MovieDetails.vote_average / 2);
    },
  },
};
</script>

<style lang="scss" scoped></style>
