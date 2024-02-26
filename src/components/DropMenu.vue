<template>
    <div :class="{ 'nav-hidden': isNavHidden }" class="navbar">
      <div class="dropdown">
        <button class="menu-button">Button 1</button>
        <button class="menu-button">Button 2</button>
        <button class="menu-button">Button 3</button>
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
  
      onMounted(() => {
        window.addEventListener('scroll', checkScroll);
      });
  
      onUnmounted(() => {
        window.removeEventListener('scroll', checkScroll);
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
    height: 10%; /* Adjust this value as needed */
    display: flex;
    align-items: center;
    background-image: url(@/assets/dropmenu.png);
    background-size: 100%;
    background-position: center;
    opacity: 0.92; /* Adjust this value as needed */
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
    color: #ebebeb;
    text-align: left;
    border: none;
    cursor: pointer;
    transition: background-color 0.3s ease;
    font-size: 20px;
    font-family: "UniSans",-apple-system,"Segoe UI","Open Sans","Helvetica Neue",sans-serif;
    font-weight: 600;
    transition: background-color 0.5s ease, color 0.5s ease;

}

.menu-button:hover {
    background-color: #007bff00;
    color: #08746e;
}
  
  </style>