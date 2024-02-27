<template>
    <div>
      <div id="trigger1" class="scroll-trigger"></div>
      <section id="panel1" class="panel p1">
        <MainCard />
      </section>
  
      <div id="trigger2" class="scroll-trigger"></div>
      <section id="panel2" class="panel p2">Section 2
        <AboutMe />
      </section>
      
      <div id="trigger3" class="scroll-trigger"></div>
      <section id="panel3" class="panel p3">Section 3</section>
  
    </div>
  </template>
  
  <script>
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";
  import MainCard from './MainCard.vue';
  import AboutMe from './AboutMe.vue';

  export default {
  components: {
    MainCard,
    AboutMe,
  },
  mounted() {
  gsap.registerPlugin(ScrollTrigger);

  gsap.to("#panel2", {
    y: "-100%", 
    scrollTrigger: {
      trigger: "#trigger2",
      start: "top bottom",
      end: "+=90%", // Change this line
      scrub: 1.5,
      pin: true
    }
  });

  gsap.to("#panel3", {
    y: "-100%", 
    scrollTrigger: {
      trigger: "#trigger3",
      start: "top bottom",
      end: "+=80%",
      scrub: 1.5,
      pin: true
    }
  });
}
}
  </script>
  
  <style scoped>
  
  body {
    margin: 0;
    padding: 0;
    overflow: hidden;
  }
  
  .panel {
    height: 100%;
    width: 100vw;
    position: fixed;
    top: 100%;
    left: 0;
    font-family: ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,
    Liberation Mono,Courier New,monospace;
  }
  
  .p1 {
    top: 0;
    background-color: rgba(0, 0, 0, 0.322);
  }
  
  .p2 {
    color: rgb(255, 255, 255);
    background-color: rgb(0, 0, 0);
  }


  .p3 {
    background-color: rgb(255, 255, 255);
  }  
  .scroll-trigger {
    height: 100vh;
  }
  </style>