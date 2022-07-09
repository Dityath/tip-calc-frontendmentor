<script setup>
defineProps({
  title: String,
});
</script>

<template>
  <h2>{{ title }}</h2>
</template>

<style scoped>
h2 {
  color: var(--neutral-gray-cyan);
  font-size: 1.1rem;
  margin-bottom: 0.25rem;
}
</style>
