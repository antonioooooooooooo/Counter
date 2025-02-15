<script setup>
import { ref } from "vue";

const initialCount = localStorage.getItem("count") || 0;
const count = ref(initialCount);

function increment() {
  count.value++;
  localStorage.setItem("count", count.value);
}

function decrement() {
  count.value--;
  localStorage.setItem("count", count.value);
}

function reset() {
  count.value = 0;
  localStorage.removeItem("count");
}
</script>

<template>
  <div class="counter-wrapper">
    <div class="button-wrapper">
      <button
        class="button"
        @click="increment()"
      >Increment</button>
      <button
        class="button"
        @click="decrement()"
      >Decrement</button>
    </div>
    <p class="counter-text">The current count is: {{ count }}.</p>
    <button
      class="reset-button"
      @click="reset()"
    >Reset</button>
  </div>
</template>

<style scoped>
.counter-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
}
.button-wrapper {
  display: flex;
  gap: 14px;
}
.button {
  height: 50px;
  width: 120px;
  border-radius: 8px;
  border: 1px solid #2e96a1;
  cursor: pointer;
  background-color: #5fc6d2;
  transition: background-color 0.2s ease-in-out;
  font-size: 14px;
  font-family: "Open Sans";
  color: #202020;
  font-weight: 700;
}
.button:hover {
  background-color: #2e96a1;
}
.counter-text {
  margin-top: 20px;
  font-size: 20px;
  font-family: "Open Sans";
  color: #202020;
}
.reset-button {
  margin-top: 20px;
  border-radius: 8px;
  height: 28px;
  width: 60px;
  background-color: #a20200;
  color: white;
  border: 1px solid black;
  transition: background-color 0.2s ease-in-out;
  cursor: pointer;
  font-family: "Open Sans";
}
.reset-button:hover {
  background-color: #740200;
}
</style>