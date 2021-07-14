<template>
  <div id="app">
    <Header @searchMoviesShows="ricercaMoviesShows" />
    <Main
      :films="filmsArray"
      :campoRicerca="searchText"
      :tvshows="showArray"
      msg="TV-SHOWS"
    />
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
      filmsArray: [],
      showArray: [],
      searchText: "",
    };
  },
  methods: {
    // },
    ricercaMoviesShows(text) {
      this.searchText = text;

      const request = {
        params: {
          api_key: this.apiKey,
          language: this.language,
          query: text,
        },
      };
      axios
        .all([
          axios.get(this.apiUrlMovies, request),
          axios.get(this.apiUrlShows, request),
        ])
        .then(
          axios.spread((responseMovies, responseTv) => {
            this.filmsArray = responseMovies.data.results.filter(
              (elem) => elem.vote_count > 300
            );
            this.showArray = responseTv.data.results.filter(
              (elem) => elem.vote_count > 300
            );
          })
        );

      // 2FUNCTIONS
      // this.ricercaShows(text);
      // this.ricercaMovies(text);
    },
  },
};

// RICERCA MOVIES AND TV-SHOWS WITH 2 FUNCTIONS
//   ricercaMovies(text) {
//     axios
//       .get(this.apiUrlMovies, {
//         params: {
//           api_key: this.apiKey,
//           language: this.language,
//           query: text,
//         },
//       })
//       .then((response) => {
//         this.filmsArray = response.data.results;
//         console.log(this.filmsArray);
//       });
//   },

//   ricercaShows(text) {
//     axios
//       .get(this.apiUrlShows, {
//         params: {
//           api_key: this.apiKey,
//           language: this.language,
//           query: text,
//         },
//       })
//       .then((response) => {
//         this.showArray = response.data.results;
//         console.log(this.showArray);
//       });
//   },
// },
</script>

<style lang="scss" scoped>
@import "@/style/common.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  background-color: #141414;
  min-height: 100vh;
}
.container {
  background-color: #141414;
}
</style>
