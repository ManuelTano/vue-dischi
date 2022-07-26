<template>
  <div class="disc">
    <img class="album" :src="image" />
    <div class="title">{{ title }}</div>
    <div class="info">
      {{ author }}
      {{ year }}
    </div>
  </div>
</template>

<script>
export default {
  name: "MyArtists",
  props: {
    poster: String,
    title: String,
    author: String,
    year: String,
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/vars";

</style> 