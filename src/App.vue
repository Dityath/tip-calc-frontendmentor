<script setup>
import Title from "./components/Title.vue";
import Result from "./components/Result.vue";
import { ref } from "vue";

const bill = ref(0);
const tip = ref(5);
const customTip = ref(null);
const people = ref(1);

const reset = () => {
  bill.value = 0;
  tip.value = 5;
  people.value = 1;
};
</script>

<template>
  <header class="header-main">
    <img src="./assets/logo.svg" alt="" />
  </header>
  <div class="all">
    <main>
      <div class="flex">
        <div class="flex-left">
          <Title title="Bill" />
          <div class="screen">
            <img src="./assets/icon-dollar.svg" alt="" />
            <input v-model="bill" placeholder="Enter amount" />
          </div>
          <Title title="Select Tip %" error="" />
          <div class="select-tip">
            <button
              @click="
                tip = 5;
                customTip = null;
              "
              :class="{ active: tip === 5 }"
            >
              5%
            </button>
            <button
              @click="
                tip = 10;
                customTip = null;
              "
              :class="{ active: tip === 10 }"
            >
              10%
            </button>
            <button
              @click="
                tip = 15;
                customTip = null;
              "
              :class="{ active: tip === 15 }"
            >
              15%
            </button>
            <button
              @click="
                tip = 25;
                customTip = null;
              "
              :class="{ active: tip === 25 }"
            >
              25%
            </button>
            <button
              @click="
                tip = 50;
                customTip = null;
              "
              :class="{ active: tip === 50 }"
            >
              50%
            </button>
            <input
              type="text"
              :value="customTip"
              @input="
                (event) => {
                  customTip = event.target.value;
                  tip = customTip;
                }
              "
              placeholder="Custom"
            />
          </div>
          <Title
            title="Number of People"
            :error="people == 0 ? `Can't be zero` : ''"
          />
          <div :class="{ screen: true, error: people == 0 || people == NaN }">
            <img src="./assets/icon-person.svg" alt="" />
            <input type="text" v-model="people" placeholder="Enter people" />
          </div>
        </div>
        <div class="flex-right">
          <Result
            :tip-amount="
              people != 0 ? ((bill * tip) / 100 / people).toFixed(2) : 'Err'
            "
            :total="
              people != 0
                ? (bill / people + (bill * tip) / 100 / people).toFixed(2)
                : 'Err'
            "
            :onClick="reset"
          />
        </div>
      </div>
    </main>
  </div>
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

.flex {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  gap: 20px;
}

.flex-left {
  width: 100%;
}

.flex-right {
  width: 100%;
}

.header-main {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem 0;
}

.all {
  display: flex;
  align-items: center;
  justify-content: center;
}

main {
  padding: 2rem;
  background-color: white;
  border-radius: 1.5rem 1.5rem 0 0;
  width: 100%;
  max-width: 800px;
}

.select-tip {
  display: grid;
  grid-template-columns: repeat(2, calc(50% - 0.5rem));
  gap: 0.75rem;
  margin-bottom: 1rem;
}

.select-tip button {
  border: none;
  background-color: var(--neutral-cyan);
  font-size: 1.2rem;
  font-weight: bold;
  color: white;
  font-family: var(--font);
  cursor: pointer;
  border-radius: 0.5rem;
  padding: 0.75rem;
  transition: all 0.2s ease-in-out;
  box-sizing: border-box;
}

.select-tip input {
  box-sizing: border-box;
  color: var(--neutral-cyan);
  outline: none;
  font-size: 1.2rem;
  font-weight: bold;
  border-radius: 0.5rem;
  padding: 0.75rem;
  background-color: var(--neutral-light-cyan);
  border: none;
  text-align: end;
}

.select-tip .active {
  background-color: var(--primary);
}

.select-tip button:hover {
  opacity: 0.8;
}

.screen {
  padding: 10px 20px;
  margin-bottom: 20px;
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
  box-sizing: border-box;
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

.error {
  border: 1px solid red;
  color: red;
}

@media screen and (min-width: 768px) {
  .header-main {
    padding: 4rem;
  }
  main {
    padding: 2rem;
    border-radius: 1.5rem;
  }
  .flex-left {
    width: 45%;
  }

  .flex {
    flex-direction: row;
    gap: 40px;
  }

  .select-tip {
    grid-template-columns: repeat(3, calc(33% - 0.5rem));
  }
}
</style>
