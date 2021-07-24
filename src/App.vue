<template>
  <div>
  <div id="app">
    <div class="main-area">
      <div class="header">
        <div>About</div>
        <div>Works</div>
        <div>Service</div>
        <div>Contact</div>
      </div>
      <div class="top-img">
        <img class="img" src="~@/assets/background.jpg">
        <div class="gray-mask">
          <div>SHIBUYA</div>
          <div>TOKYO</div>
        </div>
      </div>
      <div class="section">
        <div class="section-title">
        About This Site
        </div>
        This site was implemented to convey the image of SHIBUYA, TOKYO.<br>
        Please let me know if there is anything I should do to make the design look cooler.<br>
        There's no contact page yet, though.            
      </div>
      <div class="section">
        <div class="section-title">
          Location
        </div>
        <google-map id="map" style="margin-top: 30px;"/>  
      </div>
      <div class="section">
        <div class="section-title">
        Feature
        </div>
        Shibuya station is too crowded, right?<br>

        For more information about Shibuya-ku, click on the link below.        
        <a class ="Link" href="https://www.city.shibuya.tokyo.jp/">
        The official website of Shibuya-ku.
        </a>
      </div>
      <div class="section" style="height: 100px;">
        <div class="section-title">
        Contact
        </div>
        I'll build this section, if I get around to it...  
      </div>
      <div class=footer>©︎it's me</div>
    </div>
  </div>

  </div>
</template>

<script>
import GoogleMap from './components/GoogleMap.vue'
export default {
  name: "App",
  components: {
    "google-map" : GoogleMap
  },
  data() {
    return {
    };
  },
  methods: {
    showMap(){
        window.scrollTo({
        top: 800,
        behavior: "smooth"
      });
      
    },
    mapClick (event) {
      console.log(event);
      //$event.latLngにクリック地点が入っている
    }    
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
  background-color: rgb(0, 0, 0);
  width: 100%;
  min-height: 700px;
  min-width: 380px;  
  background-size: cover;
  margin: 0;
}
.header {
  display: flex;
  justify-content :flex-end;
  margin-right: 4px;
}
.header > div, a {
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
  cursor: pointer;

  font-style: italic;
  color: #fff;
  border: 0.2rem solid #fff;
  border-radius: .5rem;
  text-transform: uppercase;
  animation: header_flicker 1.5s infinite alternate;     

}
.header > div::-moz-selection {
  background-color: var(--neon-border-color);
  color: var(--neon-text-color);
}

.header > div::selection {
  background-color: var(--neon-border-color);
  color: var(--neon-text-color);
}

.header > div:last-child{
  background-color: rgba(255, 255, 255, 0.697);
  color: white;
}

.header > div:hover {
  background-color: rgba(255, 255, 255, 0.697);
  color: white;
}
@media screen and (min-width: 1000px) { 
  .top-img{
    position: relative;
    width: 100%;
    height: auto;
  }
  .img {
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
    opacity: .65;
    font-size: 60px;
    color: white;
  }
}
.section {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  margin-top: 70px;
  font-size: 20px;  
  color: #fff;  
}
.section-title {
  font-size: 36px;
  font-weight: bold;
  margin-bottom: 20px;
  color: #fff;
  animation: flicker 1.5s infinite alternate;
}
.footer{
  margin-top: 20px;
  color: #fff;
  font-size: 12px;  
  height: 50px;
}

:root {
  /* Base font size */
  font-size: 10px;   
  
  /* Set neon color */
  --neon-text-color: rgb(42, 90, 221);
  --neon-border-color: rgb(12, 161, 129);
}
a{
  width: 300px;
  height: 30px;
  margin-top: 30px;
}
@media screen and (max-width: 1000px) { 
  .top-img{
    position: relative;
    width: 100%;
    height: auto;
  }
  .img {
    display: block;
    width: 100%;
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
    width: 100%;
    height: 100%;
    background-color: gray;
    opacity: .65;
    font-size: 60px;
    color: white;
  }

}

/* Animate neon flicker */
@keyframes header_flicker {
    
    0%, 19%, 21%, 23%, 25%, 54%, 56%, 100% {
      
        text-shadow:
            -0.2rem -0.2rem 1rem #fff,
            0.2rem 0.2rem 1rem #fff,
            0 0 2rem var(--neon-text-color),
            0 0 4rem var(--neon-text-color),
            0 0 6rem var(--neon-text-color),
            0 0 8rem var(--neon-text-color),
            0 0 10rem var(--neon-text-color);
        
        box-shadow:
            0 0 .5rem #fff,
            inset 0 0 .5rem #fff,
            0 0 2rem var(--neon-border-color),
            inset 0 0 2rem var(--neon-border-color),
            0 0 4rem var(--neon-border-color),
            inset 0 0 4rem var(--neon-border-color);        
    }
    
    20%, 24%, 55% {        
        text-shadow: none;
        box-shadow: none;
    }    
}
@keyframes flicker {
    
  0%, 18%, 22%, 25%, 53%, 57%, 100% {

      text-shadow:
      0 0 4px #fff,
      0 0 11px #fff,
      0 0 19px #fff,
      0 0 40px #0fa,
      0 0 80px #0fa,
      0 0 90px #0fa,
      0 0 100px #0fa,
      0 0 150px #0fa;
  
  }
  
  20%, 24%, 55% {        
      text-shadow: none;
  }    
}

</style>
