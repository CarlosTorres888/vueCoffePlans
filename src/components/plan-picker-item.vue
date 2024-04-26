<template>
      <div @click="select"
    :class="{'selected-plan':isSelected}"
     class="plan">
        <div class="description">
          <span class="title">
           {{name}} Ultimo seleccionado: {{ selectedPlan}}
          </span>
        </div>
      </div>
    <div>
    </div>
</template>

<script setup>
import {computed} from 'vue';
//creando un evento
const emit = defineEmits(['select']);

const props = defineProps({
  name: {
    type: String,
    requiered: true,
  },
  selectedPlan:{
type: String
  }
});

const select = ()=>{
//detonando el evento
emit('select', props.name);
}
//creando propiedad computada
const isSelected = computed(() => {
  return props.name === props.selectedPlan;
})

</script>

<style scoped>
.selected-plan{
  background-color: #63dfd0;
}
</style>