<template>
  <h1>Welcome to the Typing Test</h1>
  <div class="scores">
    <p>Current Key: {{ currentKey }}</p>
    <p>Wpm: {{}}</p>
    <p>Accuracy: {{}}</p>
    <p>Time: {{}}</p>
  </div>
  <keyBoard />
  <form action="" id="keyboardForm">
    <input type="text" id="keyboardInput" @keypress="keystrokeChecker" />
  </form>
</template>

<script>
import keyBoard from "../components/keyBoard.vue";
export default {
  name: "TestHome",
  components: {
    keyBoard,
  },
  data() {
    return {
      currentKey: "",
      wordsPerMinute: [],
      accuracyPercentage: [],
      remaingTime: [],
    };
  },
  methods: {
    keystrokeChecker(e) {
      this.currentKey = e.key;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#keyboardInput {
  height: 20rem;
  width: 40rem;
  caret-color: transparent;
}
</style>
