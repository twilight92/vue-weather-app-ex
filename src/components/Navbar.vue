<template>
  <nav class="navbar">
    <button class="toggle" @click="store.toggleButton()">
      <font-awesome-icon class="icon" :icon="['fas', 'bars-staggered']" />
    </button>
  </nav>
</template>

<script setup>
import { useStore } from "../store/store";

const store = useStore();

/*
  함수는 변수를 가져오지 않아도
  자연스럽게 함수 호출이 가능하다
*/
</script>

<style lang="scss" scoped>
.navbar {
  background: #fff;
  width: 100%;
  padding: 20px;
  display: flex;
  justify-content: end;

  button {
    border: none;
    background: transparent;
    cursor: pointer;
  }
  .icon {
    color: #333;
    font-size: 24px;
  }
}
</style>
