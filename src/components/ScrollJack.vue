<template>
    <div>
      <div id="trigger1" class="scroll-trigger"></div>
      <section id="panel1" class="panel p1">Section 1</section>
  
      <div id="trigger2" class="scroll-trigger"></div>
      <section id="panel2" class="panel p2">Section 2</section>
  
    </div>
  </template>
  
  <script>
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";
  
  export default {
    mounted() {
      gsap.registerPlugin(ScrollTrigger);
  
      gsap.to("#panel1", {
        y: "-100%", 
        scrollTrigger: {
          trigger: "#trigger1",
          start: "top top",
          end: "+=100%",
          scrub: true,
          pin: true
        }
      });
  
      gsap.to("#panel2", {
        y: "-100%", 
        scrollTrigger: {
          trigger: "#trigger2",
          start: "top top",
          end: "+=100%",
          scrub: true,
          pin: true
        }
      });
  
      // Add as many animations as you have sections
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
    height: 100vh;
    width: 100vw;
    position: fixed;
    top: 100%;
    left: 0;
    font-family: ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,
    Liberation Mono,Courier New,monospace;
  }
  
  .p1 {
    background-color: rgb(0, 0, 0);
  }
  
  .p2 {
    background-color: rgb(255, 255, 255);
  }

  
  .scroll-trigger {
    height: 100vh;
  }
  </style>