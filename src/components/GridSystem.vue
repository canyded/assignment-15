
<template>
    <div class="grid-system">
      <div v-for="(row, rowIndex) in grid" :key="rowIndex" class="grid-row">
        <div
          v-for="(col, colIndex) in row"
          :key="colIndex"
          class="grid-column"
        >
          {{ col }}
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        grid: [
          ['1A', '1B', '1C', '1D'],
          ['2A', '2B', '2C', '2D'],
          ['3A', '3B', '3C', '3D'],
          
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  
  
  .grid-system {
    display: grid;
    gap: 10px;
  }
  
  .grid-row {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    gap: 10px;
  }
  
  .grid-column {
    padding: 10px;
    border: 1px solid #ddd;
  }
  </style>
  