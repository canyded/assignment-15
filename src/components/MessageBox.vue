
<template>
    <div v-if="isVisible" class="message-box">
      <div class="message-box-header">
        <span class="close-btn" @click="closeMessageBox">&times;</span>
      </div>
      <div class="message-box-content">
        <h2>{{ title }}</h2>
        <slot></slot>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: {
        type: String,
        default: 'Message Box',
      },
    },
    data() {
      return {
        isVisible: true,
      };
    },
    methods: {
      closeMessageBox() {
        this.isVisible = false;
      },
    },
  };
  </script>
  
  <style scoped>
  
  .message-box {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 300px;
    background-color: #fff;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
    border: 1px solid #ddd;
    border-radius: 4px;
    overflow: hidden;
    opacity: 1;
    transition: opacity 0.3s;
    z-index: 1000;
  }
  
  .message-box-header {
    background-color: #007bff;
    color: #fff;
    padding: 10px;
    text-align: right;
  }
  
  .close-btn {
    cursor: pointer;
    font-size: 18px;
    font-weight: bold;
  }
  
  .message-box-content {
    padding: 20px;
  }
  
  .message-box-content h2 {
    font-size: 1.5em;
    margin-bottom: 10px;
  }
  </style>
  