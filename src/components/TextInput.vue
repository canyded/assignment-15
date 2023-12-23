<template>
  <div class="beautiful-input">
    <label class="input-label">{{ label }}</label>
    <div class="input-container">
      <input
        v-model="inputValue"
        @input="handleInputChange"
        @blur="handleBlur"
        type="text"
        :placeholder="placeholders"
        class="custom-input"
      />
      <span v-if="isRequired" class="error-message">This field is required.</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    label: String,
    plsh: String,
    placeholders: {
      type: String,
      default: 'emadosm',
    },
  },
  data() {
    return {
      inputValue: this.value || '',
      ketti: false,
    };
  },
  computed: {
    isRequired() {
      return !this.inputValue && this.ketti;
    },
  },
  methods: {
    handleInputChange() {
      this.$emit('input', this.inputValue);
    },
    handleBlur() {
      this.ketti = true;
    },
  },
};
</script>

<style scoped>
.beautiful-input {
  font-family: 'Roboto', sans-serif;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s ease-in-out;
}

.input-label {
  display: block;
  margin-bottom: 8px;
  color: #333;
  font-weight: bold;
}

.input-container {
  display: flex;
  flex-direction: column;
}

.custom-input {
  width: 100%;
  padding: 12px;
  margin-bottom: 10px;
  box-sizing: border-box;
  border: 1px solid #ddd;
  border-radius: 6px;
  font-size: 16px;
  transition: border-color 0.3s ease-in-out;
}

.custom-input:focus {
  outline: none;
  border-color: #66afe9;
}

.error-message {
  color: #d9534f;
  font-size: 14px;
}
</style>
