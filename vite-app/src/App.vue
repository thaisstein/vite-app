<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="main-layout">
    <div class="content-wrapper">
      <a href="https://www.atech.com.br/" target="_blank">
        <img src="./assets/logo-atech.png" class="logo" alt="Atech logo" />
      </a>
      <HelloWorld msg="Bem-vindo à Atech" />
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
  overflow: hidden;
}

.main-layout {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
  background-color: #ffffff;
}

.content-wrapper {
  text-align: center;
}

.logo {
  height: 8em;
  padding: 1.5em;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #41ececaa);
}
</style>