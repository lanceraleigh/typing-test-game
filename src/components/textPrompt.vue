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
};
</script>