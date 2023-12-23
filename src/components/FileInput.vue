<template>
    <div id="app" class="container">
      <div class="file-input">
        <label for="file" class="file-label">
          <input
            id="file"
            type="file"
            class="file-input"
            @change="handleFileChange"
          />
          <span class="file-cta">
            <span class="file-icon">
              <i class="fas fa-upload"></i>
            </span>
            <span class="file-label">Choose a file…</span>
          </span>
        </label>
        <p class="file-name" v-if="selectedFile">{{ selectedFile.name }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        selectedFile: null,
      };
    },
    methods: {
      handleFileChange(event) {
        this.selectedFile = event.target.files[0];
      },
    },
  };
  </script>
  
  <style>
  .file-input {
    position: relative;
    overflow: hidden;
    background-color: rgb(231, 230, 230);
  }
  
  .file-input input[type="file"] {
    position: absolute;
    font-size: 999px;
    opacity: 0;
  }
  
  .file-input .file-label {
    cursor: pointer;
    display: inline-block;
    line-height: 1.5;
    padding: 10px 20px;
  }
  
  .file-input .file-cta {
    display: flex;
    align-items: center;
  }
  
  .file-input .file-icon {
    margin-right: 8px;
  }
  
  .file-input .file-name {
    margin-top: 10px;
    font-size: 14px;
    color: #333;
  }
 
  </style>
  
  