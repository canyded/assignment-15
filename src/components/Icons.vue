
<template>
    <div class="icons-container">
      <i v-if="type === 'heart'" class="icon-heart"></i>
      <i v-else-if="type === 'star'" class="icon-star"></i>
      <i v-else-if="type === 'check'" class="icon-check"></i>
      
    </div>
  </template>
  
  <script>
  export default {
    props: {
      type: {
        type: String,
        required: true,
        validator: (value) => ['heart', 'star', 'check'].includes(value),
      },
    },
  };
  </script>
  
  <style scoped>
  
  .icons-container {
    display: flex;
    align-items: center;
  }
  
  .icon-heart::before {
    content: '\2665'; 
    font-size: 24px;
    color: #e74c3c; 
  }
  
  .icon-star::before {
    content: '\2605'; 
    font-size: 24px;
    color: #f39c12; 
  }
  
  .icon-check::before {
    content: '\2713'; /* Unicode check mark character */
    font-size: 24px;
    color: #2ecc71; /* Green color for check mark */
  }
  </style>
  