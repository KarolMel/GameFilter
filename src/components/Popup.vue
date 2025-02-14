<script>
export default {
  name: 'Popup',
  props: {
    game: Object
  },
  methods: {
    close() {
      this.$emit('close');
    }
  }
};
</script>

<template>
  <section class="popup">
    <section class="game-details" v-if="game">
      <button @click="close" class="close-details">X</button>
      <h2>{{ game.name }}</h2>
      <p>Platform: {{ game.platforms[0].platform.name }}</p>
      <p>Screenshots</p>
      <img v-for="screenshot in game.short_screenshots" :src="screenshot.image" :key="screenshot.id" alt="Game Screenshot" class="screenshots">
    </section>
  </section>
</template>

<style scoped>
.popup {
  align-items: center;
  backdrop-filter: blur(2px);
  background-color: rgba(0, 0, 0, 0.836);
  display: flex;
  height: 100vh;
  justify-content: center;
  left: 0;
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 100;
}

.game-details {
  background: rgba(159, 71, 8, 0.432);
  background: linear-gradient(0deg, rgba(151, 170, 81, 0.171) 18%, rgba(219, 165, 165, 0.384) 82%);
  border-radius: 20px;
  color: rgb(255, 255, 255);
  font-family: monospace;
  font-size: 22px;
  height: auto;
  text-align: center;
  top: 20vh;
  padding-bottom: 50px;
  width: 60%;
}

.close-details {
  background: none;
  border: none;
  color: white;
  cursor: pointer;
  font-size: 30px;
  font-weight: bold;
  height: 50px;
  left: -45%;
  position: relative;
  width: 50px;
}

.screenshots {
  border: solid 2px rgb(139, 139, 139);
  border-radius: 10px;
  height: 120px;
  margin: 10px;
  object-fit: cover;
  transition: all 0.3s ease-in-out;
  width: 120px;
}

.screenshots:hover {
  transform: scale(2.6);
}

@media (min-width: 360px) and (max-width: 980px) {
  .popup {
    height: 120vh;
    width: 100%;
  }

  .game-details {
    flex-wrap: wrap;
    height: auto;
    width: 90%;
  }

  .screenshots {
    height: 80px;
    width: 80px;
  }
}
</style>