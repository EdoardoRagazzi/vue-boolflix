<template>
  <div class="card col-3">
    <img
      :src="'https://image.tmdb.org/t/p/w500' + infoshow.poster_path"
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
@import "@/style/common.scss";
ul {
  list-style: none;
}
.card {
  height: 400px;
  width: 300px;
  img {
    height: 60%;
    background-size: cover;
  }
}
</style>
