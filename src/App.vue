<template>
  <div class="w-full font-sans text-gray-900">
    <Header />
    <Homepage />
    <Footer />
    <Cookies />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Homepage from './components/Homepage.vue';
import Footer from './components/Footer.vue';
import Cookies from './components/cookiesBanner.vue';

export default {
  name: 'App',
  components: {
    Header,
    Homepage,
    Footer,
    Cookies
  },
};
</script>
