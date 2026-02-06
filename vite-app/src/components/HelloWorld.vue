<script setup lang="ts">
const goToSite = () => {
  window.open('https://www.atech.com.br/', '_blank');
}
defineProps<{ msg: string }>()

</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
      <button type="button" class="btn-atech" @click="goToSite">
        Acessar nosso site
      </button>
    </div>
</template>

<style scoped>
.btn-atech {
  padding: 0.8em 1.5em;
  font-size: 1em;
  font-weight: 700;
  cursor: pointer;
  border: 1px solid transparent;
  border-radius: 8px;
  background-color: #1a1a1a; 
  color: white;
  transition: all 0.3s ease;
  box-shadow: 0 0 15px 2px #41ececaa;
}

.btn-atech:hover {
  box-shadow: 0 0 25px 5px #41ececaa;
  border-color: #41ecec;
  transform: translateY(-2px);
}

.btn-atech:active {
  transform: translateY(0);
}
</style>
