<template>
  <h3>Time left: {{ setTime }} seconds</h3>
  <button @click="setTimer(-30)" class="red">-30 sec</button>
  <button @click="setTimer(30)" class="green">+30 sec</button>
  <button @click="timer" class="blue">Start</button>
  <button @click="timer(true)" class="red">Stop</button>
</template>

<script>
export default {
  name: "textPrompt",
  data() {
    return {
      setTime: 120,
      timeInput: 120,
    };
  },
  methods: {
    setTimer(adjustment) {
      this.setTime += adjustment;
    },
    timer(n) {
      let time = setInterval(() => {
        this.setTime--;
      }, 1000);
      if (n) {
        clearInterval(time);
      }
    },
    calculateStuff() {},
  },
};
</script>

<style scoped>
.red {
  background: rgb(255, 144, 144);
}
.green {
  background: rgb(144, 255, 144);
}
.blue {
  background: rgb(144, 144, 255);
}
</style>