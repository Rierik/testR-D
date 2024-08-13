<script setup>
import HelloWorld from './components/HelloWorld.vue';
import VCalendar from 'v-calendar';
import { ref } from 'vue';

const select = ref('nanum');

const changeFont = (e) => {
  console.log(select.value);
};
</script>

<template>
  <div :class="select">
    <select @click="changeFont" v-model="select">
      <option value="nanum">NanumPenScript</option>
      <option value="roboto">Roboto</option>
      <option value="sans">NotoSans</option>
    </select>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
    <div>ririririri</div>
    <div>가가가가가</div>
    <HelloWorld msg="Vite + Vue" />
    <VCalendar title-position="left" />
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100..900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Nanum+Pen+Script&family=Noto+Sans+KR:wght@100..900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');

.nanum {
  font-family: 'Nanum Pen Script', cursive;
  font-weight: 400;
  font-style: normal;
}

.sans {
  font-family: 'Noto Sans KR', sans-serif;
  font-optical-sizing: auto;
  font-weight: 500;
  font-style: normal;
}

.roboto {
  font-family: 'Roboto', sans-serif;
  font-weight: 400;
  font-style: normal;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
