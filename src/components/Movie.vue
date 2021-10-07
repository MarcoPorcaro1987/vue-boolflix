<template>
  <div class="card container">
    <div class="img-cont">
      <img
        :src="'https://image.tmdb.org/t/p/h632' + MovieDetails.poster_path"
        alt=""
      />
    </div>
    <h4>{{ MovieDetails.title }}</h4>
    <h5>Titolo originale: {{ MovieDetails.original_title }}</h5>
    <p>Lingua: <lang-flag :iso="MovieDetails.original_language" /></p>
    <p>Voto: {{ division(MovieDetails.vote_average) }}</p>
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
    division(averageVote) {
      return Math.ceil(averageVote / 2);
    },
  },
};
</script>

<style lang="scss" scoped></style>
