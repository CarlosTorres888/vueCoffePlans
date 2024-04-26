<template>
   <div  class="plans">
      <plan-picker-item
      @select="printSelected"
      :selectedPlan="selectedPlan"
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

const selectedPlan = ref(null);

const printSelected = (playload) =>{
  selectedPlan.value = playload;
}

</script>
