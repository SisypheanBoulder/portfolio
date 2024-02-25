<template>
  <div id="app">
    {{ user.email }} = {{ fullname }}
    <strong>likes: </strong> {{ counter }}
    <button @click="followUser">like</button>
    </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      counter: 0,
      msg: 'Welcome to Your Vue.js App',
      user: {
        firstname: 'John',
        lastname: 'Doe',
        email: 'johndoe@mail.com',
        isAdmin: true
      }
    }
  },
  computed: {
    fullname() {
      return `${this.user.firstname} ${this.user.lastname}`
    }
  },
  methods: {
    followUser() {
      this.counter++
    }
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
