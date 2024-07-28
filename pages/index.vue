<template>
  <Felicitation v-if="condition" />
  <Background
    class="index__fond"
    :color="finalcolor"
    v-if="condition == false"
  />
  <div class="index__content" v-if="condition == false">
    <h1
      ref="title"
      class="index__title"
      :class="className"
      :style="styleObject"
    >
      Choississez une couleur parmi celles proposées ! - Choississez une couleur
      parmi celles proposées !- Choississez une couleur parmi celles proposées !
      - Choississez une couleur parmi celles proposées !
    </h1>
    <div class="index__stop">
      <Bouton color="#FCD139" text="Stop !!" @click="Animation" />
    </div>
    <Balls />
    <Bouton
      @click="SelectColor"
      :color="selectcolor"
      text="Choisir cette couleur"
    />
  </div>
  <BlocRecherche v-if="condition == false" />
</template>

<style lang="scss">
.animation {
  animation: defilement 10s infinite linear;
}
.index {
  &__title {
    font-family: Alfa;
    color: white;
    margin: 50px 0px;
    font-size: 40px;
    background: rgba(0, 0, 0, 0.7);
    white-space: nowrap;
    padding: 20px 40px;
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

  &__stop {
    display: flex;
    justify-content: end;
    width: 90%;
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
import { ref } from "vue";
import { selectcolor, finalcolor, condition } from "../config";

function SelectColor() {
  finalcolor.value = selectcolor.value;
  console.log("couleur finale :", finalcolor.value);
}

var className = ref("animation");
var test = ref(true);
var styleObject = ref({});

const title = ref(null);

function Animation() {
  if (test.value) {
    const computedStyle = window.getComputedStyle(title.value);
    const marginLeft = computedStyle.marginLeft;
    styleObject.value = {
      marginLeft: marginLeft,
      animation: "none",
    };
    className.value = "animation-none";
  } else {
    styleObject.value = {};
    className.value = "animation";
  }
  test.value = !test.value;
}
</script>
