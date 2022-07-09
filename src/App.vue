<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import Screen from "./components/Screen.vue";
import Title from "./components/Title.vue";
</script>

<template>
  <header class="header-main">
    <img src="./assets/logo.svg" alt="" />
  </header>
  <main>
    <Title title="Bill" />
    <Screen />
  </main>
</template>

<style>
:root {
  --primary: hsl(172, 67%, 45%);
  --neutral-cyan: hsl(183, 100%, 15%);
  --neutral-dark-gray-cyan: hsl(186, 14%, 43%);
  --neutral-gray-cyan: hsl(184, 14%, 56%);
  --neutral-light-gray-cyan: hsl(185, 41%, 84%);
  --neutral-light-cyan: hsl(189, 41%, 97%);

  --font: "Space Mono", monospace;
}

* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

body {
  font-family: var(--font);
  background-color: var(--neutral-light-gray-cyan);
  margin: 0;
  padding: 0;
}

#app {
  margin: 0;
  padding: 0;
}

.header-main {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem 0;
}

main {
  padding: 2rem;
  background-color: white;
  border-radius: 1.5rem 1.5rem 0 0;
}
</style>
