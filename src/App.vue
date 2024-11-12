<script setup>
import Navbar from "./components/Navbar.vue";
import MainComp from "./components/MainComp.vue";
import About from "./components/About.vue";
import { ref, onMounted } from "vue";
// import { useStore } from "vuex";
import { useStore } from "./store/store";

/*
  앱컴포넌트에서 필요한 상태 변수나 메소드들을 가져와야 함
  컴포넌트에서 상태변수들을 반응성있게 사용하려면 storeToRefs 함수에 상태변수들을 담아 사용해야함
*/
import { storeToRefs } from "pinia";

// store라는 변수에 useStore 함수를 가져옴
const store = useStore();

/*
  우리가 사용할 데이터들을 store에서 불러와야하는데
  그냥 가져오는 것이 아니라
  storeToRefs 안에 래핑을 해서 가져와야 함
*/
const { weatherData, toggle } = storeToRefs(store);

// 앱이 실행되면 날씨 데이터 가져오기
onMounted(() => {
  // store.dispatch("getWeather");
  store.getWeather();
});

const onSearchCity = (city) => {
  weatherData.value.city = city;
  getWeather();
};
</script>

<template>
  <!-- <button @click="$store.dispatch('getWeather')">getWeather</button> -->
  <Navbar />
  <div v-if="!$store.state.toggle">
    <MainComp />
  </div>
  <div v-else>
    <About />
  </div>
</template>

<style scoped lang="scss"></style>
