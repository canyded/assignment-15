
<template>
    <nav class="navbar">
      <div class="logo">
        <img src="c:\Users\Администратор\Desktop\final project\arman\src\assets\closed-eyes.png" alt="Logo" />
      </div>
      <div class="nav-links">
        <a href="/">Home</a>
        <a href="/about">About</a>
        <a href="/services">Services</a>
        <a href="/contact">Contact</a>
      </div>
      <div class="search-bar">
        <input type="text" placeholder="Search..." />
        <button @click="search">Search</button>
      </div>
    </nav>
  </template>
  
  <script>
  export default {
    methods: {
      search() {
        // Add your search logic here
        console.log('Search button clicked');
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
    background-color: #3498db;
    color: #fff;
  }
  
  .logo img {
    height: 40px;
  }
  
  .nav-links a {
    margin-right: 20px;
    text-decoration: none;
    color: #fff;
    font-weight: bold;
    transition: color 0.3s ease;
  }
  
  .nav-links a:hover {
    color: #ffd700;
  }
  
  .search-bar {
    display: flex;
    align-items: center;
  }
  
  input {
    padding: 5px;
    margin-right: 10px;
    border: 1px solid #ddd;
    border-radius: 4px;
  }
  
  button {
    padding: 5px 10px;
    background-color: #fff;
    border: 1px solid #ddd;
    border-radius: 4px;
    cursor: pointer;
  }
  </style>
  