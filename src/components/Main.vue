<template>
  <div class="main">
    <!-- <h2 class="text-uppercase">Search: {{ campoRicerca }}</h2> -->
    <h3 class="d-flex justify-content-start">MOVIES</h3>
    <div class="card d-inline-flex flex-row g-5">
      <Card v-for="film in films" :key="film.id" :info="film" />
    </div>
    <h3 class="d-flex justify-content-start">TV-SHOWS</h3>
    <div class="card d-inline-flex flex-row g-5">
      <Card v-for="show in tvshows" :key="show.id" :info="show" />
    </div>
  </div>
</template>

<script>
import Card from "@/components/Card.vue";

export default {
  name: "Main",
  components: {
    Card,
  },
  props: {
    tvshows: Array,
    films: Array,
    campoRicerca: String,
    msg: String,
  },
};
</script>


<style scoped lang="scss">
@import "@/style/common.scss";

.main {
  width: 90%;
  margin: auto;
  color: #4b0082;
  padding: 50px;
  h3 {
    display: inline-block;
    width: 100%;
  }
}
.card {
  flex-wrap: wrap;
  background-color: #141414;
  border: none;
  padding: 10px;
  min-width: 300px;
}
</style>
