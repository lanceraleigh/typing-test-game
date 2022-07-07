<template>
  <h1>Welcome to the Typing Test</h1>
  <div class="scores">
    <p>Current Key: {{ currentKey }}</p>
    <p>Wpm: {{}}</p>
    <p>Accuracy: {{}}</p>
    <p>Time: {{}}</p>
  </div>
  <keyBoard />
  <textPrompt
    @keystroke-checker="setCurrentKey"
    @text-generator="setstringArray"
    @keypress="checkAccuracy"
  />
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
      initialI: 0,
      stringArray: [],
    };
  },
  methods: {
    setCurrentKey(k) {
      this.currentKey = k;
    },
    setStringArray(arr) {
      this.stringArray = arr;
      console.log(this.stringArray);
    },
    checkAccuracy() {
      let i = this.initialI;
      if (this.stringArray[i] === this.currentKey) {
        console.log("right");
        this.initialI = this.initialI + 1;
      } else {
        console.log("wrong");
      }
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
