<template>
  <div id="app">
    <Header @passHeaderSelectValue="catchHeaderSelectValue" :albums="albums" />
    <Albums :albums="filteredAlbums" />
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
      appSelectValue: "",
    };
  },
  methods: {
    catchHeaderSelectValue(valueFromHeader) {
      this.appSelectValue = valueFromHeader;
    },
  },
  computed: {
    filteredAlbums() {
      const filteredAlbums = [];
      this.albums.forEach((album) => {
        if (album.genre.includes(this.appSelectValue)) {
          filteredAlbums.push(album);
        }
      });
      return filteredAlbums;
    },
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
