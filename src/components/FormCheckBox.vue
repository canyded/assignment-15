

<template>
    <div class="form-checkbox-group">
      <label class="group-label">{{ label }}</label>
      <div v-for="(option, index) in options" :key="index" class="checkbox-option">
        <input
          :id="`${id}-${index}`"
          type="checkbox"
          :value="option.value"
          v-model="selectedOptions"
          class="custom-checkbox"
        />
        <label :for="`${id}-${index}`" class="checkbox-label">{{ option.label }}</label>
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
        selectedOptions: this.value || [],
      };
    },
    watch: {
      value(newVal) {
        this.selectedOptions = newVal;
      },
    },
    methods: {
      handleCheckboxChange() {
        this.$emit('input', this.selectedOptions);
      },
    },
  };
  </script>
  
  <style scoped>
  .form-checkbox-group {
    margin-bottom: 20px;
  }
  
  .group-label {
    display: block;
    margin-bottom: 8px;
    color: #333;
    font-weight: bold;
  }
  
  .checkbox-option {
    margin-bottom: 8px;
  }
  
  .custom-checkbox {
    margin-right: 8px;
  }
  
  .checkbox-label {
    display: inline-block;
    color: #333;
  }
  
  </style>
  