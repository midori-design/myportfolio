<template>
  <div id="app">
    <div class="main-area">
      <div class="header">
        <div>About</div>
        <div>Works</div>
        <div>Service</div>      
        <div>Contact</div>
      </div>
      <div class=top-img>
        <img src="~@/assets/background.jpg">
        <div class="gray-mask">
          <div>SHIBUYA</div>
          <div>TOKYO</div>
          <button>Watch Goggle Map</button>
        </div>
      </div>
      <div class="about">
      About This Site
      </div>
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
}
.main-area {
  background-color: rgb(255, 255, 255);
  width: 100%;
  min-height: 700px;
  background-size: cover;
  margin: 0;
}
.header {
  display: flex;
  justify-content :flex-end;
  margin-right: 4px;
}
.header > div {
  display: flex;
  width: 100px;
  height: 30px;
  margin: 8px 4px;
  font-size: 14px;
  font-weight: bold;
  line-height: 16px;
  justify-content: center;
  align-items: center;
  color: black;
}
.header > div:last-child{
  background-color: rgba(23, 76, 83, 0.697);
  color: white;
}
.top-img{
  position: relative;
  width: 100%;
  height: auto;
}
img {
  display: block;
  width: 100%;
  min-width: 1000px;
  margin: 0;
}
.top-img .gray-mask {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: absolute;
  z-index: 1000;
  top: 0px;
  left: 0px;
  width: 38%;
  min-width: 380px;
  height: 100%;
  background-color: gray;
  opacity: .75;
  font-size: 60px;
  font-weight: bold;
  color: white;
}
.about {
  display: block;
  width: 350px;
  font-size: 36px;
  font-weight: bold;
  margin-top: 50px;
  margin-left: 50px;
}
button {
  margin-top: 40px;
  width: 250px;
  height:40px;
  font-size: 20px;
  color: black;
  background-color: rgb(158, 218, 227);
  border-radius: 30px;
  font-weight: bold;
}
</style>
