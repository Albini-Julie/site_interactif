<template>
  <div class="confettis__box">
    <div class="confetis"></div>
  </div>
</template>

<style scoped lang="scss">
.confettis__box {
  min-width: 60px;
}
.confetis {
  width: 50px;
  height: 50px;
  background-color: v-bind(color);
  border-radius: 100%;
  z-index: 0;
  position: top;
  margin-top: -100px;
  animation: confettis v-bind(delay) ease-in infinite;
}

@keyframes confettis {
  0% {
    transform: translate(0);
    width: 50px;
  }
  50% {
    width: 25px;
  }
  100% {
    transform: translateY(120vh);
    width: 50px;
  }
}
</style>

<script setup>
defineProps({
  color: String,
  delay: String,
});
</script>
