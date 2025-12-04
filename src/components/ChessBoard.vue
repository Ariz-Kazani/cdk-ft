<script setup>
import { ref } from 'vue';

const ROWS = 8;
const COLS = 8;

const highLights = ref(Array.from({ length: ROWS }, () => Array(COLS).fill(false)));

function toggleHighlight(row, col) {
  console.log(`Toggling highlight for row ${row}, col ${col}`);
  highLights.value[row - 1][col - 1] = !highLights.value[row - 1][col - 1];
}



</script>


<template>
  <div class="chess-board">
    <div v-for="row in ROWS" :key="row" class="row">
      <div v-for="col in COLS" :key="col"
        :class="['square', (row + col) % 2 === 0 ? 'light' : 'dark', highLights[row - 1][col - 1] ? 'highlight' : '']" @click="toggleHighlight(row, col)">
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
  border: 4px solid transparent;
}

.light {
  background-color: white;
  color: black;
}

.dark {
  background-color: black;
  color: white;
}

.highlight {
  border: 4px solid orange;
}
</style>
