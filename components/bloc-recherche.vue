<template>
  <div class="bloc-recherche__noir">
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
  <div class="bloc-recherche">
    <Chiffre />
    <Chiffre />
    <Chiffre />
    <Chiffre />
  </div>
</template>

<style scoped lang="scss">
.numero {
  color: black;
  font-family: Alfa;
  font-size: 30px;
}

.bloc-recherche {
  display: flex;
  justify-content: center;

  &__text:hover {
    color: white;
  }

  &__numero1 {
    display: flex;
    justify-content: center;
    margin-top: 300px;
    transition: 2s;
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

<script setup></script>
