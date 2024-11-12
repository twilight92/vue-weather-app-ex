<template>
  <div>
    <h2>Child Component</h2>
    <!-- style 안에 들어가는 내용은 자료형이기 때문에 객체 형태로 입력 -->
    <p :style="{ color: color, backgroundColor: bgColor }">{{ color }}</p>
  </div>
</template>

<script setup>
const props = defineProps({
  color: String,
  bgColor: String,
});

console.log(props.color);
</script>

<style></style>
