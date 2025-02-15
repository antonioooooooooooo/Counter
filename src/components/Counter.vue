<script setup>
import { ref } from "vue";

const count = ref(0);
</script>

<template>
  <div class="counter-wrapper">
    <div class="button-wrapper">
      <button
        class="button"
        @click="count++"
      >Increment</button>
      <button
        class="button"
        @click="count--"
      >Decrement</button>
    </div>
    <p class="counter-text">The current count is: {{ count }}.</p>
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
  border: 1px solid #c794ff;
  cursor: pointer;
  background-color: #d6b1ff;
  transition: background-color 0.2s ease-in-out;
  font-size: 14px;
  font-family: "Open Sans";
  color: #202020;
  font-weight: 700;
}
.button:hover {
  background-color: #c794ff;
}
.counter-text {
  margin-top: 20px;
  font-size: 20px;
  font-family: "Open Sans";
  color: #202020;
}
</style>