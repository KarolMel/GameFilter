<script>
export default {
  name: 'Navigation'
}
</script>

<template>
  <nav>
    <router-link to="/">Hem</router-link>
    <router-link to="/contact">Kontakt</router-link>
    <router-link to="/about">Om mig</router-link>
  </nav>
</template>

<style scoped>
a {
  align-items: center;
  border-radius: 4px;
  color: rgb(255, 255, 255);
  display: flex;
  font-family: 'Courier New', Courier, monospace;
  font-size: 22px;
  height: 90%;
  justify-content: center;
  margin-bottom: 5px;
  text-decoration: none;
  transition: all 0.5s ease-in-out;
  width: 130px;
}

a:hover {
  background-color: rgba(238, 238, 238, 0.678);
  color: black;
  text-decoration: underline;
}

nav {
  align-items: center;
  border-bottom: solid 1px rgba(255, 255, 255, 0.432);
  display: flex;
  gap: 10px;
  height: 60px;
  padding: 0 20px;
  width: 100%;
}
</style>