
<template>
    <nav class="navigation-links">
      <ul>
        <li v-for="(link, index) in links" :key="index">
          <a :href="link.url">{{ link.label }}</a>
        </li>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    props: {
      links: {
        type: Array,
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>
  
  .navigation-links {
    background-color: #333;
    padding: 10px;
  }
  
  ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
  }
  
  li {
    margin-right: 10px;
  }
  
  a {
    text-decoration: none;
    color: #fff;
    font-weight: bold;
    transition: color 0.3s ease;
  }
  
  a:hover {
    color: #3498db;
  }
  </style>
  