<template>
    <div v-if="isVisible" class="modal-overlay">
      <div class="modal">
        <div class="modal-header">
          <span class="close-btn" @click="closeModal">&times;</span>
        </div>
        <div class="modal-content">
          <h2>{{ title }}</h2>
          <slot></slot>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: {
        type: String,
        default: 'Modal',
      },
    },
    data() {
      return {
        isVisible: true,
      };
    },
    methods: {
      closeModal() {
        this.isVisible = false;
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
  }
  
  .modal {
    background-color: #fff;
    border-radius: 4px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    overflow: hidden;
    width: 400px;
  }
  
  .modal-header {
    background-color: #007bff;
    color: #fff;
    padding: 15px;
    text-align: right;
  }
  
  .close-btn {
    cursor: pointer;
    font-size: 18px;
    font-weight: bold;
  }
  
  .modal-content {
    padding: 20px;
  }
  
  .modal-content h2 {
    font-size: 1.5em;
    margin-bottom: 10px;
  }
  </style>
  