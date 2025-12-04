<script setup>
import ChessBoard from './components/ChessBoard.vue'
import SideBar from './components/SideBar.vue'

</script>

<template>
  <div id="app" class="app">
    <div class="chess-board-con">
      <ChessBoard />
    </div>
    <div class="sidebar-con">
      <SideBar />
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
}

.sidebar-con {
  width: 100%;
  height: 100%;
}

@media screen and (max-width: 850px) {
  .app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  .chess-board-con {
    padding: 12px;
  }

}
</style>
