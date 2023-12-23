
<template>
    <div v-if="isVisible" :class="['alert', `alert-${variant}`]">
      <span class="close-btn" @click="closeAlert">&times;</span>
      <strong>{{ title }}</strong>
      <p>{{ message }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: {
        type: String,
        default: 'Alert',
      },
      message: {
        type: String,
        default: '',
      },
      variant: {
        type: String,
        default: 'info', 
      },
      autoCloseDelay: {
        type: Number,
        default: 0, 
      },
    },
    data() {
      return {
        isVisible: true,
      };
    },
    created() {
      if (this.autoCloseDelay > 0) {
        setTimeout(this.closeAlert, this.autoCloseDelay);
      }
    },
    methods: {
      closeAlert() {
        this.isVisible = false;
        this.$emit('closed');
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .alert {
    position: relative;
    padding: 15px;
    margin: 15px 0;
    border-radius: 4px;
    font-size: 16px;
  }
  
  .alert-info {
    background-color: #f4f4f4;
    color: #333;
    border: 1px solid #ddd;
  }
  
  .alert-success {
    background-color: #d4edda;
    color: #155724;
    border: 1px solid #c3e6cb;
  }
  
  .alert-warning {
    background-color: #fff3cd;
    color: #856404;
    border: 1px solid #ffeeba;
  }
  
  .alert-danger {
    background-color: #f8d7da;
    color: #721c24;
    border: 1px solid #f5c6cb;
  }
  
  .close-btn {
    position: absolute;
    top: 5px;
    right: 10px;
    font-size: 20px;
    cursor: pointer;
  }
  </style>
  