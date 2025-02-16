<script></script>

<template>
  <div class="me">
    <img class="karol-img" src="../../assets/Karol3Ed.jpg">
    <h2>Karol Melnicki</h2>
    <h3>Front-end developer</h3>

    <div class="icons-container">
     <a href="https://github.com/KarolMel"> <img class="icon" src="../../assets/icons/github.png"> </a>
     <a href="mailto:karol.melnicki1999@gmail.com"> <img class="icon" src="../../assets/icons/gmail-logo.png"> </a>
     <a href="www.linkedin.com/in/karol-melnicki-209879263/"> <img class="icon" src="../../assets/icons/linkedin.png"> </a>
    </div>
  </div>
</template>

<style scoped>
.icon {
  cursor: pointer;
  height: 60px;
  margin: 20px;
  transition: transform 0.4s;
  width: 60px;
}

.icon:hover {
  transform: scale(1.1);
}

.karol-img {
  border-radius: 10px;
  height: 500px;
  margin: 10px;
  object-fit: cover;
  width: 250px;
}

.me {
  align-items: center;
  background: rgba(37, 88, 58, 0.226);
  background: linear-gradient(0deg, rgba(37, 88, 58, 0.158) 18%, rgba(240, 238, 243, 0.164) 82%);
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  height: 80vh;
  justify-content: start;
  margin: -5px 0 -60px;
  width: 420px;
}

h2, h3 {
  color: white;
  font-family: monospace;
  letter-spacing: 3px;
}

h3 {
  color: rgb(99, 226, 99);
}

@media (min-width: 360px) and (max-width: 980px) {
  .me {
    height: 80vh;
    width: 400px;
  }
}
</style>