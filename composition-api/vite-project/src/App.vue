<script setup>
// props 변수(상태변수) 추가시 ref 함수 필요
import { ref, onMounted, watch } from "vue";
import ChildCompVue from "./components/ChildComp.vue";

let count = ref(0); // 상태변수 초기값(state)
let title = "Hello Vue";
let color = ref("green");

onMounted(() => {
  console.log("mounted");
});

const increaseCount = () => {
  count.value++;
};

watch(color, () => {
  console.log("color 변경");
});
</script>

<template>
  <div>
    <h1>{{ title }}</h1>
    <button @click="increaseCount">count++</button>
    <p>{{ count }}</p>
    <ChildCompVue :color="color" bgColor="yellow" />
    <button @click="color = 'red'">Change color</button>
  </div>
</template>

<style scoped></style>
