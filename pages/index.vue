<template>
  <Background class="fond" />
  <div class="content">
    <Ball />
  </div>
</template>

<style lang="scss">
.fond {
  z-index: 0;
  position: absolute;
}

.content {
  z-index: 50;
  position: relative;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>

<script setup></script>
