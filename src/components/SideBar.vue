<script setup>

const props = defineProps({
  listItems: {
    type: Array,
    default: () => []
  }
});


</script>

<template>
  <div class="sidebar">
    <h1>
      Click List
    </h1>
    <ul>
      <li v-for="(item, index) in props.listItems" :key="index">
        Row: {{ item.row }}, Col: {{ item.col }}
      </li>
    </ul>
  </div>
</template>


<style scoped>
.sidebar {
  width: 100%;
  height: 100%;
  background-color: rgb(242, 242, 242);
  padding: 16px;
}

ul {
  padding-left: 20px;
  margin: 0;
}
</style>
