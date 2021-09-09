<template>
  <div>
    <label class="white me-3" for="select-genres">Seleziona un genere</label>
    <select v-model="genre" id="select-genres">
      <option selected value="all">All</option>
      <option v-for="(genre, index) in genres" :key="index" :value="genre">
        {{ genre }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "Select",
  props: ["genres"],
  data() {
    return {
      genre: "",
    };
  },
};
</script>

<style scoped lang="scss">
.white {
  color: #fff;
}
</style>