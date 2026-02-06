<script setup lang="ts">
defineProps<{ msg: string }>() 

const goToSite = () => {
  window.open('https://www.atech.com.br/', '_blank');
}
</script>

<template>
  <div class="hello-container">
    <h1 class="main-title">{{ msg }}</h1>
    
    <div class="button-wrapper">
      <button type="button" class="btn-atech" @click="goToSite">
        <span class="btn-text">Acessar nosso site</span>
        <div class="btn-glow"></div>
      </button>
    </div>
  </div>
</template>

<style scoped>
.hello-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
}

.main-title {
  color: #ffffff;
  font-size: 2.5rem;
  font-weight: 700;
  letter-spacing: 2px;
  margin: 0;
  text-transform: uppercase;
  text-shadow: 0 0 20px rgba(65, 236, 236, 0.3);
}

.button-wrapper {
  margin-top: 1rem;
}

.btn-atech {
  position: relative;
  padding: 1.2rem 3rem;
  background-color: transparent;
  color: #41ecec;
  font-size: 1rem;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: 3px;
  border: 2px solid #41ecec;
  border-radius: 4px;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
}

.btn-atech:hover {
  background-color: #41ecec;
  color: #060a13;
  box-shadow: 0 0 40px rgba(65, 236, 236, 0.6);
  transform: translateY(-3px);
}

.btn-glow {
  position: absolute;
  top: 0; left: -100%; width: 100%; height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
  transition: 0.5s;
}

.btn-atech:hover .btn-glow {
  left: 100%;
}

</style>