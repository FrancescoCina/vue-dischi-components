<template>
  <div class="albums-container">
    <div class="container">
      <div class="row">
        <div
          v-for="(album, index) in albums"
          :key="index"
          class="col my-2 d-flex justify-content-center align-items-center"
        >
          <Album :album="album"></Album>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Album from "@/components/Album.vue";
export default {
  name: "Albums",
  components: { Album },
  props: ["albums"],
};
</script>

<style scoped lang="scss">
@import "../assets/scss/_vars.scss";

.albums-container {
  height: calc(100vh - 100px);
  background-color: $body-color;
}

.col {
  flex-basis: calc(100% / 5);
}
</style>