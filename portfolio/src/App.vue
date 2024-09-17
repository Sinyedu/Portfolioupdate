<template>
  <div id="app">
    <!-- Intro will stay on screen -->
    <Intro />

    <!-- portfolio content starts here -->
    <div class="portfolio-content mt-16 p-8 bg-white">
      <router-view />
    </div>
  </div>
</template>

<script lang="ts">
import { ref } from 'vue';
import { defineComponent } from 'vue';
import Intro from './components/Intro.vue';

export default defineComponent({
  components: {
    Intro,
  },
});
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
.portfolio-content {
  padding-top: 5rem;
}
</style>
