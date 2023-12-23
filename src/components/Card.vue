
<template>
    <div class="card">
      <img :src="image" alt="еммаааааа карасай ананы" class="card-image" />
      <div class="card-content">
        <h2 class="card-title">{{ title }}</h2>
        <p class="card-description">{{ description }}</p>
        <button @click="handleButtonClick">ок досм</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      image: String,
      title: String,
      description: String,
    },
    methods: {
      handleButtonClick() {
        console.log(`Button clicked for ${this.title}`);
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .card {
    max-width: 300px;
    margin: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    overflow: hidden;
    transition: transform 0.3s ease-in-out;
  }
  
  .card:hover {
    transform: scale(1.05);
  }
  
  .card-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
  }
  
  .card-content {
    padding: 15px;
  }
  
  .card-title {
    font-size: 1.2rem;
    margin-bottom: 10px;
  }
  
  .card-description {
    color: #555;
    margin-bottom: 15px;
  }
  
  button {
    background-color: #007bff;
    color: #fff;
    border: none;
    padding: 8px 15px;
    border-radius: 4px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  