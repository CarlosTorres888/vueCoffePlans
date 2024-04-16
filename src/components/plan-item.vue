<template>
      <div class="plan">
        <div class="description">
          <span class="title">
           {{name}}👍 Likes: {{ likes }}
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
  },
  likes: {
    type: Number,
    default: 0,
  }
});
</script>
<style>

</style>