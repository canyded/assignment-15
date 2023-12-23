
<template>
    <div>
      <button class="toggle-btn" @click="toggleSidebar">&#9776;</button>
      <aside class="page-sidebar" :class="{ 'sidebar-open': isOpen }">
        <button class="close-btn" @click="toggleSidebar">&times;</button>
        <nav class="sidebar-menu">
          <ul>
            <li v-for="(item, index) in menuItems" :key="index">
              <router-link :to="item.link" @click="closeSidebar">{{ item.label }}</router-link>
            </li>
          </ul>
        </nav>
      </aside>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isOpen: false,
        menuItems: [
          { label: 'Home', link: '/' },
          { label: 'About Us', link: '/about' },
          { label: 'Services', link: '/services' },
          { label: 'Contact', link: '/contact' },
        ],
      };
    },
    methods: {
      toggleSidebar() {
        this.isOpen = !this.isOpen;
      },
      closeSidebar() {
        this.isOpen = false;
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .page-sidebar {
    width: 250px;
    height: 100%;
    position: fixed;
    top: 0;
    left: -250px;
    background-color: #c3e4fe;
    padding-top: 20px;
    transition: left 0.3s ease;
  }
  
  .sidebar-open {
    left: 0;
  }
  
  .close-btn {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 24px;
    color: #ecf0f1;
    background: none;
    border: none;
    cursor: pointer;
  }
  
  .toggle-btn {
    position: fixed;
    top: 20px;
    left: 20px;
    font-size: 24px;
    color: #ecf0f1;
    background: none;
    border: none;
    cursor: pointer;
  }
  
  .sidebar-menu ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  
  .sidebar-menu li {
    margin-bottom: 10px;
  }
  
  .sidebar-menu a {
    text-decoration: none;
    color: #ecf0f1;
    font-size: 1.2em;
    display: block;
    padding: 10px;
    border-radius: 4px;
    transition: background-color 0.3s ease;
  }
  
  .sidebar-menu a:hover {
    background-color: #b7c4d2; 
  }
  </style>
  