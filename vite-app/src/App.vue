<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="main-layout">
    <div class="grid-background"></div>
    
    <div class="content-wrapper">
      <header class="logo-section">
        <a href="https://www.atech.com.br/" target="_blank">
          <img src="./assets/logo-atech.png" class="logo" alt="Atech logo" />
        </a>
      </header>

      <main class="main-section">
        <HelloWorld msg="Inovação em Defesa e Tecnologia" />
      </main>
    </div>
  </div>
</template>

<style>
* {
  cursor: url('/plane-icon.svg') 0 0, auto !important;
}

html, body, #app {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background-color: #060a13;
  font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
  overflow: hidden;
}

.main-layout {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
  background: radial-gradient(circle at center, #111d35 0%, #060a13 100%);
}

.grid-background {
  position: absolute;
  top: 0; left: 0; width: 100%; height: 100%;
  background-image: 
    linear-gradient(rgba(65, 236, 236, 0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(65, 236, 236, 0.05) 1px, transparent 1px);
  background-size: 40px 40px;
}

.content-wrapper {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
  text-align: center;
}

.logo {
  height: 120px;
  width: auto;
  filter: drop-shadow(0 0 15px rgba(65, 236, 236, 0.2));
  transition: transform 0.5s ease;
}

.logo:hover {
  transform: scale(1.15);
}
</style>