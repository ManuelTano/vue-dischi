<template>
  <div id="app">
    <MyHeader :genres-list="genresList" @genre-change="setSelectedGenre"/>
    <SectionCard :selected-genre="selectedGenre" @fetched-genres="setGenresList"/>
  </div>
</template>

<script>
import MyHeader from "./components/MyHeader";
import SectionCard from "./components/SectionCard";
export default {
  name: 'App',
  components: {
    MyHeader,
    SectionCard,
  },
  data() {
    return {
      selectedGenre: "",
      genresList: ["Rock", "Pop", "Metal", "Jazz"],
    };
  },
  methods: {
    setSelectedGenre(genre) {
      this.selectedGenre = genre; 
    },
    setGenresList(genres) {
      this.genresList = genres;
    }
  }
}
</script>

<style lang="scss">
@import "./assets/scss/style.scss";

</style>
