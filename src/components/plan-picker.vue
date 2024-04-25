<template>
   <div  class="plans">
      <plan-picker-item
       v-for="plan in plans"
       :name="plan"
       v-bind:key="plan"/>
    </div>
</template>

<script setup>
import {ref} from 'vue'
import planPickerItem from './plan-picker-item.vue';


defineProps({
  plans: {
    type: String,
    requiered: true,
  }
});

</script>
