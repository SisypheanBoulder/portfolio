<template>
    <div id="Loading">
      <div v-if="isLoading" class="loading-screen">
        <img src="./assets/Springfieldstripperclip.gif" alt="Logo" class="logo">
        <div class="loading-animation"></div>
      </div>
        <div id="app">
          {{ user.email }} = {{ fullname }}
          <strong>likes: </strong> {{ counter }}
          <button @click="followUser">like</button>
          </div>
          <MainCard/>
          <ParallaxEffect/>
          <DropMenu/>
  </div>
</template>

<script>

import MainCard from './components/MainCard.vue'
import ParallaxEffect from './components/ParallaxEffect.vue'
import DropMenu from './components/DropMenu.vue'

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
    DropMenu
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
    background: #000000;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    z-index: 9999; /* Add this line */
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

  .section {
  height: 500px;
  overflow: auto;
}
  
  @keyframes spin {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
