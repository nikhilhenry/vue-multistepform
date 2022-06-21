<template>
  <div class="flex flex-col items-center justify-center h-screen">
    <MultiStepForm
      :forms="forms"
      :steps="['Personal information 👶', 'Series 📺', 'Feedback 🌟']"
      :submit-action="submitAction"
    />
  </div>
</template>

<script lang="ts" setup>
import MultiStepForm from "./components/MultiStepForm.vue";
import Step1 from "./components/Step1.vue";
import Step2 from "./components/Step2.vue";
import Step3 from "./components/Step3.vue";

const forms = [Step1, Step2, Step3];
const submitAction = () => {
  console.log("submitting form...");
};
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
