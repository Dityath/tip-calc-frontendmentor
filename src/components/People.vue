<script setup>
defineProps({
  peoples: Number,
});
</script>

<template>
  <div class="people">
    <img src="../assets/icon-person.svg" alt="" />
    <input
      type="text"
      v-model="peoples"
      @keyup.enter="onEnter"
      @keyup.backspace="onBackspace"
      placeholder="Enter people"
    />
  </div>
</template>

<style>
.people {
  padding: 10px 20px;
  margin-bottom: 20px;
  background-color: var(--neutral-light-cyan);
  border-radius: 0.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.people img {
  width: 10px;
  height: 14px;
}

.people input {
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

.people input:focus {
  outline: none;
}
</style>
