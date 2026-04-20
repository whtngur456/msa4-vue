<script setup>
// 자식 컴포넌트에서 defineProps()를 이용해 넘어온 데이터 선언
//  이때 부모 컴포넌트에서 넘겨줄 때 사용한 키를 사용해 선언
//  데이터 타입도 지정
import { defineProps } from 'vue';  
// Props에서는 setup을 쓰면 생략가능

const Props =defineProps({
  cnt: Number,
  page: Number,
})

//프롭스 검증하는방식
// defineProps({
//   'cnt': Number,
//   'page': Number,
// });

// 자식 컴포넌트에서는 defineEmits()를 이용해 넘어온 컴포넌트 이벤트 선언
//   이때 부모 컴포넌트에서 넘겨줄때 사용한 이벤트 명을 사용해 선언
const emit= defineEmits(['minusCnt']);

</script>

<template>
  <h1>{{page}}프롭스 자식 컴포넌트: {{ cnt }}</h1>
  <button type="button" @click="emit('minusCnt', 10)">감소(자식쪽)</button>

</template>
  
<style scoped>

</style >