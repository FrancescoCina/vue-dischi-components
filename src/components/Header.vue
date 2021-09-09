<template>
  <header>
    <div class="h-100 d-flex justify-content-between align-items-center">
      <img class="ms-4 img-fluid" src="@/assets/img/logo.png" alt="Logo" />
      <div class="search"></div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped lang="scss">
@import "../assets/scss/_vars.scss";
header {
  height: 100px;
  background-color: $header-color;
}

img {
  width: 50px;
  height: 50px;
}
</style>