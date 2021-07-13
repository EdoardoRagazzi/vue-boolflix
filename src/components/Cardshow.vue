<template>
  <div class="card">
    <img
      :src="'https://image.tmdb.org/t/p/w300' + infoshow.poster_path"
      alt=""
    />
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
.card {
  float: left;
}
</style>
