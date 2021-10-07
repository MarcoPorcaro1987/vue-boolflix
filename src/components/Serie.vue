<template>
  <div class="card container">
    <div class="img-cont">
      <img
        :src="'https://image.tmdb.org/t/p/w154' + SerieDetails.poster_path"
        alt=""
      />
    </div>
    <h4>Titolo: {{ SerieDetails.name }}</h4>
    <h5>Titolo Originale: {{ SerieDetails.original_name }}</h5>
    <p>Lingua: <lang-flag :iso="SerieDetails.original_language" /></p>
    <p>Voto: {{ division(SerieDetails.vote_average) }}</p>
  </div>
</template>

<script>
import LangFlag from "vue-lang-code-flags";
import "@fortawesome/fontawesome-free/js/all.js";

export default {
  name: "Serie",
  props: ["SerieDetails"],
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
