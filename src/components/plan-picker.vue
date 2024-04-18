<template>
   <div class="plans">
      <plan-picker-item
       v-for="plan in plans"
       :name="plan"
       v-bind:key="plan"/>
    </div>
</template>

<script setup>
import {ref} from 'vue'
import planPickerItem from './plan-picker-item.vue';
const plans = ref([
"El soltero",
"El adicto",
"El viajero",
"El colombiano",
"El italiano"]);
</script>
