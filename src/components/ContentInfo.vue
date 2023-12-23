<template>
    <div class="content-info">
      <div class="labels">
        <span v-for="(label, index) in labels" :key="index" class="label">{{ label }}</span>
      </div>
      <div class="content">
        <slot></slot>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      labels: Array,
    },
  };
  </script>
  
  <style scoped>
  
  
  .content-info {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 15px;
    background-color: #f9f9f9;
    border: 1px solid #ddd;
    border-radius: 8px;
    margin-bottom: 20px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  .labels {
    display: flex;
  }
  
  .label {
    background-color: #007bff;
    color: #fff;
    padding: 8px 15px;
    margin-right: 8px;
    border-radius: 6px;
    font-weight: bold;
  }
  
  .content {
    flex: 1;
    margin: 0 15px;
    font-size: 16px;
    color: #333;
  }
  
  .badges {
    display: flex;
  }
  
  .badge {
    background-color: #28a745;
    color: #fff;
    padding: 8px 15px;
    margin-left: 8px;
    border-radius: 6px;
    font-weight: bold;
  }
  </style>
  