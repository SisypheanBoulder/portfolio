<template>
    <Carousel :items-to-show="2.5" :wrap-around="true">
      <Slide v-for="slide in images" :key="slide">
        <div class="carousel__item">
          <img :src="slide" alt="Slide image">
        </div>
      </Slide>
  
      <template #addons>
        <Navigation />
      </template>
    </Carousel>
  </template>
  
  <script>
  import { defineComponent } from 'vue';
  import { Carousel, Navigation, Slide } from 'vue3-carousel';
  
  import 'vue3-carousel/dist/carousel.css';
  
  // Import images
  import image1 from '../assets/pomodoro.png';
  import image2 from '../assets/whitebaord.png';
  import image3 from '../assets/targetrifleclub.png';
  import image4 from '../assets/gd.png';
  
  export default defineComponent({
    name: 'WrapAround',
    components: {
      Carousel,
      Slide,
      Navigation,
    },
    data() {
      return {
        images: [
          image1,
          image2,
          image3,
          image4,
        ]
      }
    }
  })
  </script>
  
  
  <style scoped>
  .carousel__item {
    
    margin-top: 50px;
    height: 50vh; 

  }
  
  .carousel__item img {
    height: 50vh;  /* 50% of the viewport's height */
    object-fit: cover;
  }
  </style>
  
  <style scoped>
  .carousel__item {
    
    margin-top: 50px;
    height: 50vh; 

  }
  
  .carousel__item img {
    height: 50vh;  /* 50% of the viewport's height */
    object-fit: cover;
  }
  </style>