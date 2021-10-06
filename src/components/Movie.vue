<template>
  <div class="card container">
    <img
      :src="'https://image.tmdb.org/t/p/w154' + MovieDetails.poster_path"
      alt=""
    />
    <h4>{{ MovieDetails.title }}</h4>
    <h5>Titolo originale: {{ MovieDetails.original_title }}</h5>
    <p>Lingua: <lang-flag :iso="MovieDetails.original_language" /></p>
    <p>Voto: {{ MovieDetails.vote_average }}</p>
  </div>
</template>

<script>
import LangFlag from "vue-lang-code-flags";

export default {
  name: "Movie",
  props: ["MovieDetails"],
  components: {
    LangFlag,
  },
};
</script>

<style lang="scss" scoped></style>
