<template>
  <div :class="{ 'nav-hidden': isNavHidden }" class="navbar" >
    <div class="dropdown">
      <button class="menu-button" v-scroll-to="'#panel1'"><img src="../assets/homeicon.png" alt="homebutton" class="logo"></button>
      <button class="menu-button" v-scroll-to="'#panel2'">About me</button>
      <button class="menu-button" v-scroll-to="'#trigger3'">Showcase</button>
    </div>
  </div>
</template>
  
  <script>
  import { ref, onMounted, onUnmounted } from 'vue';
  
  export default {
  setup() {
    const isNavHidden = ref(false);
    let lastScrollPosition = 0;

    const checkScroll = () => {
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop;
      if (currentScrollPosition < 0) {
        return;
      }
      // Shows the navbar if scrolling up, hides it if scrolling down
      isNavHidden.value = currentScrollPosition > lastScrollPosition;
      lastScrollPosition = currentScrollPosition <= 0 ? 0 : currentScrollPosition;
    };

    const checkMousePosition = (event) => {
      // Shows the navbar if the mouse is at the top 10% of the screen
      isNavHidden.value = event.clientY > window.innerHeight * 0.1;
    };

    onMounted(() => {
      window.addEventListener('scroll', checkScroll);
      window.addEventListener('mousemove', checkMousePosition);
    });

    onUnmounted(() => {
      window.removeEventListener('scroll', checkScroll);
      window.removeEventListener('mousemove', checkMousePosition);
    });

    return { isNavHidden };
  },
};
</script>

<style>
body, html {
    margin: 0;
    padding: 0;
}


  .navbar {
    position: fixed;
    top: 0;
    width: 100%;
    transition: top 2s;
    height: 10%;
    display: flex;
    align-items: center;
    background-image: url(@/assets/dropmenublk.png);
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    opacity: 0.97; 
    justify-content: center;
  }
  
  .nav-hidden {
    top: -10%;
  }

  .dropdown {
    display: flex;
    justify-content: center;
    gap: 100px;
}
  .menu-button {
    display: block;
    width: auto;
    padding: 10px;
    background-color: #00000000;
    color: #afadad;
    text-align: left;
    border: none;
    cursor: pointer;
    font-size: 1.2vw;
    font-family: ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,
    Liberation Mono,Courier New,monospace;
    transition: background-color 0.5s ease, color 0.5s ease;
    text-align: right;


}


  .menu-button:hover {
    background-color: #007bff00;
    color: #000000;
    opacity: 0.7;

  }


  .menu-button .logo {
    width: 40px; 
    height: 40px; 
  }

  </style>