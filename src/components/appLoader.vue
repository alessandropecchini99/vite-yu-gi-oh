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
  display: flex;
  justify-content: center;
}

.rotate-icon {
  animation: rotate 2s linear infinite;
  color: black;
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
