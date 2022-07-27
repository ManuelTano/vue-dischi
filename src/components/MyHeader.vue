<template>
  <header>
    <div class="row px-3 h-100 justify-content-between">
      <div class="col-6 d-flex h-100 align-items-center">
        <div class="image">
          <img src="../assets/spotify.png" alt="Spotify Logo" />
        </div>
      </div>
      <div class="col-2 d-flex text-end h-100 align-items-center">
        <select class="form-select" name="genre" id="genres">
          <option value="allGenres" selected>Seleziona un genere</option>
          <option value="rock">Rock</option>
          <option value="jazz">Jazz</option>
          <option value="pop">Pop</option>
          <option value="metal">Metal</option>
        </select>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "BaseHeader",
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