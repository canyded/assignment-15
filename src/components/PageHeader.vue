
<template>
    <div class="page-header">
      <h1 class="title">{{ title }}</h1>
      <p class="subtitle">{{ subtitle }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: {
        type: String,
        required: true,
      },
      subtitle: {
        type: String,
        default: '',
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .page-header {
    text-align: center;
    margin-bottom: 30px;
  }
  
  .title {
    font-size: 2.5em;
    color: #3498db;
    margin-bottom: 10px;
  }
  
  .subtitle {
    font-size: 1.2em;
    color: #7f8c8d;
  }
  </style>
  