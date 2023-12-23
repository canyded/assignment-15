
<template>
    <footer class="page-footer">
      <p>&copy; {{ currentYear }} Arman Armn Arman. All rights reserved.</p>
    </footer>
  </template>
  
  <script>
  export default {
    data() {
      return {
        currentYear: new Date().getFullYear(),
      };
    },
  };
  </script>
  
  <style scoped>
  /* Styled component-specific styles */
  
  .page-footer {
    text-align: center;
    padding: 20px;
    background-color: #2c3e50;
    color: #ecf0f1;
    bottom: 0;
    width: 100%;
  }
  </style>
  