<template>
  <div class="bloc-recherche__noir">
    <h1 class="bloc-recherche__title">
      Trouvez le code secret pour débloquer la suite
    </h1>
    <div class="bloc-recherche">
      <Chiffre ref="chiffre-1" number="1" />
      <Chiffre ref="chiffre-2" number="2" />
      <Chiffre ref="chiffre-3" number="3" />
      <Chiffre ref="chiffre-4" number="4" />
    </div>
    <div class="bloc-recherche__aide"><p>Cherchez ici !</p></div>
    <div class="bloc-recherche__numero1 numero">
      <p class="bloc-recherche__text">5</p>
    </div>
    <div class="bloc-recherche__numero2 numero">
      <p class="bloc-recherche__text">2</p>
    </div>
    <div class="bloc-recherche__numero3 numero">
      <p class="bloc-recherche__text">9</p>
    </div>
    <div class="bloc-recherche__numero4 numero">
      <p class="bloc-recherche__text">6</p>
    </div>
  </div>
</template>

<style scoped lang="scss">
.numero {
  color: black;
  font-family: Alfa;
  font-size: 50px;
  margin: 0px;
}

.bloc-recherche {
  display: flex;
  justify-content: center;

  &__aide {
    color: black;
    margin-top: 50px;
    display: flex;
    font-family: Alfa;
    font-size: 40px;
    justify-content: center;

    &:hover {
      color: white;
    }
  }

  &__title {
    color: v-bind(finalcolor);
    margin-top: 150px;
    display: flex;
    font-family: Alfa;
    font-size: 60px;
    justify-content: center;
    transition: 2s;
  }

  &__text:hover {
    color: white;
  }

  &__numero1 {
    display: flex;
    justify-content: center;
    margin-top: 200px;
    margin-left: 500px;
  }

  &__numero2 {
    display: flex;
    justify-content: center;
    margin-right: 500px;
    margin-top: 500px;
  }

  &__numero3 {
    display: flex;
    justify-content: center;
    margin-top: 300px;
  }

  &__numero4 {
    display: flex;
    margin-top: 300px;
  }

  &__noir {
    background-color: black;
    height: 100vh;
  }
}
</style>

<script setup>
import { finalcolor } from "../config";
</script>
