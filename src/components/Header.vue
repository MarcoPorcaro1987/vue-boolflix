<template>
  <header>
    <div class="logo">
      <img src="../assets/img/Logo.png" alt="logo" />
    </div>
    <div>
      <input
        v-on:keyup.enter="$emit('searching', searchText)"
        type="text"
        v-model="searchText"
        placeholder="Cerca il titolo di un film o di una serie tv"
      />
      <button @click="$emit('searching', searchText)">Cerca</button>
    </div>
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
header {
  display: flex;
  justify-content: space-between;
  background-color: black;
  align-items: center;
  padding: 0.9375rem;
  img {
    height: 2rem;
  }
  input {
    width: 18.75rem;
    padding: 0.625rem;
    border-radius: 0.3125rem;
    margin-right: 0.625rem;
  }
  button {
    background-color: red;
    color: white;
    padding: 0.625rem;
    border-radius: 0.625rem;
    cursor: pointer;
  }
}
</style>
