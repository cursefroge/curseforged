<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';

const greetings = ['Hello', 'Hola', 'Bonjour', 'Hallo', 'Ciao', 'Olá', 'こんにちは', '你好', 'Zdravo', 'Hej', 'Ahoj', 'Γεια', 'שלום', 'Merhaba', 'Привет', 'नमस्ते', '안녕하세요', 'Sawubona', 'Jambo', 'Hei', 'Salut', 'Cześć', 'สวัสดี', 'Xin chào', 'Salam'];
let index = 0;
const msg = ref(greetings[index]);

const names = ['cursefroge', 'カースフロッジ']
const name = ref(names[0]);

onMounted(() => {
  setInterval(() => {
    index = (index + 1) % greetings.length;
    msg.value = greetings[index];
  }, 3000);
});

function toggleName() {
  name.value = name.value === names[0] ? names[1] : names[0];
}


onUnmounted(() => {
  clearInterval(index);
});
</script>

<template>
  <div class="greetings">
    <h1 :key="name" @click="toggleName()">{{ name }}</h1>
    <transition name="slide-fade" mode="out-in">
      <h3 :key="msg">{{ msg }}</h3>
    </transition>
  </div>
</template>

<style scoped>
.slide-fade-enter-active, .slide-fade-leave-active {
  transition: all 1s;
}

.slide-fade-enter-from {
  opacity: 0;
  transform: translateY(10px);
}

.slide-fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}

.slide-fade-enter-to, .slide-fade-leave-from {
  opacity: 1;
  transform: translateY(0);
}
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
  font-weight: 700;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
