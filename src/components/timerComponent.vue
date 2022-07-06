<template>
  <div class="textPromptBox">
    <p>{{ populatedText }}</p>
  </div>
  <form action="" id="keyboardForm">
    <input type="text" id="keyboardInput" @keypress="keystrokeChecker" />
  </form>
</template>

<script>
export default {
  name: "textPrompt",
  methods: {
    setTimer() {},
    timer(time) {},
    calculateStuff() {},
  },
};
</script>

<style scoped>
#keyboardInput {
  height: 20rem;
  width: 40rem;
  caret-color: transparent;
}
</style>