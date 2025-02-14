<script>
import Popup from './Popup.vue';

export default {
  name: 'GameBox',
  components: {
    Popup
  },
  data() {
    return {
      selectedGame: null,
      showPopup: false
    };
  },
  methods: {
    closePopup() {
      this.showPopup = false;
    },
    showGameDetails(game) {
      this.selectedGame = game;
      this.showPopup = true;
    }
  },
  props: {
    games: Array,
    year: String
  }
};
</script>

<template>
  <section class="game-container">
    <h2>Games From Year {{ year }}</h2>
    <div class="games-flex">
      <div @click="showGameDetails(game)" v-for="game in games" :key="game.id" class="game-card">
        <img :src="game.background_image" alt="Game Image" class="game-image">
        <h3>{{ game.name }}</h3>
        <p>Release Date: {{ game.released }}</p>
        <img class="rating-star" src="/assets/star.png" alt="">
        <p>{{ game.rating }} / {{ game.rating_top }}</p>
      </div>
    </div>
    <Popup v-if="showPopup" :game="selectedGame" @close="closePopup" />
  </section>
</template>

<style scoped>
.game-card {
  align-items: center;
  background-color: #1012147a;
  border-radius: 20px;
  box-shadow: rgba(0, 0, 0, 0.07) 0px 1px 2px, rgba(0, 0, 0, 0.07) 0px 2px 4px, rgba(0, 0, 0, 0.07) 0px 4px 8px, rgba(0, 0, 0, 0.07) 0px 8px 16px, rgba(0, 0, 0, 0.07) 0px 16px 32px, rgba(0, 0, 0, 0.07) 0px 32px 64px;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  height: 450px;
  justify-content: center;
  margin: 15px;
  text-align: center;
  transition: transform 0.2s;
  width: 280px;
}

.game-card:hover {
  transform: scale(1.05);
}

.game-card p {
  color: #dacf6e;
  font-size: 1.1em;
  margin: 5px 0;
}

.game-container {
  height: 50vh;
  margin: 50px;
  width: 90%;
}

.game-image {
  border-radius: 20px;
  height: 200px;
  margin-top: 15px;
  object-fit: cover;
  width: 250px;
}

.games-flex {
  align-items: center;
  display: flex;
  flex-wrap: wrap;
  height: auto;
  justify-content: center;
  padding: 70px;
}

h2 {
  color: white;
  text-align: center;
  width: 100%;
}

h3 {
  color: #bbdce0;
  font-size: 1.2em;
  margin: 10px 0;
}

.rating-star {
  height: 25px;
  width: 25px;
}
</style>