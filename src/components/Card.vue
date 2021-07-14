<template>
  <div class="card col-2">
    <img :src="'https://image.tmdb.org/t/p/w500' + info.poster_path" alt="" />
    <ul>
      <li>Titolo: {{ info.title || info.name }}</li>
      <li>Titolo.Originale: {{ info.original_title || info.original_name }}</li>
      <li>Lingua: {{ info.original_language }}</li>
      <li>Voto: {{ info.vote_average }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["info"],
};
</script>


<style scoped lang="scss">
@import "@/style/common.scss";
ul {
  list-style: none;
}
.card {
  height: 500px;
  width: 350px;
  img {
    height: 60%;
    background-size: 100% 100%;
  }
}
</style>
