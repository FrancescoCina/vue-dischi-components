<template>
  <div class="card-album text-center p-4">
    <div class="img-container">
      <img class="img-fluid" :src="album.poster" :alt="album.title" />
    </div>
    <h4 class="mb-2">{{ album.title }}</h4>
    <h6 class="mb-2">{{ album.author }}</h6>
    <h6 class="mb-2">{{ album.year }}</h6>
  </div>
</template>

<script>
export default {
  name: "Album",
  props: ["album"],
};
</script>

<style scoped lang="scss">
@import "../assets/scss/_vars.scss";
.card-album {
  background-color: $header-color;
  .img-container {
    height: 300px;
  }
  h4 {
    color: #fff;
  }
  h6 {
    color: darkgray;
  }
}
</style>