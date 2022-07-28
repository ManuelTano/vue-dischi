<template>
  <main>
    <div class="container">
      <div class="row py-5">
        <my-artists
          v-for="(artist, index) in filteredDiscs"
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
  props: {
    selectedGenre: String,
  },
  computed: {
    filteredDiscs() {
      if (!this.selectedGenre) return this.albumsList;
      return this.albumsList.filter(
        (artist) => artist.genre === this.selectedGenre
      );
    },
  },
  data() {
    return {
      albumsList: [],
    };
  },
  methods: {
    fetchDiscs() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          this.albumsList = res.data.response;

          this.getGenresList();
        })
        .catch((err) => {
          console.log(err);
        });
    },

    getGenresList() {
      const genres = [];
      this.albumsList.forEach((artist) => {
        if (!genres.includes(artist.genre))
          genres.push(artist.genre);
      });
      this.$emit("fetched-genres", genres);
    },
  },

  created() {
    this.fetchDiscs();
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/vars";

main {
  background-color: $bg-color;
}
</style> 