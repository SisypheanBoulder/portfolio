<template>
    <div class="card">
        <h2>{{ "Adrian Tran" }}</h2>
        <p>{{ "description" }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      image: {
        type: String,
        required: true
      },
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
    width: 1200px;
    height: 500px;
    padding: 20px;
    background-color: #20242dfd;
    overflow: hidden;
    color: rgb(255, 255, 255);
    box-shadow: 9px 10px 9px 0px rgba(97, 97, 97, 0.767);
    border-radius:10px;
    margin: 50px;
    border-style: solid;
    border-width: 3px;
    border-color: #CCCCCC;
  }

  
  .card-text {
    position: absolute;
    bottom: 0;
    left: 0;
    padding: 20px;
    color: white;
    background: rgba(0,0,0,0.5);
  }
  </style>