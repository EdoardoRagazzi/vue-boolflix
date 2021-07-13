<template>
  <div class="card">
    <ul>
      <li>Titolo: {{ info.title }}</li>
      <li>Titolo.Originale: {{ info.original_title }}</li>
      <li>Lingua: {{ info.language }}</li>
      <li>Voto: {{ info.vote_avarage }}</li>
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
</style>
