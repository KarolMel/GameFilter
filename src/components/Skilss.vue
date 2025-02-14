<script></script>

<template>
  <div class="skills">
    <h2>My skills</h2>
    <div class="skills-icons">
      <p>Html
        <img class="icon" src="../../assets/icons/html-5.png">
      </p>
      <p>Css
        <img class="icon" src="../../assets/icons/css.png">
      </p>
      <p>JavaScript
        <img class="icon" src="../../assets/icons/js.png">
      </p>
      <p>Git
        <img class="icon" src="../../assets/icons/git.png">
      </p>
      <p>Vue.js
        <img class="icon" src="../../assets/icons/vue.png">
      </p>
    </div>
  </div>
</template>

<style scoped>
.skills {
  border-radius: 20px;
  height: 30vh;
  margin: 50px;
  text-align: center;
  width: 71%;
}

.skills-icons {
  align-items: center;
  display: flex;
  justify-content: center;
}

.icon {
  height: 100px;
  margin-top: 20px;
  width: 100px;
}

h2 {
  color: white;
  font-family: monospace;
}

p {
  align-items: center;
  color: white;
  display: flex;
  flex-direction: column;
  font-family: monospace;
  font-size: 25px;
  margin: 30px;
}

@media (min-width: 360px) and (max-width: 980px) {
  .skills {
    align-items: center;
    border: none;
    display: flex;
    flex-direction: column;
    height: auto;
    justify-content: center;
    width: 100%;
  }

  .skills-icons {
    flex-wrap: wrap;
    width: 100%;
  }
}

@media (min-width: 981px) and (max-width: 1400px) {
  .skills {
    border: none;
    height: auto;
    margin: 20px;
    width: 500px;
  }

  .skills-icons {
    flex-wrap: wrap;
  }
}
</style>