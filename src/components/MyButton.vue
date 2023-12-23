

<template>
    <button
      :class="{'custom-button': true, 'primary-button': type === 'primary', 'secondary-button': type === 'secondary'}"
      @click="handleClick"
    >
      {{ label }}
    </button>
  </template>
  
  <script>
  export default {
    props: {
      label: String,
      type: {
        type: String,
        default: 'primary', 
        validator: value => ['primary', 'secondary'].includes(value),
      },
    },
    methods: {
      handleClick() {
        this.$emit('click'); 
      },
    },
  };
  </script>
  
  <style scoped>
  .custom-button {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    border: none;
    border-radius: 5px;
  }
  
  .primary-button {
    background-color: #3498db;
    color: #fff;
  }
  
  .secondary-button {
    background-color: #ecf0f1;
    color: #333;
  }
  </style>
  