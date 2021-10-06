<template>
  <div class="card container">
    <img
      :src="'https://image.tmdb.org/t/p/w154' + SerieDetails.poster_path"
      alt=""
    />
    <h4>Titolo: {{ SerieDetails.name }}</h4>
    <h5>Titolo Originale: {{ SerieDetails.original_name }}</h5>
    <p>Lingua: <lang-flag :iso="SerieDetails.original_language" /></p>
    <p>Voto: {{ SerieDetails.vote_average }}</p>
  </div>
</template>

<script>
import LangFlag from "vue-lang-code-flags";

export default {
  name: "Serie",
  props: ["SerieDetails"],
  components: {
    LangFlag,
  },
};
</script>

<style lang="scss" scoped></style>
