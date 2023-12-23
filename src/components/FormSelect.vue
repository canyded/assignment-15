<template>
    <div class="custom-select">
      <label :for="id" class="select-label">{{ label }}</label>
      <select :id="id" :name="name" v-model="selectedOption" class="select-box">
        <option
          v-for="(option, index) in options"
          :key="index"
          :value="option.value"
          class="select-option"
        >
          {{ option.label }}
        </option>
      </select>
    </div>
  </template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      required: true,
    },
    options: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      selectedOption: null,
    };
  },
};
</script>
  
  <style scoped>
  
  .custom-select {
    position: relative;
    width: 200px; 
  }
  
  .select-label {
    display: block;
    margin-bottom: 8px;
    font-weight: bold;
  }
  
  .select-box {
    margin-left: 20px;
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #fff;
    color: #333;
    font-size: 16px;
  }
  
  .select-option {
    background-color: #fff;
    color: #333;
  }
  
  .select-option:hover,
  .select-option:focus {
    background-color: #f0f0f0;
  }
  
  .select-box::after {
    content: '\25BC';
    position: absolute;
    top: 50%;
    right: 10px;
    transform: translateY(-50%);
    pointer-events: none;
  }
  </style>
  