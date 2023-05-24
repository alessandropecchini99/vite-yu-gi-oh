<script>
export default {};
</script>

<template>
  <div>
    <i class="fa-solid fa-circle-notch rotate-icon"></i>
  </div>
</template>

<style lang="scss" scoped>
div {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.rotate-icon {
  animation: rotate 1s linear infinite;
  color: black;
  font-size: 10em;
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
