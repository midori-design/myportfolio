<template>
  <div id="app">
    <div class="bg">
      <button style="margin-top:100px;" v-on:click="handleClick">Who are you?</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      msg: "I am Midori.",
      question: "Who are you?",
    };
  },
  methods: {
    handleClick() {
      alert("I'm midori!");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.bg {
  background-image: url("~@/assets/background.jpg");
  margin: 0 auto;
  width: 100%;
  min-height: 700px;
  background-size: cover;
}
</style>
