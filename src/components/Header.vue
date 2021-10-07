<template>
  <header class="container">
    <input
      v-on:keyup.enter="$emit('searching', searchText)"
      type="text"
      v-model="searchText"
      placeholder="Cerca il titolo di un film o di una serie tv"
    />
    <button @click="$emit('searching', searchText)">Cerca</button>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      searchText: "",
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/common.scss";
header {
  padding: 0.625rem;
  text-align: right;
  input {
    width: 18.75rem;
    padding: 0.625rem;
    border-radius: 0.3125rem;
    margin-right: 0.625rem;
    text-align: center;
  }
  button {
    background-color: red;
    color: white;
    padding: 0.625rem;
    border-radius: 0.625rem;
  }
}
</style>
