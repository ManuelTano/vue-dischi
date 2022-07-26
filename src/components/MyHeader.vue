<template>
    <header>
      <div class="px-3 h-100 d-flex align-items-center">
        <img src="../assets/spotify.png" alt="Spotify Logo" />
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
img {
  height: 50%;
}
</style> 