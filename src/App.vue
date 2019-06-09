<template>
  <div id="app">
    <div class="calculator">
      <h1>Calculator</h1>
      <Screen :screen="screen"/>
      <Main @handle-click="handleClick"/>
    </div>
  </div>
</template>

<script>
import Screen from "./components/Screen.vue";
import Main from "./components/Main.vue";

export default {
  name: "app",
  components: {
    Main,
    Screen
  },
  data() {
    return {
      screen: ""
    };
  },
  methods: {
    handleClick(e) {
      let inputValue = e.target.innerText;
      if (e.target.tagName === "TD") {
        try {
          if (inputValue === "=") {
            this.screen = eval(this.screen);
          } else if (inputValue === "clear") {
            this.screen = "";
          } else {
            this.screen = this.screen + inputValue;
          }
        } catch (err) {
          this.screen = "error";
        }
      }
    }
  }
};
</script>

<style scoped>
#app {
  display: grid;
  place-items: center;
  padding: 50px;
}
.calculator {
  border: 4px solid#85144b;
  background-color: #39cccc;
  text-align: center;
}
</style>