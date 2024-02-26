<template>
  <div>
    <img
      v-for="(img, index) in images"
      :key="index"
      :style="{ transform: `translate(${img.x + img.initialX}px, ${img.y + img.initialY}px)` }"
      :src="img.src"
    />
  </div>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue';

export default {
  setup() {
    const images = ref([
      { src: 'https://randomuser.me/api/portraits/lego/0.jpg', x: 0, y: 0, initialX: 100, initialY: 100 },
      { src: 'https://randomuser.me/api/portraits/lego/2.jpg', x: 0, y: 0, initialX: 200, initialY: 200 },
      // add more images as needed
    ]);

    const handleMouseMove = (event) => {
      const { clientX, clientY } = event;
      images.value = images.value.map((img, index) => {
        const factor = (index + 1) * 0.01; // adjust this to change the speed of the movement
        return {
          ...img,
          x: (clientX - window.innerWidth / 2) * factor,
          y: (clientY - window.innerHeight / 2) * factor,
        };
      });
    };

// stops the event listener when the component is unmounted to prevent memory leaks
    onMounted(() => {
      window.addEventListener('mousemove', handleMouseMove);
    });

    onUnmounted(() => {
      window.removeEventListener('mousemove', handleMouseMove);
    });

    return { images };
  },
};
</script>

