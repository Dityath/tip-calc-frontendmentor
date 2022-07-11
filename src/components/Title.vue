<script setup>
defineProps({
  title: String,
  error: String,
});
</script>

<template>
  <div class="title">
    <h2>{{ title }}</h2>
    <p>{{ error }}</p>
  </div>
</template>

<style scoped>
.title {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.title h2 {
  color: var(--neutral-gray-cyan);
  font-size: 1.1rem;
  margin-bottom: 0.25rem;
}

.title p {
  color: red;
}
</style>
