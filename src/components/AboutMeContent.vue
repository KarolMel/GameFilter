<script>
import Me from '../components/Me.vue';
import Skilss from '../components/Skilss.vue';

export default {
  components: {
    Me,
    Skilss
  },
  name: 'AboutMeContent',
  mounted() {
    this.slideOut();
  },
  methods: {
    slideOut() {
      setTimeout(() => {
        const div = document.querySelector('.content');
        div.classList.add('div-slide-out');
      }, 500);
    }
  }
};
</script>

<template>
  <div class="content">
    <Me />
    <Skilss />
  </div>
</template>

<style scoped>
.content {
  align-items: center;
  border-radius: 20px;
  display: flex;
  height: 70vh;
  justify-content: start;
  position: absolute;
  top: 120%;
  transition: all 1.5s;
  width: 80%;
  max-width: 100%;
}

.div-slide-out {
  top: 20%;
}

@media (min-width: 360px) and (max-width: 980px) {
  .content {
    align-items: center;
    display: flex;
    flex-direction: column;
    height: auto;
    justify-content: center;
  }
}
</style>