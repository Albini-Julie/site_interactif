<template>
  <!--Caroussel-->
  <div class="container">
    <input type="radio" name="slider" id="item-1" checked />
    <input type="radio" name="slider" id="item-2" />
    <input type="radio" name="slider" id="item-3" />
    <input type="radio" name="slider" id="item-4" />
    <input type="radio" name="slider" id="item-5" />
    <input type="radio" name="slider" id="item-6" />
    <div class="cards">
      <!--Items-->
      <label class="card" for="item-1" id="song-1" @click="Select(1)">
        <Ball class="ball" color="#FF00C7" />
      </label>
      <label class="card" for="item-2" id="song-2" @click="Select(2)">
        <Ball class="ball" color="#8438FF" />
      </label>
      <label class="card" for="item-3" id="song-3" @click="Select(3)">
        <Ball class="ball" color="#FF7A00" />
      </label>
      <label class="card" for="item-4" id="song-4" @click="Select(4)">
        <Ball class="ball" color="#FF0000" />
      </label>
      <label class="card" for="item-5" id="song-5" @click="Select(5)">
        <Ball class="ball" color="#00FF00" />
      </label>
      <label class="card" for="item-6" id="song-6" @click="Select(6)">
        <Ball class="ball" color="#0000FF" />
      </label>
    </div>
  </div>
</template>

<script setup>
import { selectcolor } from "../config.js";

function Select(number) {
  if (number == 1) {
    selectcolor.value = "#FF00C7";
  } else if (number == 2) {
    selectcolor.value = "#8438FF";
  } else if (number == 3) {
    selectcolor.value = "#FF7A00";
  } else if (number == 4) {
    selectcolor.value = "#FF0000";
  } else if (number == 5) {
    selectcolor.value = "#00FF00";
  } else {
    selectcolor.value = "#0000FF";
  }
  console.log(selectcolor.value);
}
</script>

<style lang="scss">
input[type="radio"] {
  display: none;
}
.card {
  position: absolute;
  width: max-content;
  height: max-content;
  left: 0;
  right: 0;
  margin: auto;
  transition: transform 0.4s ease;
  cursor: pointer;
}

.container {
  width: 100%;
  max-width: 800px;
  max-height: 450px;
  height: 100%;
  transform-style: preserve-3d;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}

.cards {
  position: relative;
  width: 100%;
  height: 100%;
  margin-bottom: 20px;
}

#item-1:checked ~ .cards #song-6,
#item-2:checked ~ .cards #song-1,
#item-3:checked ~ .cards #song-2,
#item-4:checked ~ .cards #song-3,
#item-5:checked ~ .cards #song-4,
#item-6:checked ~ .cards #song-5 {
  transform: translatex(-40%) scale(1);
  opacity: 0.6;
  z-index: 1;
}

#item-1:checked ~ .cards #song-5,
#item-2:checked ~ .cards #song-6,
#item-3:checked ~ .cards #song-1,
#item-4:checked ~ .cards #song-2,
#item-5:checked ~ .cards #song-3,
#item-6:checked ~ .cards #song-4 {
  transform: translatex(-80%) scale(0.8);
  opacity: 0.6;
  z-index: 0;
}

#item-1:checked ~ .cards #song-2,
#item-2:checked ~ .cards #song-3,
#item-3:checked ~ .cards #song-4,
#item-4:checked ~ .cards #song-5,
#item-5:checked ~ .cards #song-6,
#item-6:checked ~ .cards #song-1 {
  transform: translatex(40%) scale(1);
  opacity: 0.6;
  z-index: 1;
}

#item-1:checked ~ .cards #song-3,
#item-2:checked ~ .cards #song-4,
#item-3:checked ~ .cards #song-5,
#item-4:checked ~ .cards #song-6,
#item-5:checked ~ .cards #song-1,
#item-6:checked ~ .cards #song-2 {
  transform: translatex(80%) scale(0.8);
  opacity: 0.6;
  z-index: 0;
}

#item-1:checked ~ .cards #song-1,
#item-2:checked ~ .cards #song-2,
#item-3:checked ~ .cards #song-3,
#item-4:checked ~ .cards #song-4,
#item-5:checked ~ .cards #song-5,
#item-6:checked ~ .cards #song-6 {
  transform: translatex(0) scale(1.2);
  opacity: 1;
  z-index: 50;
}
</style>
