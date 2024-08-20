<template>
  <RouterView />
</template>

<script setup>
import { RouterView } from 'vue-router';
import Lenis from '@studio-freight/lenis';
import { onMounted } from 'vue';

function scrollAnimation() {
  const lenis = new Lenis({
    duration: 1,
    easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
    direction: "vertical",
    gestureDirection: "vertical",
    smooth: true,
  });

  function raf(time) {
    lenis.raf(time);
    requestAnimationFrame(raf);
  }

  requestAnimationFrame(raf);

  lenis.on("scroll", (e) => {
    console.log(e);
  });
}

onMounted(() => {
  scrollAnimation();
});

</script>
