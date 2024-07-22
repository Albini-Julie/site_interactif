<template>
  <svg
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
    style="width: 100px; height: 100px; position: relative"
    preserveAspectRatio="none"
  >
    <path
      d="M31.3561 25.677L69.9811 47.977C71.5381 48.876 71.5381 51.124 69.9811 52.023L31.3561 74.323C29.7991 75.222 27.8521 74.098 27.8521 72.3V27.7C27.8521 25.902 29.7981 24.778 31.3561 25.677Z"
      :fill="color"
    ></path>
  </svg>
</template>

<script setup>
defineProps({
  color: String,
});
</script>
