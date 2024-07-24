<script setup>
import Menu from './components/Menu.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  
<div class="main">
  <Menu />
  <router-view></router-view>
  <Footer />
</div>

</template>

<style>
body {
    height: 100vh;
    background-color: #FAD961;
    background-image: linear-gradient(90deg, #FAD961 0%, #F76B1C 100%);
    overflow: hidden;
  }

  footer {
    position: fixed;
    bottom: 0;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 56px;
  }


</style>
