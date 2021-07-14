<template>
  <div class="card col-2">
    <img :src="'https://image.tmdb.org/t/p/w500' + info.poster_path" alt="" />
    <ul>
      <li>Titolo: {{ info.title || info.name }}</li>
      <li>Titolo.Originale: {{ info.original_title || info.original_name }}</li>
      <li v-if="flags.includes(info.original_language)">
        <strong>lingua:</strong>
        <img
          :src="require(`../assets/${info.original_language}.svg`)"
          :alt="info.original_language"
        />
        <!-- :src="
            'https://raw.githubusercontent.com/lipis/flag-icon-css/6c93c71ab3ddaf7a1f0b580322c293f610f716ae/flags/1x1/' +
            info.original_language +
            '.svg' -->
      </li>
      <li v-else>
        <strong>Lingua: {{ info.original_language }}</strong>
      </li>
      <li>Voto: {{ info.vote_average }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["info"],
  data() {
    return {
      flags: ["en", "it"],
    };
  },
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
    width: 100%;
    height: 60%;
    background-size: cover;
  }
  li > img {
    height: 10%;
    width: 10%;
  }
}
</style>
