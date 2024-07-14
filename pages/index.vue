<template>
  <Background class="index__fond" :color="finalcolor" />
  <div class="index__content">
    <h1 class="index__title">
      Choississez une couleur parmi celles proposées !
    </h1>
    <Balls />
    <Bouton @click="SelectColor" :color="selectcolor" />
  </div>
</template>

<style lang="scss">
.index {
  &__title {
    font-family: Alfa;
    color: white;
    margin: 50px;
    font-size: 40px;
  }
  &__fond {
    z-index: 0;
    position: absolute;
  }

  &__content {
    z-index: 50;
    position: relative;
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
}
</style>

<script setup>
import { selectcolor, finalcolor } from "../config";
function SelectColor() {
  finalcolor.value = selectcolor.value;
  console.log("couleur finale :", finalcolor.value);
}
</script>
