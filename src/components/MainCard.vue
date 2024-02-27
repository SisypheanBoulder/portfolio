<template>
    <div class="card">
        <p>{{ "Developer" }}</p>
        <h1>{{ "Adrian.Stack" }}</h1>
        <img src="../assets/github-sign.png" alt="githublogo" class="logo">
        <img src="../assets/email.png" alt="emaillogo" class="logo">
        <img src="../assets/bookmark.png" alt="bookamrklogo" class="logo">


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
    width: 600px;
    height: 250px;
    padding: 20px;
    background-color: #00000080;
    overflow: hidden;
    color: rgb(255, 255, 255);
    box-shadow: 9px 10px 9px 0px rgba(94, 94, 94, 0.555);
    border-radius:10px;
    margin: 50px;
    margin-top: 250px;
    font-size: 30px;
    font-family: ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,
    Liberation Mono,Courier New,monospace;
    text-align: left;
  }

  .header {
  font-size: 50px; 
  font-weight: 600;
}

.body-text {
  font-size: 10px; 
}
.logo {
    width: 30px;
    height: 30px;
    margin: 15px;
  }

  </style>

