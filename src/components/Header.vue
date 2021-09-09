<template>
  <header>
    <div class="h-100 d-flex justify-content-between align-items-center">
      <img class="ms-4 img-fluid" src="@/assets/img/logo.png" alt="Logo" />
      <div class="select me-3">
        <Select
          @passSelectValue="catchSelectValue"
          :genres="singleGenre"
        ></Select>
      </div>
    </div>
  </header>
</template>

<script>
import Select from "@/components/Select.vue";

export default {
  name: "Header",
  components: { Select },
  props: ["albums"],
  data() {
    return {
      allGenres: [],
      headerSelectValue: "",
    };
  },
  methods: {
    catchSelectValue(selectValue) {
      this.headerSelectValue = selectValue;
      this.$emit("passHeaderSelectValue", this.headerSelectValue);
    },
  },
  computed: {
    singleGenre() {
      this.albums.forEach((album) => {
        this.allGenres.push(album.genre);
      });
      const singleGenres = [];
      this.allGenres.forEach((genre) => {
        if (!singleGenres.includes(genre)) {
          singleGenres.push(genre);
        }
      });
      return singleGenres;
    },
  },
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