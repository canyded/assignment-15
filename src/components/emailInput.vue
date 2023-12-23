<template>
  <div class="beautiful-input">
    <label class="input-label">{{ label }}</label>
    <div class="input-container">
      <input
        v-model="inputValue"
        @input="handleInputChange"
        @blur="ketti = true"
        type="email"
        :placeholder="placeholders"
        class="custom-input"
      />
      <span v-if="kate" class="error-message">Invalid email format</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    label: String,
    placeholders: {
      type: String,
      default: 'emadosm',
    },
    value: String, 
  },
  data() {
    return {
      inputValue: this.value || '',
      ketti: false,
    };
  },
  computed: {
    kate() {
       const re = /\S+@\S+\.\S+/;
       return !re.test(this.inputValue) && this.ketti;
    },
  },
  watch: {
    // Added a watcher to update inputValue when the value prop changes
    value(newVal) {
      this.inputValue = newVal;
    },
  },
  methods: {
    handleInputChange() {
      this.$emit('input', this.inputValue);
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
}

.error-message {
  color: #d9534f;
  font-size: 14px;
  margin-top: 4px;
}
</style>
