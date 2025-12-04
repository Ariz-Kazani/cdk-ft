<script setup>
const ROWS = 8;
const COLS = 8;


</script>


<template>
  <div class="chess-board">
    <div v-for="row in ROWS" :key="row" class="row">
      <div v-for="col in COLS" :key="col" :class="['square', (row + col) % 2 === 0 ? 'light' : 'dark']">
        {{ square }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.chess-board {
  width: 100%;
  background-color: #f0d9b5;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(8, 1fr);
  border: 2px solid #535353;
}

.row {
  width: 100%;
  display: flex;
}

.square {
  width: 100%;
  height: 100%;
  aspect-ratio: 1 / 1;
}

.light {
  background-color: white;
  color: black;
}

.dark {
  background-color: black;
  color: white;
}
</style>
