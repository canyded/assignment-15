<template>
  <div class="password-input">
    <label>{{ label }}</label>
    <div class="input-container">
      <input
        v-model="inputValue"
        @input="handleInputChange"
        @blur="handleBlur"
        :type="showPassword ? 'text' : 'password'"
        :placeholder="placeholders"
        class="custom-input"
      />
      <img
        class="show-password-icon"
        :src="showPassword ? './src/assets/view.png' : './src/assets/closed-eyes.png'"
        alt="Toggle Password Visibility"
        @click="toggleShowPassword"
      />
    </div>
    <span v-if="isRequired" class="error-message">Password must contain a minimum of 8 characters</span>
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
  },
  data() {
    return {
      inputValue: this.value || '',
      ketti: false,
      showPassword: false,
    };
  },
  computed: {
    isRequired() {
      return this.inputValue.length < 8 && this.ketti;
    },
  },
  methods: {
    handleInputChange() {
      this.$emit('input', this.inputValue);
    },
    handleBlur() {
      this.ketti = true;
    },
    toggleShowPassword() {
      this.showPassword = !this.showPassword;
    },
  },
};
</script>

<style scoped>
.password-input {
  font-family: 'Arial', sans-serif;
  margin-bottom: 20px;
  font-family: 'Arial', sans-serif;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s ease-in-out;
}

label {
  display: block;
  margin-bottom: 8px;
  color: #333;
  font-weight: bold;
}

.input-container {
  position: relative;
  width: 100%;
}

.custom-input {
  width: calc(100% - 30px); 
  padding: 12px;
  box-sizing: border-box;
  border: 1px solid #ddd;
  border-radius: 6px;
  font-size: 16px;
  display: inline-block;
}

.show-password-icon {
  cursor: pointer;
  position: absolute;
  top: 50%;
  right: 10px;
  transform: translateY(-50%);
  width: 20px;
  height: 20px;
}

.show-password-icon:hover {
  opacity: 0.7;
}

.error-message {
  color: red;
  font-size: 14px;
  margin-top: 4px;
}
</style>
