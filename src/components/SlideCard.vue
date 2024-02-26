<template>
    <div class="container">
      <div ref="animatedElement" class="slide-in-fade-in">
        <img src="https://randomuser.me/api/portraits/lego/3.jpg" alt="Your Image">
        <p>Your Text</p>
      </div>
    </div>
  </template>
  
  <script>
  import { ref, onMounted, onUnmounted } from 'vue';
  
  export default {
    setup() {
      const animatedElement = ref(null);
      let observer = null;
  
      onMounted(() => {
        observer = new IntersectionObserver((entries) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              entry.target.classList.add('animate');
            } else {
              entry.target.classList.remove('animate');
            }
          });
        });
  
        if (animatedElement.value) {
          observer.observe(animatedElement.value);
        }
      });
  
      onUnmounted(() => {
        if (observer && animatedElement.value) {
          observer.unobserve(animatedElement.value);
        }
      });
  
      return { animatedElement };
    },
  };
  </script>
  
  <style>
  .slide-in-fade-in {
    opacity: 0;
    transform: translateX(-50px);
    transition: opacity 2s, transform 2s;
    
  }
  
  .slide-in-fade-in.animate {
    opacity: 1;
    transform: translateX(0);
  }
  </style>