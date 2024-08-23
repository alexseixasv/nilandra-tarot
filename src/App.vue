<template>
  <div class="w-full font-sans text-gray-900">
    <Header />
    <Homepage />
    <Footer />
    <Cookies />
    <a href="https://wa.me/5511937007820" class="whatsapp-button" target="_blank">
        <img src="https://www.imagemhost.com.br/images/2024/02/29/whatsapp-white-icon.png" alt="WhatsApp" class="p-1">
    </a>
  </div>
</template>

<style>
        .whatsapp-button {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: #25D366;
            border-radius: 50%;
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
            z-index: 1000;
            text-decoration: none;
        }

        .whatsapp-button img {
            width: 40px;
            height: 40px;
        }

        .whatsapp-button:hover {
            background-color: #128C7E;
        }
</style>

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
