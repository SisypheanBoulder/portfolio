<template>
    <div id="Loading">
      <div v-if="isLoading" class="loading-screen">
        <img src="./assets/Springfieldstrippergrey.gif" alt="Logo" class="logo">
        <div class="loading-animation"></div>
      </div>
        <div id="background">
          <div class="background-video">
            <img src="./assets/bgstatic.png" alt = "bg" class="bg">
            <!-- <video autoplay muted loop>
              <source src="./assets/bluearena.mp4" type="video/mp4">
            </video> -->
          </div>
          </div>
          <div id="app">
          </div>  
          <MainCard/>
          <ParallaxEffect/>
          <DropMenu/>
          <SlideCard/>
  </div>
</template>

<script>

import MainCard from './components/MainCard.vue'
import ParallaxEffect from './components/ParallaxEffect.vue'
import DropMenu from './components/DropMenu.vue'
import SlideCard from './components/SlideCard.vue'
export default {
  data() {
      return {
        isLoading: true,
        counter: 0,
        msg: 'Welcome to Your Vue.js App',
        user: {
          firstname: 'John',
          lastname: 'Doe',
          email: 'johndoe@mail.com',
          isAdmin: true
      }
      };
    },
    mounted() {
      const delay = Math.random() * (5000) + 500;

      setTimeout(() => {
        this.isLoading = false;
      }, delay);
    },
  name: 'App',
  components: {
    MainCard,
    ParallaxEffect,
    DropMenu,
    SlideCard,
  },  
  computed: {
    fullname() {
      return `${this.user.firstname} ${this.user.lastname}`
    }
  },
  methods: {
    followUser() {
      this.counter++
    }
  }
}

</script>

<style>

.loading-screen {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(circle at center, rgb(44, 44, 44), #000 80%);
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  z-index: 9999;
}

  .logo {
    width: 500px;
    height: 200px;
  }
  
  .loading-animation {
    width: 50px;
    height: 50px;
    border: 4px solid #616161;
    border-top-color: transparent;
    border-radius: 50%;
    animation: spin 1s linear infinite;
  }
  
  @keyframes spin {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }

  .bg {
    position: fixed;
    right: 0;
    bottom: 0;
    min-width: 100%;
    min-height: 100%;
    z-index: -1;
  }

  /* .background-video {
  position: fixed;
  right: 0;
  bottom: 0;
  min-width: 100%;
  min-height: 100%;
  z-index: -1;
}

.background-video video {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: auto;
  height: auto;
  min-width: 100%;
  min-height: 100%;
} */

#app {
  padding-top: 20px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
