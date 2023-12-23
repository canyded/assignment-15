<template>
    <div class="drawer" :class="{ 'open': isOpen }">
      <div class="drawer-content">
        <slot>nbnbvnbvn</slot>
      </div>
      <div class="overlay" @click="closeDrawer" v-if="isOpen"></div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isOpen: false,
      };
    },
    methods: {
      openDrawer() {
        this.isOpen = true;
      },
      closeDrawer() {
        this.isOpen = false;
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .drawer {
    position: fixed;
    top: 0;
    left: -300px; 
    width: 300px;
    height: 100%;
    background-color: #fff;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    transition: left 0.3s ease;
    z-index: 1000;
  }
  
  .drawer.open {
    left: 0;
  }
  
  .drawer-content {
    padding: 20px;
    height: 100%;
    overflow-y: auto;
  }
  
  .overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: none;
  }
  
  .drawer.open + .overlay {
    display: block;
  }
  </style>
  