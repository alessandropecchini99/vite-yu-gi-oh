<script>
export default {};
</script>

<template>
  <div>
    <div class="logo">
      <img
        src="https://3.bp.blogspot.com/-wLH_qbmRoJU/TZdYCkrQuZI/AAAAAAAAAw0/G1_uzsANMI8/s1600/yugioh+logo.png"
        alt="logo"
      />
      <h1>Yu-Gi-Oh! Api</h1>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "./../assets/variables.scss" as *;
div {
  background-color: white;
}

.logo {
  @include myContainer;
  height: 100px;
  display: flex;
  align-items: center;

  img {
    width: 180px;
    height: 90px;
  }

  h1 {
    padding-left: 1em;
  }
}
</style>
