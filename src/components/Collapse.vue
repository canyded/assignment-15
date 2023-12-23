
<template>
    <div class="collapse">
      <div class="collapse-header" @click="toggleCollapse">
        <h3>{{ title }}</h3>
        <span :class="{ 'rotate-icon': isOpen }">&#9660;</span>
      </div>
      <div v-show="isOpen" class="collapse-content">
        <slot></slot>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: String,
    },
    data() {
      return {
        isOpen: false,
      };
    },
    methods: {
      toggleCollapse() {
        this.isOpen = !this.isOpen;
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .collapse {
    max-width: 400px;
    margin: 20px auto;
  }
  
  .collapse-header {
    padding: 10px;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    background-color: #f4f4f4;
    border: 1px solid #ddd;
    border-radius: 4px;
  }
  
  .rotate-icon {
    transform: rotate(180deg);
    transition: transform 0.3s ease-in-out;
  }
  
  .collapse-content {
    padding: 10px;
    background-color: #fff;
    border: 1px solid #ddd;
    border-top: none;
    border-radius: 0 0 4px 4px;
    overflow: hidden;
    transition: max-height 0.3s ease-in-out;
    max-height: 500px; 
  }
  
  .collapse-content > * {
    margin-top: 10px;
  }
  
  .collapse-content:not(.open) {
    max-height: 0;
    overflow: hidden;
  }
  </style>
  