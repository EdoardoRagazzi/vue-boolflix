<template>
  <div id="app">
    <Header @searchMoviesShows="ricercaMoviesShows" />
    <Main :films="filmsArray" :campoRicerca="searchText" :tvshows="showArray" />
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
      apiUrlMovies: "https://api.themoviedb.org/3/search/movie",
      apiUrlShows: "https://api.themoviedb.org/3/search/tv",
      language: "it-IT",
      filmsArray: [],
      showArray: [],
      searchText: "",
    };
  },
  methods: {
    // },
    ricercaMoviesShows(text) {
      this.searchText = text;
      this.ricercaShows(text);
      this.ricercaMovies(text);
    },

    ricercaMovies(text) {
      axios
        .get(this.apiUrlMovies, {
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

    ricercaShows(text) {
      axios
        .get(this.apiUrlShows, {
          params: {
            api_key: this.apiKey,
            language: this.language,
            query: text,
          },
        })
        .then((response) => {
          this.showArray = response.data.results;
          console.log(this.showArray);
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

  height: 100%;
}
</style>
