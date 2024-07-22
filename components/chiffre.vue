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
import { finalcolor } from "../config";
var nombre = ref(0);

function updateNumber(action) {
  if (action === "moins" && nombre.value > 0) {
    nombre.value -= 1;
  } else if (action === "plus") {
    nombre.value += 1;
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
