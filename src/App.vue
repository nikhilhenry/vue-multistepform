<template>
  <div class="flex flex-col items-center justify-center h-screen">
    <MultiStepForm :forms="['hi','hello']"/>
  </div>
</template>

<script lang="ts" setup>
 import MultiStepForm from "./components/MultiStepForm.vue" 
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
body {
    @apply bg-slate-800 text-white;
  }
</style>
