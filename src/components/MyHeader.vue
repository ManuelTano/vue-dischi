<template>
  <header>
    <div class="row px-3 h-100 justify-content-between">
      <div class="col-6 d-flex h-100 align-items-center">
        <div class="image">
          <img src="../assets/spotify.png" alt="Spotify Logo" />
        </div>
      </div>
      <div class="col-2 d-flex text-end h-100 align-items-center">
        <SelectGenre
          placeholder="Seleziona Genere"
          :options="genresList"
          @option-change="emitGenreChange"
        />
      </div>
    </div>
  </header>
</template>

<script>
import SelectGenre from "./SelectGenre.vue";
export default {
  name: "BaseHeader",
  components: {
    SelectGenre,
  },
  props: {
    genresList: Array,
  },
  methods: {
    emitGenreChange(genre) {
      this.$emit("genre-change", genre);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/vars";

header {
  background-color: $primary-color;
  height: 100px;
}

.image img {
  width: 20%;
}
</style> 