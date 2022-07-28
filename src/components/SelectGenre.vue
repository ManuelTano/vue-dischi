<template>
  <select class="form-select" v-model="selectedOption" @change="changeOption">
    <option value="">{{ placeholder || "Select an option" }}</option>
    <option v-for="option in options" :key="option.value || option" :value="option.value || option">
      {{ option.label || option }}
    </option>
  </select>
</template>

<script>
export default {
  name: "SelectGenre",
  data() {
    return {
      selectedOption: "",
    };
  },
  props: {
    placeholder: String,
    options: Array,
  },
  methods: {
    changeOption() {
      this.$emit("option-change", this.selectedOption);
    },
  },
};
</script>

<style>
</style> 