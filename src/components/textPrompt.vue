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
    keystrokeChecker(e) {
      this.$emit("keystroke-checker", e.key);
    },
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