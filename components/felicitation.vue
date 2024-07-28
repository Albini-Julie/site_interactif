<template>
  <div class="felicitation">
    <div class="felicitation__confettis">
      <div v-for="i in 25" :key="i">
        <Confetis
          :color="i % 2 === 0 ? 'pink' : 'blue'"
          :delay="i % 2 === 0 ? '5s' : '7s'"
        />
        <Confetis
          :color="i % 2 === 0 ? 'orange' : 'yellow'"
          :delay="i % 2 === 0 ? '6s' : '8s'"
        />
        <Confetis
          :color="i % 2 === 0 ? 'red' : 'green'"
          :delay="i % 2 === 0 ? '4s' : '9s'"
        />
      </div>
    </div>
    <div class="felicitation__box">
      <h1 class="felicitation__title">FÉLICITATION !!!</h1>
    </div>
  </div>
</template>

<style scoped lang="scss">
.felicitation {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  animation: backcolor 15s ease-in infinite;
  position: relative;

  &__confettis {
    z-index: 10;
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    pointer-events: none;
    display: flex;
    gap: 20px;
    overflow-x: hidden;
  }

  &__title {
    font-family: Alfa;
    color: pink;
    font-size: 180px;
    animation: color 10s ease-in infinite, vibration 0.3s infinite;
    margin: 0;
    z-index: 50;
    text-align: center;
  }

  &__box {
    animation: boxcolor 5s ease-in infinite;
    padding: 50px;
    border-radius: 50px;
    z-index: 50;
  }
}

@keyframes vibration {
  0% {
    transform: translate(0, 0);
  }
  20% {
    transform: translate(-2px, 2px);
  }
  40% {
    transform: translate(2px, -2px);
  }
  60% {
    transform: translate(-2px, 2px);
  }
  80% {
    transform: translate(2px, -2px);
  }
  100% {
    transform: translate(0, 0);
  }
}

@keyframes boxcolor {
  0% {
    box-shadow: 0 0 300px 150px black;
  }
  10% {
    box-shadow: 0 0 300px 150px pink;
  }
  20% {
    box-shadow: 0 0 300px 150px fuchsia;
  }
  30% {
    box-shadow: 0 0 300px 150px blue;
  }
  40% {
    box-shadow: 0 0 300px 150px aqua;
  }
  50% {
    box-shadow: 0 0 300px 150px green;
  }
  60% {
    box-shadow: 0 0 300px 150px greenyellow;
  }
  70% {
    box-shadow: 0 0 300px 150px yellow;
  }
  80% {
    box-shadow: 0 0 300px 150px orange;
  }
  90% {
    box-shadow: 0 0 300px 150px red;
  }
  100% {
    box-shadow: 0 0 300px 150px black;
  }
}

@keyframes backcolor {
  0% {
    background-color: black;
  }
  10% {
    background-color: blue;
  }
  20% {
    background-color: pink;
  }
  30% {
    background-color: purple;
  }
  40% {
    background-color: red;
  }
  50% {
    background-color: orange;
  }
  60% {
    background-color: aqua;
  }
  70% {
    background-color: yellow;
  }
  80% {
    background-color: greenyellow;
  }
  90% {
    background-color: green;
  }
  100% {
    background-color: black;
  }
}

@keyframes color {
  0% {
    color: white;
  }
  10% {
    color: pink;
  }
  20% {
    color: yellow;
  }
  30% {
    color: red;
  }
  40% {
    color: fuchsia;
  }
  50% {
    color: purple;
  }
  60% {
    color: blue;
  }
  70% {
    color: aqua;
  }
  80% {
    color: green;
  }
  90% {
    color: greenyellow;
  }
  100% {
    color: white;
  }
}
</style>
