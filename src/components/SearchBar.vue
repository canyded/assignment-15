
<template>
    <div class="search-bar">
      <input v-model="searchQuery" type="text" placeholder="Search..." />
      <button @click="search" class="search-btn">&#128269;</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        searchQuery: '',
      };
    },
    methods: {
      search() {
        // Implement your search logic here
        console.log('Search for:', this.searchQuery);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Styled component-specific styles */
  
  .search-bar {
    display: flex;
    align-items: center;
  }
  
  input {
    padding: 10px;
    font-size: 1em;
    border: 1px solid #ddd;
    border-radius: 4px;
    margin-right: 10px;
  }
  
  .search-btn {
    background-color: #3498db;
    color: #fff;
    border: none;
    padding: 10px;
    font-size: 1.2em;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .search-btn:hover {
    background-color: #2980b9;
  }
  </style>
  