<script setup>
defineProps({
  screen: Number,
});
</script>

<template>
  <div class="screen">
    <img src="../assets/icon-dollar.svg" alt="" />
    <input
      type="text"
      v-model="screen"
      @keyup.enter="onEnter"
      @keyup.backspace="onBackspace"
      placeholder="Enter amount"
    />
  </div>
</template>

<style>
.screen {
  padding: 10px 20px;
  background-color: var(--neutral-light-cyan);
  border-radius: 0.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.screen img {
  width: 10px;
  height: 16px;
}

.screen input {
  margin: 0;
  padding: 0;
  font-size: 1.2rem;
  font-weight: bold;
  width: 100%;
  text-align: right;
  border: none;
  background-color: transparent;
  font-family: var(--font);
  color: var(--neutral-cyan);
}

.screen input:focus {
  outline: none;
}
</style>
