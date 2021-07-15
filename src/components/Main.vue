<template>
  <div class="main">
    <!-- <h2 class="text-uppercase">Search: {{ campoRicerca }}</h2> -->
    <div class="card d-flex flex-row g-5">
      <Card v-for="film in films" :key="film.id" :info="film" />
    </div>
    <div class="card d-flex flex-row g-5">
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
}
.card {
  flex-wrap: wrap;
  background-color: #141414;
  border: none;
  padding: 10px;
}
</style>
