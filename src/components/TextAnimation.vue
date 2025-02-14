<script>
export default {
  name: 'TextAnimation',
  data() {
    return {
      name: 'About Me',
    };
  },
  mounted() {
    this.writher();
  },
  methods: {
    writher() {
      let i = 0;
      const typeLetter = () => {
        if (i < this.name.length) {
          document.querySelector('.text').textContent += this.name.charAt(i);
          i++;
          setTimeout(typeLetter, 70);
        }
      };
      typeLetter();
    }
  }
};
</script>

<template>
  <div class="text-animation">
    <h1 class="text"></h1>
  </div>
</template>

<style scoped>
.text-animation {
  color: white;
  height: 100px;
  letter-spacing: 10px;
  position: absolute;
  top: 6%;
  white-space: nowrap;
  width: auto;
}

.text-animation::after {
  animation: blink 1s infinite;
  background-color: white;
  content: '';
  display: block;
  height: 25px;
  width: 3px;
}

@keyframes blink {
  0%, 100% {
    background-color: white;
  }
  50% {
    background-color: transparent;
  }
}

@media (min-width: 360px) and (max-width: 980px) {
  .text-animation {
    align-items: center;
    display: flex;
    justify-content: center;
  }
}
</style>