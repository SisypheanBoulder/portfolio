<template>
    <div class="popup-container" @mouseover="isPopupHidden = false" @mouseleave="isPopupHidden = true">
      <div :class="{ 'popup-hidden': isPopupHidden }" class="popup">
        <!-- Your popup content here -->
      </div>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    setup() {
      const isPopupHidden = ref(true);
  
      return { isPopupHidden };
    },
  };
  </script>
  
  <style>
  .popup-container {
    position: fixed;
    bottom: 0;
    width: 100%;
    height: 10%;
  }
  
  .navbar {
    position: fixed;
    top: 0;
    width: 100%;
    transition: top 2s;
    height: 10%;
    display: flex;
    align-items: center;
    background-image: url(@/assets/dropmenublk.png);
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    opacity: 0.97; 
    justify-content: center;
  }
  
  .popup-hidden {
    bottom: -100%;
  }
  
  </style>