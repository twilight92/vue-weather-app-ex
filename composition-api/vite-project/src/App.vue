<script setup>
// props 변수(상태변수) 추가시 ref 함수 필요
import { onMounted, ref } from "vue";
import ChildCompVue from "./components/ChildComp.vue";

let count = ref(0); // 상태변수 초기값(state)
let title = "Hello Vue";

onMounted(() => {
  console.log("mounted");
});

const increaseCount = () => {
  count.value++;
};
</script>

<template>
  <div>
    <h1>{{ title }}</h1>
    <button @click="increaseCount">count++</button>
    <p>{{ count }}</p>
    <ChildCompVue />
  </div>
</template>

<style scoped></style>
