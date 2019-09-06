<template>
  <b-container>
    <b-row class="ml-auto mr-auto text-center">
      <h3>Final Fantasy Games</h3>
    </b-row>
    <b-row>
      <Game
        v-for="game in games"
        :key="game.id"
        :title="game.title"
        :platform="game.platform"
        :releaseDate="game.releaseDate"
        :picture="game.picture"
      />
    </b-row>
  </b-container>
</template>


<script>
import axios from 'axios'
import Game from './Game'
export default {
  name: 'GameContainer',
  components: {
    Game
  },
  data() {
    return {
      games: []
    };
  },
  mounted: function() {
    this.getGames();
  },
  methods: {
    getGames() {
      axios.get("https://www.moogleapi.com/api/v1/games").then(response => {
        this.games = response.data;
      });
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
