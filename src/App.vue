<template>
  <div id="app">
    <Header @ricerca="ricercaFilm" />
    <Main :films="filmsArray" :campoRicerca="searchText" />
  </div>
</template>

<script>
import axios from "axios";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data() {
    return {
      apiKey: "8b05b374941d56adfa82388d6d98149a",
      apiUrl: "https://api.themoviedb.org/3/search/movie",
      language: "it-IT",
      filmsArray: [],
      searchText: "",
    };
  },
  methods: {
    ricercaFilm(text) {
      this.searchText = text;
      axios
        .get(this.apiUrl, {
          params: {
            api_key: this.apiKey,
            language: this.language,
            query: text,
          },
        })
        .then((response) => {
          this.filmsArray = response.data.results;
          console.log(this.filmsArray);
        });

      console.log(text);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/common.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  background-color: grey;
}
</style>
