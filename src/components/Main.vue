<template>
  <AllButtons @handle-click="handleClick"/>
</template>

<script>
import AllButtons from "./AllButtons.vue";

export default {
  name: "main",
  components: {
    AllButtons
  },
  methods: {
    handleClick(e) {
      this.$emit("handle-click", e);
    }
  }
};
</script>
<style>
</style>
