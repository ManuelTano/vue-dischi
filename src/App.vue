<template>
  <div id="app">
    <MyHeader />
    <SectionCard />
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
  }
}
</script>

<style lang="scss">
@import "./assets/scss/style.scss";

</style>
