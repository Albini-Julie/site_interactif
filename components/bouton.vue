<template>
  <div class="bouton">
    <p class="bouton__text">{{ text }}</p>
  </div>
</template>

<style lang="scss" scoped>
.bouton {
  background: v-bind(color);
  padding: 10px 40px;
  min-width: 200px;
  box-shadow: 10px 10px 5px #ffffff;
  cursor: pointer;
  color: #ffffff;
  transition: 0.4s;

  &__text {
    font-family: Alfa;
    font-size: 25px;
    text-align: center;
  }
}

.bouton:hover {
  background: black;
  border: solid 2px v-bind(color);
  box-shadow: 0px 0px 20px 10px v-bind(color);
  color: v-bind(color);
  animation: neon 2s infinite;
}
@keyframes neon {
  0%,
  100% {
    box-shadow: 0px 0px 10px 5px v-bind(color);
  }
  50% {
    box-shadow: 0px 0px 20px 10px v-bind(color);
  }
}
</style>

<script setup>
defineProps({
  color: String,
  text: String,
});
</script>
