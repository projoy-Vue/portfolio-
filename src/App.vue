<template>
  <div id="app">
    <Header />
    <!-- Transition Wrapper -->
    <transition name="fade" mode="out-in">
      <RouterView />
    </transition>
    <Footer />
  </div>
</template>

<script>
import Footer from './components/Footer.vue';
import Header from './components/Header.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
  },
};
</script>

<style scoped>
/* Transition Styles */
.fade-enter-active, .fade-leave-active {
  transition: transform 0.5s ease, opacity 0.5s ease;
}
.slide-enter-from {
  transform: translateX(100%);
  opacity: 0;
}
.slide-leave-to {
  transform: translateX(-100%);
  opacity: 0;
}
</style>

