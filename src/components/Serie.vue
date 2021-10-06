<template>
  <div class="card">
    <h3>Titolo: {{ SerieDetails.name }}</h3>
    <h4>Titolo Originale: {{ SerieDetails.original_name }}</h4>
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
