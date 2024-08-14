<script setup>
import HelloWorld from './components/HelloWorld.vue';
import VCalendar from 'v-calendar';
import { ref } from 'vue';

const select = ref('nanum');
const isDarkMode = ref(false);

const changeFont = (e) => {
  console.log(select.value);
};

const changeDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
  document.documentElement.setAttribute('color-theme', isDarkMode.value ? 'dark' : 'light');
};

function openPopups() {
  setTimeout(function () {
    let popup1 = window.open('', 'Popup1', 'width=300,height=200,top=100,left=100');
    popup1.document.write('<h1>첫 번째 팝업</h1>');
  }, 0);

  setTimeout(function () {
    let popup3 = window.open('', 'Popup3', 'width=300,height=200,top=300,left=700');
    popup3.document.write('<h1>세 번째 팝업</h1>');
  }, 200);

  setTimeout(function () {
    let popup2 = window.open('', 'Popup2', 'width=300,height=200,top=150,left=400');
    popup2.document.write('<h1>두 번째 팝업</h1>');
  }, 400);
}
</script>

<template>
  <div :class="selec">
    <button @click="changeDarkMode">
      <div v-if="!isDarkMode">다크모드</div>
      <div v-else>라이트모드</div>
    </button>
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

  <div class="">
    <p>팝업테스트</p>

    <button @click="openPopups">팝업 열기</button>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100..900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Nanum+Pen+Script&family=Noto+Sans+KR:wght@100..900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');

:root[color-theme='light'] {
  --background-color: #ffffff;
  --text-color: #000000;
}

:root[color-theme='dark'] {
  --background-color: #121212;
  --text-color: #ffffff;
}

body {
  background-color: var(--background-color);
  color: var(--text-color);
}

button {
  margin: 20px;
  padding: 10px;
  cursor: pointer;
}

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
