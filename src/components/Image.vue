
<template>
    <img :src="source" :alt="altText" class="image" />
  </template>
  
  <script>
  export default {
    props: {
      source: {
        type: String,
        required: true,
      },
      altText: {
        type: String,
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .image {
    max-width: 100%;
    height: auto;
    display: block;
  }
  </style>
  