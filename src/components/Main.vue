<template>
  <div class="main">
    <h2>Hai Cercato: {{ campoRicerca }}</h2>
    <div class="movies">
      <h2>Movies</h2>
      <Card v-for="film in films" :key="film.id" :info="film" />
    </div>
    <div class="tv-show">
      <h2>Tv-show</h2>
      <Cardshow v-for="film in films" :key="film.id" :info="film" />
    </div>
  </div>
</template>

<script>
import Card from "@/components/Card.vue";
import Cardshow from "@/components/Cardshow.vue";
export default {
  name: "Main",
  components: {
    Card,
    Cardshow,
  },
  props: {
    films: Array,
    campoRicerca: String,
  },
};
</script>


<style scoped lang="scss">
.movies {
  float: left;
}
.tv-show {
  float: right;
}
</style>
