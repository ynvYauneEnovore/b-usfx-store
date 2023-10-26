<script setup lang="ts">
import Header from "@/components/Header.vue";
import DefaultFooter from "@/components/Footer.vue";
</script>

<template>
 

  <Header />

  <div id="welcomeBody" class="welcome-body">
    <h1>Bienvenido a Mi Sitio Web</h1>
  </div>

  <DefaultFooter />
</template>

<style>

.welcome-body {
    display: flex;
  justify-content: center; 
  align-items: center; 
  height: 100vh; 
  background-color: #f0f0f0;
}

.welcome-body h1 {
  font-size: 24px;
  color: #333;
  
}

.welcome-body.show {
  opacity: 1;
  transform: translateY(0);
}

</style>


