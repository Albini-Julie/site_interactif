<template>
  <Background class="index__fond" :color="finalcolor" />
  <div class="index__content">
    <h1 class="index__title">
      Choississez une couleur parmi celles proposées ! - Choississez une couleur
      parmi celles proposées !- Choississez une couleur parmi celles proposées !
      - Choississez une couleur parmi celles proposées !
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
    margin: 50px 0px;
    font-size: 40px;
    background: rgba(0, 0, 0, 0.7);
    white-space: nowrap;
    padding: 20px 40px;
    animation: defilement 10s infinite linear;
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
    overflow-x: hidden;
  }
}

@keyframes defilement {
  0% {
    margin-left: 0;
  }
  100% {
    margin-left: -100%;
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
