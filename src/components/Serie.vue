<template>
  <div class="card">
    <div class="img-cont">
      <img
        v-if="SerieDetails.poster_path != null"
        :src="'https://image.tmdb.org/t/p/w342' + SerieDetails.poster_path"
        :alt="SerieDetails.name"
      />
      <img
        v-else
        src="../assets/img/movie-poster-coming-soon.png"
        :alt="SerieDetails.name"
      />
      <h3 v-if="SerieDetails.poster_path == null">{{ SerieDetails.name }}</h3>
      <div class="info">
        <h4>{{ SerieDetails.name }}</h4>
        <h5 v-if="SerieDetails.name != SerieDetails.original_name">
          Titolo Originale: {{ SerieDetails.original_name }}
        </h5>
        <p>Lingua: <lang-flag :iso="SerieDetails.original_language" /></p>
        <i
          v-for="n in 5"
          :key="n"
          class="fa-star"
          :class="n <= vote() ? 'fas' : 'far'"
        ></i>
        <p v-if="SerieDetails.overview != null" class="overview">
          {{ SerieDetails.overview }}
        </p>
      </div>
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
