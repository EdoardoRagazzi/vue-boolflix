<template>
  <div class="main">
    <h2>Hai Cercato: {{ campoRicerca }}</h2>
    <Card v-for="film in films" :key="film.id" :info="film" />
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
    films: Array,
    campoRicerca: String,
  },
};
</script>


<style scoped lang="scss">
</style>
