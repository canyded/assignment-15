

<template>
    <div class="group-buttons">
      <button
        v-for="(button, index) in buttons"
        :key="index"
        @click="toggleButton(button)"
        :class="{ 'active': selectedButtons.includes(button) }"
      >
        {{ button.label }}
      </button>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    props: {
      buttons: Array,
      value: Array,
    },
    setup(props, { emit }) {
      const selectedButtons = ref(props.value || []);
  
      const toggleButton = (button) => {
        if (selectedButtons.value.includes(button)) {
          selectedButtons.value = selectedButtons.value.filter((b) => b !== button);
        } else {
          selectedButtons.value = [...selectedButtons.value, button];
        }
  
        emit('update:value', selectedButtons.value);
      };
  
      return { selectedButtons, toggleButton };
    },
  };
  </script>
  
  <style scoped>
  .group-buttons {
    display: flex;
  }
  
  button {
    padding: 10px;
    margin-right: 8px;
    border: 1px solid #ccc;
    background-color: #fff;
    cursor: pointer;
  }
  
  button.active {
    background-color: #3498db;
    color: #fff;
  }
  </style>
  