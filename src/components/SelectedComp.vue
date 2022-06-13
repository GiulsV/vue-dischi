<template>
  <select v-model="selectedOption" @change="changeOption">
    <option value="">
        {{ label }}
    </option>
    <option v-for="option in options" :key="option" :value="option">
        {{ option }}
    </option>
  </select>
</template>

<script>
export default {
  name: "SelectedComp",
  props: {
    label: String,
    options: Array,
  },
  data() {
    return {
      selectedOption: "",
    };
  },
  methods: {
    changeOption() {
      this.$emit("changedOption", this.selectedOption);
    },
  },
};
</script>

<style></style>
