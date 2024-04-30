<script setup>
import planPicker from './components/plan-picker.vue';
import appTitle from './components/app-title.vue';
import appSubtitle from './components/app-subtitle.vue';
import {ref} from 'vue';
const showPlans = ref(true);
</script>

<template>
  <header>
    <div>
      <span id="logo">Liquid Gold Box</span>
      <img src="./assets/logo.png" alt="logo">
    </div>
  </header>

  <div class="content">
    <app-title title="Vacaciones"/>
    <app-subtitle subtitle="Viajamos por el mundo para encontrar el mejor café de origen único para ti"/>
    <label>
      <input type="checkbox" v-model="showPlans">
      Mostrar Selector de Planes
    </label>
    <plan-picker :plans="['el soltero','El colombiano','Extra']" v-if="showPlans"/>
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
