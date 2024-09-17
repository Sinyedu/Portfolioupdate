<template>
    <div class="intro-container fixed inset-0 flex flex-col items-center justify-center bg-gray-900 z-50">
      <!-- Name and Age -->
      <h1 class="text-white text-5xl font-bold opacity-0 animate-fade-in mb-6">{{ name }}</h1>
      <h2 class="text-gray-400 text-3xl opacity-0 animate-fade-in delay-1s">{{ age }} Years Old</h2>
  
      <!-- Tech Stack List -->
      <div class="tech-stack opacity-0 animate-fade-in delay-2s mt-8 flex flex-wrap justify-center space-x-4">
        <span v-for="(tech, index) in techStack" :key="index" class="text-gray-300 text-xl bg-gray-800 p-2 rounded">
          {{ tech }}
        </span>
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  
  export default defineComponent({
    name: 'mainIntro',
    setup() {
      const name = 'Simon Nyblom';
      const age = 25;
      const techStack = ['HTML', 'CSS', 'JavaScript', 'PHP', 'Typescript', 'TailwindCSS', 'Bootstrap', 'Vue/Vite', 'Wordpress'];
  
      return {
        name,
        age,
        techStack,
      };
    },
  });
  </script>
  
  <style scoped>
  @keyframes fadeIn {
    0% { opacity: 0; }
    100% { opacity: 1; }
  }
  
  /* Fade-in animation for different elements */
  .animate-fade-in {
    animation: fadeIn 2s ease-in forwards;
  }
  .delay-1s {
    animation-delay: 1s;
  }
  .delay-2s {
    animation-delay: 2s;
  }
  </style>
  