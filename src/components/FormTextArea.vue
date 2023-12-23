

<template>
    <div class="form-textarea">
      <label :for="id">{{ label }}</label>
      <textarea
        :id="id"
        v-model="textareaValue"
        @input="handleTextareaChange"
        :placeholder="placeholder"
        class="custom-textarea"
      ></textarea>
      <span v-if="showError" class="error-message">{{ errorMessage }}</span>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      id: String,
      label: String,
      placeholder: String,
      value: String,
      required: Boolean,
    },
    data() {
      return {
        textareaValue: this.value || '',
        showError: false,
        errorMessage: 'This field is required.',
      };
    },
    watch: {
      value(newVal) {
        this.textareaValue = newVal;
      },
    },
    computed: {
      isInvalid() {
        return this.required && !this.textareaValue.trim();
      },
    },
    methods: {
      handleTextareaChange() {
        this.showError = this.isInvalid;
        this.$emit('input', this.textareaValue);
      },
    },
  };
  </script>
  
  <style scoped>
  .form-textarea {
    margin-bottom: 20px;
  }
  
  label {
    display: block;
    margin-bottom: 8px;
    color: #333;
    font-weight: bold;
  }
  
  .custom-textarea {
    width: 100%;
    padding: 12px;
    box-sizing: border-box;
    border: 1px solid #ddd;
    border-radius: 6px;
    font-size: 16px;
    transition: border-color 0.3s ease-in-out;
  }
  
  .custom-textarea:focus {
    outline: none;
    border-color: #66afe9;
  }
  
  .error-message {
    color: #d9534f;
    font-size: 14px;
    margin-top: 4px;
  }
  </style>
  