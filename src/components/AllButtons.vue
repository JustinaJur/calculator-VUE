<template>
  <table v-on:click="handleClick">
    <tbody>
      <td>7</td>
      <td>8</td>
      <td>9</td>
      <td>/</td>
      <td>4</td>
      <td>5</td>
      <td>6</td>
      <td>*</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>.</td>
      <td>0</td>
      <td>-</td>
      <td>+</td>
      <td class="result">=</td>
      <td class="clear">clear</td>
    </tbody>
  </table>
</template>

<script>
export default {
  name: "allButtons",
  methods: {
    handleClick(e) {
      console.log(e.target);
      this.$emit("handle-click", e);
    }
  }
};
</script>

<style scoped>
tbody {
  display: grid;
  grid-template-columns: repeat(4, 70px);
  grid-template-rows: repeat(5, 70px);
  border: 2px solid #85144b;
}
td {
  display: grid;
  place-items: center;
  border: 1px solid #85144b;
  background-color: #ffdc00;
  font-size: 30px;
  font-weight: 800;
}
td:hover {
  transform: scale(1.05);
}
.clear {
  grid-column: 1/4;
  background-color: #f012be;
}
.result {
  grid-column: 4;
  grid-row: span 2;
  background-color: #0074d9;
}
</style>
