<template>
  <div class="card container">
    <div class="img-cont">
      <img
        v-if="SerieDetails.poster_path != null"
        :src="'https://image.tmdb.org/t/p/w154' + SerieDetails.poster_path"
      />
      <img v-else src="../assets/img/movie-poster-coming-soon.png" />
    </div>
    <h4>Titolo: {{ SerieDetails.name }}</h4>
    <h5>Titolo Originale: {{ SerieDetails.original_name }}</h5>
    <p>Lingua: <lang-flag :iso="SerieDetails.original_language" /></p>
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
  name: "Serie",
  props: ["SerieDetails"],
  components: {
    LangFlag,
  },
  methods: {
    vote: function () {
      return Math.ceil(this.SerieDetails.vote_average / 2);
    },
  },
};
</script>

<style lang="scss" scoped></style>
