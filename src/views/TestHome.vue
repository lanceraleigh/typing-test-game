<template>
  <h1>Welcome to the Typing Test</h1>
  <div class="scores">
    <p>Current Key: {{ currentKey }}</p>
    <p>Wpm: {{}}</p>
    <p>Accuracy: {{}}</p>
    <p>Time: {{}}</p>
  </div>
  <keyBoard />
  <textPrompt @keystroke-checker="setCurrentKey" />
</template>

<script>
import keyBoard from "../components/keyBoard.vue";
import textPrompt from "../components/textPrompt.vue";
export default {
  name: "TestHome",
  components: {
    keyBoard,
    textPrompt,
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
    setCurrentKey(k) {
      this.currentKey = k;
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
