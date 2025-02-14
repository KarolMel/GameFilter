<script>
import GameBox from '../components/GameBox.vue';

export default {
  components: {
    GameBox
  },
  name: 'Home',
  data() {
    return {
      logo: 'GameFilter',
      games: [],
      year: '',
      isLoading: false
    };
  },
  methods: {
    fetchGames() {
      const apiKey = '110ea2ab3de4482c870ffa76e75217cd';
      const search = document.querySelector('.search-input');
      const year = search.value;
      const url = `https://api.rawg.io/api/games?dates=${year}-01-01,${year}-12-31&ordering=-rating&page_size=40&key=${apiKey}`;

      if (!year) {
        return;
      } else if (year < 1958 || year > 2025) {
        alert('Please enter a year between 1958 and 2025');
        search.value = '';
        this.year = '';
        return;
      }

      search.value = '';

      this.isLoading = true;
      this.year = year;

      fetch(url)
        .then(response => response.json())
        .then(data => {
          this.games = data.results.filter(game => !game.tags.some(tag => tag.name === 'Erotic' || tag.name === 'hentai' || tag.name === 'sex'));
          this.isLoading = false;
          console.log(data);
        });
    }
  }
};
</script>

<template>
  <div class="games-container">
    <p class="loading-window" v-if="isLoading">Loading...</p>
    <h1>{{ logo }}</h1>
    <input v-model="year" class="search-input" type="number" placeholder="Sök efter spel" />
    <button @click="fetchGames" class="search-button">Sök</button>
    <GameBox :games="games" :year="year" />
  </div>
</template>

<style scoped>
.loading-window {
  align-items: center;
  background-color: rgba(0, 0, 0, 0.726);
  color: white;
  display: flex;
  font-size: 40px;
  height: 100vh;
  justify-content: center;
  position: absolute;
  width: 100%;
}

a {
  color: white;
  font-size: 30px;
}

button {
  background: #007bff;
  border: none;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  color: white;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
  margin-top: 20px;
  padding: 12px 24px;
  transition: all 0.3s ease;
}

button:active {
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.2);
  transform: translateY(2px);
}

button:hover {
  background: #0056b3;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
}

.games-container {
  align-items: center;
  display: flex;
  flex-direction: column;
  height: auto;
  justify-content: start;
  margin: 10px 0 10px 10px;
  overflow: auto;
  width: 99%;
}

h1 {
  color: white;
  font-size: 5rem;
  letter-spacing: 10px;
}

input {
  background: #fff;
  border: 2px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.05);
  font-size: 16px;
  outline: none;
  padding: 12px 16px;
  transition: all 0.3s ease;
  width: 280px;
}

input:focus {
  border-color: #007bff;
  box-shadow: 0 4px 12px rgba(0, 123, 255, 0.2);
}

@media (min-width: 360px) and (max-width: 980px) {
  h1 {
    font-size: 40px;
  }
}
</style>