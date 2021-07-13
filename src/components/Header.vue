<template>
  <div class="header">
    <h1 class="text-uppercase">Boolflix</h1>
    <div class="input mb-3">
      <!--INPUT CON  V-MODEL PRENDE IL DATO INSERITO MENTRE CON $EMIT MI DA LA POSSIBILITA DI PASSARE IL DATO DAL FIGLIO AL PADRE CHE IN QUESTO CASO è APP.VUE---IL VALORE DI SEARCHTEXT -->
      <input
        type="text"
        class="form-control mac-style"
        placeholder="TITOLO FILM"
        aria-label="TITOLO FILM"
        aria-describedby="button-addon2"
        v-model="searchText"
        @keyup.enter="$emit('searchMovies&Shows', searchText)"
      />
      <button
        class="btn btn-outline-secondary"
        @click="$emit('searchMovies&Shows', searchText)"
        type="button"
      >
        ENTER
      </button>
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
@import "@/style/common.scss";

.header {
  background-color: indigo;
  height: 100px;
  width: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.mac-style {
  vertical-align: middle;
  display: inline-block;
  width: 150px;
  -webkit-transition: width 1s ease-in-out;
  -moz-transition: width 1s ease-in-out;
  -o-transition: width 1s ease-in-out;
  transition: width 1s ease-in-out;

  text-align: center;
}

.mac-style:focus {
  width: 460px;
}
</style>
