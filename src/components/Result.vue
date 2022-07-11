<script setup>
defineProps({
  tipAmount: Number,
  total: Number,
  onClick: Function,
});
</script>

<template>
  <div class="tip-amount">
    <div class="flex-inside">
      <div class="flex-box-left">
        <h3>Tip Amount</h3>
        <p>/ person</p>
      </div>
      <div class="flex-box-right">
        <h3>${{ tipAmount }}</h3>
      </div>
    </div>
    <div class="flex-inside">
      <div class="flex-box-left">
        <h3>Total</h3>
        <p>/ person</p>
      </div>
      <div class="flex-box-right">
        <h3>${{ total }}</h3>
      </div>
    </div>
    <button class="btn" @click="onClick">RESET</button>
  </div>
</template>

<style scoped>
.tip-amount {
  background-color: var(--neutral-cyan);
  font-size: 1.1rem;
  padding: 1.5rem 1.4rem 1.4rem;
  border-radius: 1rem;
  gap: 1rem;
  display: flex;
  flex-direction: column;
  color: white;
}

.flex-inside {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.flex-box-left h3 {
  font-size: 1.1rem;
}

.flex-box-left p {
  font-size: 0.9rem;
  color: var(--neutral-gray-cyan);
}

.flex-box-right h3 {
  font-size: 1.8rem;
  color: var(--primary);
  max-width: 150px;
  overflow: hidden;
  text-overflow: ellipsis;
}

.btn {
  background-color: var(--primary);
  border: none;
  margin-top: 1rem;
  border-radius: 0.5rem;
  padding: 0.8rem 1rem;
  font-size: 1rem;
  color: var(--neutral-cyan);
  font-weight: bold;
  cursor: pointer;
  transition: all 0.2s ease-in-out;
}

.btn:hover {
  opacity: 0.8;
}
</style>
