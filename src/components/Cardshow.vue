<template>
  <div class="card">
    <ul>
      <li>Titolo: {{ infoshow.name }}</li>
      <li>Titolo.Originale: {{ infoshow.original_name }}</li>
      <li>Lingua: {{ infoshow.original_language }}</li>
      <li>Voto: {{ infoshow.vote_average }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["infoshow"],
};
</script>


<style scoped lang="scss">
ul {
  list-style: none;
}
</style>
