<template>
  <main>
     <div class="container">
      <div class="row justify-content-between py-5">
        <my-artists
          v-for="(artist, index) in albumsList"
          :key="index"
          :image="artist.poster"
          :title="artist.title"
          :author="artist.author"
          :year="artist.year"
        />
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import MyArtists from "./MyArtists.vue";
export default {
  name: "SectionCard",
  components: {
    MyArtists,
  },
    data() {
    return {
      albumsList: [],
    };
  },

  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        console.log(res.data);
        this.albumsList = res.data.response;
      });
  },
};
 
</script>

<style lang="scss" scoped>
@import "../assets/scss/vars";

main {
  background-color: $bg-color;
}

</style> 