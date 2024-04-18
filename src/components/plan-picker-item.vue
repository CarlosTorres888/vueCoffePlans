<template>
      <div class="plan">
        <div class="description">
          <span class="title">
           {{name}}
          </span>
        </div>
      </div>
    <div>
    </div>
</template>

<script setup>
defineProps({
  name: {
    type: String,
    requiered: true,
  }
});
</script>
<style>

</style>