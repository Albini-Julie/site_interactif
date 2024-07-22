<template>
  <div class="chiffre">
    <IconsFleche
      :color="finalcolor"
      class="chiffre__fleche"
      @click="updateNumber('moins')"
    />
    <div class="chiffre__bloc">
      <p class="chiffre__text">{{ nombre }}</p>
    </div>
    <IconsFleche :color="finalcolor" @click="updateNumber('plus')" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import {
  finalcolor,
  number1,
  number2,
  number3,
  number4,
  condition,
} from "../config";
const props = defineProps({
  number: Number,
});
var nombre = ref(0);

function updateNumber(action) {
  if (action === "moins" && nombre.value > 0) {
    nombre.value -= 1;
  } else if (action === "plus") {
    nombre.value += 1;
  }
  switch (props.number) {
    case "1":
      number1.value = nombre.value;
      break;
    case "2":
      number2.value = nombre.value;
      break;
    case "3":
      number3.value = nombre.value;
      break;
    case "4":
      number4.value = nombre.value;
      break;
  }
  // Test de la combinaison
  if (
    number1.value == "5" &&
    number2.value == "2" &&
    number3.value == "9" &&
    number4.value == "6"
  ) {
    console.log("Gagné !");
  }
}
</script>

<style lang="scss" scoped>
.chiffre {
  display: flex;
  align-items: center;
  &__bloc {
    background-color: v-bind(finalcolor);
    width: 40px;
    height: 40px;
    display: flex;
    padding: 15px 25px;
    justify-content: center;
    align-items: center;
    transition: 2s;
  }

  &__fleche {
    transform: rotate(180deg);
  }

  &__text {
    font-family: Alfa;
    color: white;
    font-size: 30px;
    margin: 0px;
  }
}
</style>
