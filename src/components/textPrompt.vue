<template>
  <div class="textPromptBox">
    <p>{{ populatedText }}</p>
  </div>
  <form action="" id="keyboardForm">
    <input
      type="text"
      id="keyboardInput"
      @keypress="
        keystrokeChecker;
        randomLoremArray;
      "
    />
  </form>
</template>

<script>
export default {
  name: "textPrompt",
  data() {
    return {
      loremIpsum: `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec varius mollis ornare. Curabitur enim erat, iaculis sed tristique in, volutpat a urna. Phasellus tempus vulputate quam a ultricies. Proin lobortis sit amet est at blandit. Pellentesque rutrum congue elit hendrerit consectetur. Morbi in ante enim. Donec varius dapibus neque, nec blandit sem commodo eu. Morbi consequat mollis enim. Morbi risus felis, pulvinar id magna sit amet, cursus tempor nunc. Morbi pellentesque magna sit amet molestie facilisis. Etiam in mollis neque. Etiam faucibus augue orci, id sodales enim pulvinar eget. Sed placerat aliquam risus vitae porttitor. Proin quis odio mollis, commodo dolor eu, faucibus erat. Phasellus suscipit id magna a venenatis. Sed rhoncus sem eget convallis convallis. Quisque elit erat, viverra quis finibus non, sollicitudin in quam. Mauris non tellus sit amet justo molestie rutrum in rhoncus nisl. Praesent feugiat vel nisl et hendrerit. Integer et ex nulla. Mauris rhoncus sed quam ut vulputate. Nullam faucibus convallis pulvinar. Ut congue velit at ex aliquet porttitor. Quisque massa urna, facilisis aliquam magna in, lobortis tempus est. Etiam sodales, odio in lacinia efficitur, neque turpis aliquet lacus, sit amet vestibulum nulla elit id massa. Fusce lobortis justo eu viverra gravida. Proin et felis semper quam aliquet feugiat at ut felis. Cras urna risus, semper eu tristique ut, faucibus sed elit. Suspendisse potenti. Donec mollis sapien vitae justo faucibus sodales. Sed tempor tristique leo in imperdiet. Donec ut risus euismod, auctor nibh nec, facilisis felis. Pellentesque egestas augue non risus porta, quis tempor diam iaculis. Suspendisse ullamcorper nisl sed eros imperdiet ultricies. Aenean vitae pulvinar eros. Ut leo augue, elementum eget purus et, volutpat tincidunt magna. Nullam id metus molestie, bibendum purus vel, convallis turpis. Maecenas egestas tincidunt ante, eget tempus nisi commodo vitae. Quisque imperdiet volutpat metus a pellentesque. Nunc gravida convallis dolor, sed laoreet dolor eleifend pellentesque. Integer id suscipit mauris. Nulla nec sollicitudin magna, ac dictum tellus. Nulla facilisi. Curabitur id ullamcorper urna. Pellentesque ornare tellus eget fermentum sodales. In hac habitasse platea dictumst. Nam sit amet velit venenatis, blandit nibh scelerisque, consequat risus. Maecenas lobortis felis sit amet purus cursus consequat. Nunc aliquam mauris tellus, ac fringilla leo posuere in. Maecenas in fringilla massa. In blandit nisi nulla, at ullamcorper lacus tristique ut. Nullam congue sem sodales turpis sodales sollicitudin.`,
      populatedText: "",
      populatedTextArray: [],
    };
  },
  methods: {
    randomLorem() {
      let loremIpsumArray = this.loremIpsum.split(" ");
      for (let i = 0; i < loremIpsumArray.length; i++) {
        this.populatedText =
          this.populatedText +
          ` ${
            loremIpsumArray[Math.floor(Math.random() * loremIpsumArray.length)]
          }`;
      }
      this.randomLoremArray(this.populatedText);
    },
    randomLoremArray(str) {
      this.populatedTextArray = str.split("");
      this.$emit("text-generator", str.split(""));
    },
    keystrokeChecker(e) {
      this.$emit("keystroke-checker", e.key);
    },
  },
  mounted() {
    this.randomLorem();
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