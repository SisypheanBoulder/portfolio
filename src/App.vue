<template>
    <div id="Loading">
      <div v-if="isLoading" class="loading-screen">
        <img src="./assets/Springfieldstrippergrey.gif" alt="Logo" class="logo">
        <div class="loading-animation"></div>
      </div>
      <div id="background">
          <div class="background-video">
            <!-- <img src="./assets/bgstaticblk.png" alt = "bg" class="bg"> -->
            <video autoplay muted loop>
              <source src="./assets/Blkdsatbghq-1.mp4" type="video/mp4">
            </video> 
          </div>
          </div>
          <ScrollJack/>
          <DropMenu/>

  </div>
</template>

<script>

import DropMenu from './components/DropMenu.vue'
import ScrollJack from './components/ScrollJack.vue'

export default {
  components: {
    DropMenu,
    ScrollJack,
  },  
  data() {
    return {
      isLoading: true, // Add this line
    }
  },
    mounted() {
      const delay = Math.random() * (5000) + 500;

      setTimeout(() => {
        this.isLoading = false;
      }, delay);
    },

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

   .background-video {
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
} 

</style>
