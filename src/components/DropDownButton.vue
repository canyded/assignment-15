

<template>
    <div class="dropdown">
      <button @click="toggleDropdown" class="dropdown-toggle">
        <span>{{ selectedOption.label }}</span>
        <i class="arrow-icon" :class="{ 'arrow-up': isOpen, 'arrow-down': !isOpen }"></i>
      </button>
  
      <ul v-if="isOpen" class="dropdown-menu">
        <li v-for="(option, index) in options" :key="index" @click="selectOption(option)">
          {{ option.label }}
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    props: {
      options: Array,
      value: Object,
    },
    setup(props, { emit }) {
      const isOpen = ref(false);
      const selectedOption = ref(props.value || props.options[0]);
  
      const toggleDropdown = () => {
        isOpen.value = !isOpen.value;
      };
  
      const selectOption = (option) => {
        selectedOption.value = option;
        isOpen.value = false;
        emit('update:value', option); 
      };
  
      return { isOpen, selectedOption, toggleDropdown, selectOption };
    },
  };
  </script>
  
  <style scoped>
  .dropdown {
    position: relative;
    display: inline-block;
  }
  
  .dropdown-toggle {
    padding: 12px 20px;
    cursor: pointer;
    background-color: #3498db;
    color: #fff;
    border: none;
    border-radius: 5px;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  
  .dropdown-toggle span {
    flex-grow: 1;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
  
  .arrow-icon {
    position: relative;
    width: 10px;
    height: 10px;
    margin-left: 10px;
    transform: translateY(-50%);
  }
  
  .arrow-up {
    transform: translateY(-50%) rotate(180deg);
  }
  
  .dropdown-menu {
    list-style: none;
    padding: 0;
    margin: 0;
    position: absolute;
    top: 100%;
    left: 0;
    background-color: #fff;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    border-radius: 5px;
    z-index: 100;
    width: 100%;
    max-height: 200px;
    overflow-y: auto;
    overflow-x: hidden;
  }
  
  .dropdown-menu li {
    padding: 12px;
    cursor: pointer;
    transition: background-color 0.3s ease-in-out;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  
  .dropdown-menu li:hover {
    background-color: #ecf0f1;
  }
  </style>
  