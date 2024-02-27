<template>
    <div class="card">
        <h1>{{ "Works in progress" }}</h1>
        <p class="body-text">{{ "The first experience I had with web design was a Pomodoro webapp that would "+ 
        "that was designed to help myself effectively study" }}</p>
        <p class="body-text">{{ "Whiteboard was a group capstone university project that was based off Moodle but had "+ 
        "more features and was easier to use" }}</p>
        <p class="body-text">{{ "I dedicate my time to running the UNSW Target Rifle CLub which has developed my team "+ 
        "building and coaching ability" }}</p>
        <p class="body-text">{{ "In my spare time I try try to dabble in the arts and am proud to say that I commissioned to do artwork "+
        "for an NFT project that unfortunately went no where" }}</p>
        <p class="body-text">{{ "And of course this very website, I hope to improve it as I improve and grow as a developer"}}</p>




    </div>
  </template>
  
  <script>

  export default {
    props: {
      title: {
        type: String,
        required: true
      },
      description: {
        type: String,
        required: true
      }
    }
  }
  </script>
  
  <style scoped>
  .card {
    position: relative;
    width: 85%;
    height: 27%;
    padding: 10px;
    background-color: #0f0f0f80;
    overflow: hidden;
    color: rgb(255, 255, 255);
    box-shadow: 0px 0px 20px 10px rgba(26, 25, 25, 0.555);
    border-radius:10px;
    margin: 5%;
    font-size: calc(8px + 0.7vw);
    font-family: ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,
    Liberation Mono,Courier New,monospace;
    text-align: left;
  }

.body-text {
  font-size: calc(0.7rem + 0.3vw); 
}

  </style>

