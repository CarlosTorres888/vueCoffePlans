<template>
   <div ref="plansWrapper" 
   
    class="plans">
      <plan-picker-item
      @select="printSelected"
      :selectedPlan="selectedPlan"
       v-for="plan in plans"
       :name="plan"
       v-bind:key="plan"/>
       <p style="font-size: 30px;">Counter: {{ counter }}</p>
    </div>
</template>

<script setup>
import {ref, onMounted, onUnmounted} from 'vue'
import planPickerItem from './plan-picker-item.vue';


defineProps({
  plans: {
    type: String,
    requiered: true,
  }
});

const plansWrapper = ref(null);
const selectedPlan = ref(null);

const printSelected = (playload) =>{
  selectedPlan.value = playload;
}

//Creando una referencia reactiva
//para un contador
const counter = ref(0);
//Creando un metodo para incrementar el contador
const processId = setInterval(() =>{
  console.log('Incrementando contador')
counter.value++
},1000);

//Registrando el CB (Call Back) onMounted
onMounted(()=>{
  //Obteniendo la referencia del elemento .plans
  console.log('Componente Plan Picker montado')
console.log(plansWrapper.value);
});
//Registrando el CB de onUnmounted
onUnmounted(()=>{
console.log('Componente Plan Picker desmontado')
clearInterval(processId);
});
</script>
