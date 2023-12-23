
<template>
    <div class="table-container">
      <table class="custom-table">
        <thead>
          <tr>
            <th v-for="(header, index) in headers" :key="index">{{ header }}</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(row, rowIndex) in rows" :key="rowIndex" :class="{ 'even-row': rowIndex % 2 === 0, 'odd-row': rowIndex % 2 !== 0 }">
            <td v-for="(cell, cellIndex) in row" :key="cellIndex">{{ cell }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      headers: {
        type: Array,
        required: true,
      },
      rows: {
        type: Array,
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>
  /* Modern component-specific styles */
  
  .table-container {
    width: 100%;
    overflow-x: auto;
  }
  
  .custom-table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
  }
  
  th, td {
    border: none;
    padding: 16px;
    text-align: left;
  }
  
  th {
    background-color: #2c3e50;
    color: #ecf0f1;
  }
  
  .even-row {
    background-color: #34495e;
    color: #ecf0f1;
  }
  
  .odd-row {
    background-color: #2c3e50;
    color: #ecf0f1;
  }
  </style>
  