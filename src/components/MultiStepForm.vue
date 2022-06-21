<template>
    <div>
        <ul class="steps">
            <li v-for="(stepText,index) in props.steps" class="step" :class="index==step ? 'step-primary' : ''">
                {{stepText}}
            </li>
        </ul>
       <div class="py-3"></div> 
        <form @submit.prevent="formAction"> 
            <component
                :is="props.forms[step]"
            >
            </component>
       <div class="py-4"></div> 
            <div class="flex justify-end">
                <button class="btn btn-ghost" v-if="step!==0" @click="step--">Back</button>
                <button class="btn btn-primary" type="submit" v-if="step!=props.steps.length-1">Next</button>
            </div>
        </form>
    </div>
</template>

<script lang="ts" setup>
import {ref} from "vue"
import Step1 from "./Step1.vue"

let step = ref(0);
const props = defineProps<{
    forms:typeof Step1[]
    steps:string[]
}>()

const formAction = () => {
        if(step.value !== props.steps.length-1) step.value++
}
</script>
