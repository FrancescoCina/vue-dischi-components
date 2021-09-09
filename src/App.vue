<template>
  <div id="app">
    <Header :albums="albums" />
    <Albums :albums="albums" />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Albums from "@/components/Albums.vue";
import axios from "axios";

export default {
  name: "App",
  components: { Header, Albums },
  data() {
    return {
      albums: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.albums = res.data.response;
      });
  },
};
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
</style>
