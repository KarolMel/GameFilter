<script>
import AboutMeContent from '../components/AboutMeContent.vue';
import TextAnimation from '../components/TextAnimation.vue';

export default {
  components: {
    AboutMeContent,
    TextAnimation
  },
  data() {
    return {
      title: 'Om mig'
    };
  }
};
</script>

<template>
  <div>
    <TextAnimation />
    <AboutMeContent />
  </div>
</template>

<style scoped>
a {
  color: white;
  font-size: 30px;
}

div {
  align-items: center;
  display: flex;
  height: 85vh;
  justify-content: center;
  margin: 10px 0 10px 10px;
  width: 99%;
}

img {
  border-radius: 5px;
  height: 590px;
  left: 10%;
  margin: 10px;
  position: absolute;
  width: 400px;
}

@media (min-width: 360px) and (max-width: 980px) {
}
</style>