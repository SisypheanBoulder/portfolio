<template>
  <div class="card">
    <p class="body-text">{{ "Developer" }}</p>
    <h1>{{ "adrian.stack@proton.me" }}</h1>
    <button class="icon-button" @click="goToGithub">
      <img src="../assets/github-sign.png" alt="githublogo" class="logo">
    </button>
    <button class="icon-button" @click="sendEmail">
      <img src="../assets/email.png" alt="emaillogo" class="logo">
    </button>
    <button class="icon-button" @click="bookmark">
      <img src="../assets/bookmark.png" alt="bookamrklogo" class="logo">
    </button>
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
  },
  methods: {
    goToGithub() {
      window.open('https://github.com/SisypheanBoulder', '_blank');
    },
    sendEmail() {
      window.open('mailto:adrian.stack@proton.me', '_blank');
    },
    bookmark() {
      alert('Press ' + (navigator.userAgent.toLowerCase().indexOf('mac') != - 1 ? 'Cmd' : 'Ctrl') + '+D to bookmark this page :)');
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
    font-size: calc(12px + 1vw);
    font-family: ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,
    Liberation Mono,Courier New,monospace;
    text-align: left;
  }

.body-text {
  font-size: 17px; 
}
.logo {
    width: 30px;
    height: 30px;
    margin: 15px;
  }

  .icon-button {
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  margin: 0;
}

.icon-button:hover {
  opacity: 0.4;
}

  </style>

