<template>
  <div class="card col-2" :class="info">
    <img :src="'https://image.tmdb.org/t/p/w500' + info.poster_path" alt="" />
    <div class="overlay">
      <div class="text">
        <ul>
          <li>Titolo: {{ info.title || info.name }}</li>
          <li>
            Titolo.Originale: {{ info.original_title || info.original_name }}
          </li>
          <li v-if="flags.includes(info.original_language)">
            <strong>lingua:</strong>
            <img
              :src="require(`../assets/${info.original_language}.svg`)"
              :alt="info.original_language"
            />
          </li>
          <!-- :src="
            'https://raw.githubusercontent.com/lipis/flag-icon-css/6c93c71ab3ddaf7a1f0b580322c293f610f716ae/flags/1x1/' +
            info.original_language +
            '.svg' -->
          <li v-else>
            <strong>Lingua: {{ info.original_language }}</strong>
          </li>
          <li>
            Voto: {{ vote }}
            <i
              v-for="(star, index) in this.vote"
              :key="index"
              class="bi bi-star-fill purple"
            ></i>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["info"],
  data() {
    return {
      flags: ["en", "it"],
      vote: "",
    };
  },
  mounted() {
    this.function();
  },
  methods: {
    function() {
      const numerodecimale = Math.floor(this.info.vote_average / 2);
      this.info.vote_avarage = numerodecimale;
      console.log(numerodecimale);
      this.vote = numerodecimale;
    },
  },
};
</script>


<style scoped lang="scss">
@import "@/style/common.scss";

ul {
  list-style: none;
}
.card {
  height: 400px;
  width: 350px;
  border-radius: 10px;
  position: relative;
  img {
    display: block;
    width: 100%;
    height: 100%;
    border-radius: 10px;
    background-size: cover;
  }
  li > img {
    height: 10%;
    width: 10%;
  }
  .overlay {
    position: absolute;
    text-align: center;
    border-radius: 8px;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    height: 100%;
    width: 100%;
    opacity: 0;
    transition: 0.5s ease;
    background-color: #141414;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  }
}
.id:hover .overlay {
  opacity: 1;
  cursor: pointer;
}
.text {
  color: white;
  font-size: 20px;
  position: absolute;
  top: 40%;
  left: 40%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  text-align: center;
}
.purple {
  color: purple;
}
</style>
