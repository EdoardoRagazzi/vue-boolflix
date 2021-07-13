<template>
  <div class="card col-3">
    <img
      :src="'https://image.tmdb.org/t/p/w500' + infofilm.poster_path"
      alt=""
    />
    <ul>
      <li>Titolo: {{ infofilm.title }}</li>
      <li>Titolo.Originale: {{ infofilm.original_title }}</li>
      <li>Lingua: {{ infofilm.original_language }}</li>
      <li>Voto: {{ infofilm.vote_average }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["infofilm"],
};
</script>


<style scoped lang="scss">
@import "@/style/common.scss";
ul {
  list-style: none;
}
.card {
  height: 300px;
  width: 300px;
  img {
    height: 60%;
    background-size: 100% 100%;
  }
}
</style>
