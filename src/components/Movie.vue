<template>
  <div class="card">
    <h3>Titolo: {{ MovieDetails.title }}</h3>
    <h4>Titolo Originale: {{ MovieDetails.original_title }}</h4>
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
