<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import JobBoardComponent from './components/JobBoardComponent.vue'
import Header from './components/Header.vue'
</script>

<template>
  <div class="">
  <Header />
    <JobBoardComponent />
  </div>
  
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: hsl(180, 52%, 96%);

}
</style>
