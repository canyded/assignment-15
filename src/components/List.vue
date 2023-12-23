
<template>
    <div class="list-container">
      <ul class="custom-list">
        <li v-for="(item, index) in items" :key="index">{{ item }}</li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      items: {
        type: Array,
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .list-container {
    width: 100%;
  }
  
  .custom-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  
  li {
    background-color: #ecf0f1;
    border: 1px solid #bdc3c7;
    padding: 12px;
    margin: 8px 0;
    border-radius: 4px;
    transition: background-color 0.3s ease;
    cursor: pointer;
  }
  
  li:hover {
    background-color: #3498db;
    color: #fff;
  }
  </style>
  