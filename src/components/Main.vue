<template>
  <div class="main">
    <h2 class="text-uppercase">Hai Cercato: {{ campoRicerca }}</h2>
    <div class="movies">
      <h2>Movies</h2>
      <Card v-for="film in films" :key="film.id" :infofilm="film" />
    </div>
    <div class="tv-show">
      <h2>Tv-show</h2>
      <Cardshow v-for="show in tvshows" :key="show.id" :infoshow="show" />
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
    tvshows: Array,
    films: Array,
    campoRicerca: String,
  },
};
</script>


<style scoped lang="scss">
@import "@/style/common.scss";
.movies {
  float: left;
}
.tv-show {
  float: right;
}
</style>
