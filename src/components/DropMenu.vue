<template>
    <div :class="{ 'nav-hidden': isNavHidden }" class="navbar">
      <!-- Navbar content here -->
      <div class="dropdown">
        <button @click="toggleDropdown" class="dropbtn">Dropdown</button>
        <div v-show="showDropdown" class="dropdown-content">
          <a href="#">Link 1</a>
          <a href="#">Link 2</a>
          <a href="#">Link 3</a>
        </div>
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
    data() {
      return {
        showDropdown: false,
      };
    },
    methods: {
      toggleDropdown() {
        this.showDropdown = !this.showDropdown;
      },
    },
  };
  </script>
  
  <style>
  .navbar {
    position: fixed;
    top: 0;
    width: 100%;
    transition: top 0.3s;
  }
  
  .nav-hidden {
    top: -50px;
  }
  
  /* rest of your styles */
  </style>