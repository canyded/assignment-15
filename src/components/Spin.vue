
<template>
    <div class="spin" v-if="loading">
      <div class="spinner"></div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        loading: false,
      };
    },
    mounted() {
      
      setTimeout(() => {
        this.loading = true;
        setTimeout(() => {
          this.loading = false;
        }, 15000);
      }, 500);
    },
  };
  </script>
  
  <style scoped>
  
  
  .spin {
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: rgba(189, 69, 69, 0.9);
    border-radius: 8px;
    padding: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    z-index: 1000;
  }
  
  .spinner {
    border: 4px solid #3498db;
    border-top: 4px solid transparent;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    animation: spin 1s linear infinite;
  }
  
  @keyframes spin {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
  </style>
  