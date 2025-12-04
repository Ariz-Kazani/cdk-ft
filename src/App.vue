<script setup>
import { ref } from 'vue';

import ChessBoard from './components/ChessBoard.vue'
import SideBar from './components/SideBar.vue'

function handleSquareClicked(click) {
  sideBarClickList.value.push(click);
}

const sideBarClickList = ref([]);

</script>

<template>
  <div id="app" class="app">
    <div class="chess-board-con">
      <ChessBoard @square-clicked="handleSquareClicked" />
    </div>
    <div class="sidebar-con">
      <SideBar :listItems="sideBarClickList" />
    </div>
  </div>
</template>

<style scoped>
.app {
  min-height: 100vh;
  display: grid;
  background-color: #ccc;
  grid-template-columns: 1fr 400px;
}

.chess-board-con {
  width: 100%;
  padding: 10%;
  /* background-color: #000000; */
}

.sidebar-con {
  width: 100%;
  height: 100%;
}

@media screen and (max-width: 850px) {
  .app {
    display: flex;
    flex-direction: column;
    height: 100vh;
  }

  .chess-board-con {
    padding: 12px;
  }

}
</style>
