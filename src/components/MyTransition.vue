<script setup>
import {ref, Transition } from 'vue';

const flg = ref(false);

</script>

<template>
  <h1>MyTransition 트렌지션 {{ flg }}</h1>
  <button type="button" @click="flg = !flg" >토글</button>
  
  <Transition name="box">
    <div class="box" v-if="flg"></div>
  </Transition>
</template>
 
<style>
.box {
  width: 200px;
  height: 200px;
  background-color: aqua;
}

/* 등장 애니메이션 */
.box-enter-from {
  opacity: 0;
  transform: translateX(100vw);
}
.box-enter-active {
  transition: opacity 2s ease;
  transition: all 2s;
}
.box-enter-to {
  opacity: 1;
  transform: translateX(0);
}

/* 퇴장 애니메이션 */

.box-leave-from {
  transform: translateX(0);
}
.box-leave-active {
  transition: all 2s;
}
.box-leave-to {
  transform: translateX(100vw);
}

</style > 