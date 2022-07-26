<template>
  <div class="disc text-center m-3 col-2 p-3">
    <img class="album" :src="image" />
    <div class="title mt-2">{{ title }}</div>
    <div class="info">
      {{ author }}
      {{ year }}
    </div>
  </div>
</template>

<script>
export default {
  name: "MyArtists",
   props: ["image", "title", "author", "year"],

};
</script>

<style lang="scss" scoped>
@import "../assets/scss/vars";
.disc {
  background-color: $primary-color;
}
.album {
  width: 90%;
}
.title {
  color: white;
  font-size: 15px;
  text-transform: uppercase;
  font-weight: bold;
}
.info {
  font-size: 12px;
  color: #b0a69f;
}
</style> 