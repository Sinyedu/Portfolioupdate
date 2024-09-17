<template>
  <div class="intro-container fixed inset-0 flex flex-col items-center justify-center bg-gray-900 z-50">
    <!-- Name and Age -->
    <h1 class="text-white text-5xl font-bold opacity-0 animate-fade-in mb-6">{{ name }}</h1>
    <h2 class="text-gray-400 text-3xl opacity-0 animate-fade-in delay-1s">{{ age }} Years Old</h2>

    <!-- Tech Stack Logos -->
    <div class="tech-stack opacity-0 animate-fade-in delay-2s mt-8 flex flex-wrap justify-center space-x-4">
      <!-- Loop through the tech stack and display logos -->
      <img 
        v-for="(tech, index) in techStack" 
        :key="index" 
        :src="tech.logo" 
        :alt="tech.name" 
        class="h-12 w-auto rounded-md"
      />
    </div>
  </div>
</template>

<script lang="ts">
import htmlLogo from '@/assets/html.png';
import cssLogo from '@/assets/css.png';
import jsLogo from '@/assets/js.png';
import phpLogo from '@/assets/php.png';
import tsLogo from '@/assets/typescript.png';
import tailwindLogo from '@/assets/tailwind.png';
import bootstrapLogo from '@/assets/bootstrap.png';
import vueLogo from '@/assets/vue.png';
import wpLogo from '@/assets/wp.png';
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'mainIntro',
  setup() {
    const name = 'Simon Nyblom';
    const age = 25;

    // Add your tech stack with corresponding logo URLs
    const techStack = [
  { name: 'HTML', logo: htmlLogo },
  { name: 'CSS', logo: cssLogo },
  { name: 'JavaScript', logo: jsLogo },
  { name: 'PHP', logo: phpLogo },
  { name: 'TypeScript', logo: tsLogo },
  { name: 'TailwindCSS', logo: tailwindLogo },
  { name: 'Bootstrap', logo: bootstrapLogo },
  { name: 'Vue/Vite', logo: vueLogo },
  { name: 'Wordpress', logo: wpLogo },
];

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

.animate-fade-in {
  animation: fadeIn 2s ease-in forwards;
}

.delay-1s {
  animation-delay: 1s;
}

.delay-2s {
  animation-delay: 2s;
}

/* You can add some hover effects for logos if you want */
img:hover {
  transform: scale(1.1);
  transition: transform 0.2s;
}
</style>
