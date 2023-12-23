
<template>
    <div class="progress-container">
      <div class="progress-bar" :style="{ width: progress + '%' }"></div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      progress: {
        type: Number,
        default: 0,
      },
    },
  };
  </script>
  
  <style scoped>
  
  .progress-container {
    width: 100%;
    background-color: #f4f4f4;
    border: 1px solid #ddd;
    border-radius: 4px;
    overflow: hidden;
  }
  
  .progress-bar {
    height: 20px;
    background-color: #007bff;
    transition: width 0.3s ease-in-out;
  }
  </style>
  