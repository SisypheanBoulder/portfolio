<template>
    <div class="card">
        <h1>{{ "About ME" }}</h1>
        <p class="body-text">{{ "Hello! I am Adrian, a fresh graduate with a keen interest in "+ 
        "computer science across all aspects of the field. I am currently going to be doing " + 
        "freelance website projects with Vue, as it is a user friendly and responsive approach "+
        "to web design, I also immerse myself in game design and digital art when I have the " + 
        "time. "}}</p>
        <p class="body-text">{{ "Throughout my time in university I was involved in dozens of "+ 
        "group projects and tasks, where I came to the understanding that valuing teamwork " + 
        "and communication is keystone in any project, and a value I try to exemplify through "+
        "my work and extra curricular activities and responsibilities"}} </p>


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
    width: 65%;
    height: 45%;
    padding: 20px;
    background-color: #0f0f0f80;
    overflow: hidden;
    color: rgb(255, 255, 255);
    box-shadow: 0px 0px 20px 10px rgba(94, 94, 94, 0.555);
    border-radius:10px;
    margin: 10%;
    margin-top: 10%;
    font-size: calc(12px + 1vw);
    font-family: ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,
    Liberation Mono,Courier New,monospace;
    text-align: left;
  }

.body-text {
  font-size: calc(0.8rem + 0.3vw); 
}
.logo {
    width: 30px;
    height: 30px;
    margin: 15px;
  }

  </style>

