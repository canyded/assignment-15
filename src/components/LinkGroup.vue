
<template>
    <div class="link-group">
      <div v-for="(group, groupIndex) in linkGroups" :key="groupIndex" class="link-group-item">
        <div class="group-title">{{ group.title }}</div>
        <ul>
          <li v-for="(link, linkIndex) in group.links" :key="linkIndex">
            <a :href="link.url">{{ link.label }}</a>
          </li>
        </ul>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      linkGroups: {
        type: Array,
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>
  
  .link-group {
    display: flex;
    gap: 20px;
  }
  
  .link-group-item {
    width: 200px;
  }
  
  .group-title {
    font-weight: bold;
    margin-bottom: 8px;
  }
  
  ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  
  li {
    margin-bottom: 8px;
  }
  
  a {
    text-decoration: none;
    color: #333;
    transition: color 0.3s ease;
  }
  
  a:hover {
    color: #3498db;
  }
  </style>
  