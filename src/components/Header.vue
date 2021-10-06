<template>
  <header>
    <input
      v-on:keyup.enter="$emit('searching', searchText)"
      type="text"
      v-model="searchText"
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

<style lang="scss" scoped></style>
