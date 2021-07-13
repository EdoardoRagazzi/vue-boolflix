<template>
  <div class="main">
    <h2>Hai Cercato:</h2>
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
  },
};
</script>


<style scoped lang="scss">
</style>
