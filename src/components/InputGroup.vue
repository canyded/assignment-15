
<template>
    <div class="input-groups">
      <div class="input-group">
        <label for="username">Username:</label>
        <div class="input-container">
          <span class="icon"><i class="fas fa-user"></i></span>
          <input type="text" id="username" v-model="formData.username" required />
        </div>
      </div>
  
      <div class="input-group">
        <label for="password">Password:</label>
        <div class="input-container">
          <span class="icon"><i class="fas fa-lock"></i></span>
          <input type="password" id="password" v-model="formData.password" required />
        </div>
      </div>
  
      <button @click="handleSubmit">Submit</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        formData: {
          username: '',
          password: '',
        },
      };
    },
    methods: {
      handleSubmit() {
        console.log('Data submitted:', this.formData);
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .input-groups {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .input-group {
    margin-bottom: 20px;
  }
  
  .input-container {
    position: relative;
  }
  
  .icon {
    position: absolute;
    left: 10px;
    top: 50%;
    transform: translateY(-50%);
    color: #777;
  }
  
  input {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
    padding-left: 30px; /* Space for icon */
  }
  
  button {
    background-color: #007bff;
    color: #fff;
    border: none;
    padding: 10px 20px;
    border-radius: 4px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  