

<template>
    <div class="form-toggle-group">
      <label class="group-label">{{ label }}</label>
      <div v-for="(option, index) in options" :key="index" class="toggle-option">
        <label :for="`${id}-${index}`" class="toggle-label">{{ option.label }}</label>
        <input
          :id="`${id}-${index}`"
          type="checkbox"
          :checked="selectedToggles.includes(option.value)"
          @change="handleToggleChange(option.value)"
          class="custom-toggle visually-hidden"
        />
        <div :class="{ 'toggle-switch': true, 'toggle-switch-on': selectedToggles.includes(option.value) }"></div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      id: String,
      label: String,
      options: Array,
      value: Array,
    },
    data() {
      return {
        selectedToggles: this.value || [],
      };
    },
    watch: {
      value(newVal) {
        this.selectedToggles = newVal;
      },
    },
    methods: {
      handleToggleChange(optionValue) {
        const index = this.selectedToggles.indexOf(optionValue);
  
        if (index === -1) {
          this.selectedToggles.push(optionValue);
        } else {
          this.selectedToggles.splice(index, 1);
        }
  
        this.$emit('input', this.selectedToggles);
      },
    },
  };
  </script>
  
  <style scoped>
  .form-toggle-group {
    margin-bottom: 20px;
  }
  
  .group-label {
    display: block;
    margin-bottom: 8px;
    color: #333;
    font-weight: bold;
  }
  
  .toggle-option {
    margin-bottom: 8px;
    display: flex;
    align-items: center;
  }
  
  .custom-toggle {
    position: absolute;
    opacity: 0;
    width: 0;
    height: 0;
  }
  
  .toggle-switch {
    width: 40px;
    height: 20px;
    border-radius: 10px;
    position: relative;
    cursor: pointer;
    margin-left: 10px;
    background-color: rgb(181, 179, 179); 
    transition: background-color 0.3s ease-in-out;
  }
  
  .toggle-switch-on {
    background-color: blue; 
  }
  
  .toggle-switch:before {
    content: '';
    width: 16px;
    height: 16px;
    background-color: #e0dddd;
    border-radius: 50%;
    position: absolute;
    top: 2px;
    left: 2px;
    transition: transform 0.3s ease-in-out;
  }
  
  .custom-toggle:checked + .toggle-switch:before {
    transform: translate(20px, 0);
  }
  
  .toggle-label {
    margin-right: 10px;
    color: #333;
  }
  
  .visually-hidden {
    position: absolute;
    width: 1px;
    height: 1px;
    margin: -1px;
    padding: 0;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    border: 0;
  }
  </style>
  