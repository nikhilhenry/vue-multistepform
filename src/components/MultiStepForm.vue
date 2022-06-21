<template>
    <div>
        <ul class="steps">
            <li class="step step-primary">Register</li>
            <li class="step step-primary">Choose plan</li>
            <li class="step">Purchase</li>
            <li class="step">Receive Product</li>
        </ul>
       <div class="py-5"></div> 
        <form @submit.prevent> 
            <component
                :is="forms[step]"
            >
            </component>
            <div class="flex justify-end">
                <button class="btn btn-ghost" @click="step--">Back</button>
                <button class="btn btn-primary" @click="step++">Next</button>
            </div>
        </form>
    </div>
</template>

<script lang="ts" setup>
import {ref} from "vue"

let step = ref(0);
const props = defineProps<{
    forms:[string]
}>()

</script>
