<template>
  <div class="wrapper">
    <button @click="start">Start</button>
    <button @click="stop">Stop</button>
    <br />
    <div class="disco-box"></div>
    <div class="disco-box"></div>
    <div class="disco-box"></div>
    <div class="disco-box"></div>
    <div class="disco-box"></div>
    <div class="disco-box"></div>
    <div class="disco-box"></div>
    <div class="disco-box"></div>
    <div class="disco-box"></div>
    <div class="disco-box"></div>
    <div class="disco-box"></div>
    <div class="disco-box"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      timer: 500,
      intervalId: null,
    };
  },
  methods: {
    start() {
      this.intervalId = setInterval(this.changeColor, this.timer);
    },
    stop() {
      clearInterval(this.intervalId);
    },
    generateRandomColor() {
      return "#" + Math.floor(Math.random() * 16777215).toString(16);
    },
    changeColor() {
      var discoBoxes = document.getElementsByClassName("disco-box");
      [...discoBoxes].forEach(
        (box) => (box.style.backgroundColor = this.generateRandomColor())
      );
    },
  },
};
</script>

<style scoped>
.wrapper {
  border-radius: 10px;
  background: #f4f7f8;
  border: 2px solid #ccc;
  padding: 10px;
  margin: 15px;
  width: 450px;
  height: 100%;
}

.disco-box {
  background-color: rgb(243, 232, 198);
}

div {
  display: inline-block;
  box-sizing: border-box;
  margin: 1vh;
  width: 10vw;
  height: 10vh;
  background-color: #fff;
}
</style>