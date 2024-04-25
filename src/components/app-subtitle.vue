<template> 
    <div class="content2">
        <h2 class="subtitle">
     {{subtitle}}
    </h2>
    </div>
</template>

<script setup>
defineProps({
  subtitle: {
    type: String,
    requiered: true,
  }
});
</script>
