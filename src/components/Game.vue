<template>
  <b-col class="game-container" cols="4">
    <b-card>
      <img class="game-image" :src="picture" alt>
      <h4>{{ title }}</h4>
      <h6>{{ platform }} - {{ releaseDate }}</h6>
    </b-card>
  </b-col>
</template>



<script>
export default {
  name: "Game",
  props: {
    title: String, 
    platform: String,
    releaseDate: String,
    picture: String
  }
};
</script>

<style scoped>
.game-image {
  width: 200px;
  height: 200px;
}

.game-container {
  margin-bottom: 2%;
  text-align: center;
}
</style>
