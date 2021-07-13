<template>
  <div class="header">
    <div class="input-group mb-3">
      <input
        type="text"
        class="form-control"
        placeholder="Titolo FILM"
        aria-label="Titolo FILM"
        aria-describedby="button-addon2"
        v-model="searchText"
        @keyup="$emit('ricerca', searchText)"
      />
      <button
        class="btn btn-outline-secondary"
        type="button"
        id="button-addon2"
      ></button>
    </div>
  </div>
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


<style scoped lang="scss">
</style>
