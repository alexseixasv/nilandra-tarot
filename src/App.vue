<template>
  <div class="w-full font-sans text-gray-900">
    <Header />
    <HeroSection />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import HeroSection from './components/HeroSection.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    HeroSection,
    Footer,
  },
};
</script>
