<template>
  <div class="beautiful-radio">
    <label :style="{ color: labelColor }" class="radio-label">{{ label }}</label>
    <div v-for="(option, index) in options" :key="index" class="radio-option">
      <input
        type="radio"
        :id="getOptionId(index)"
        :value="option.value"
        v-model="selectedOption"
        @change="handleOptionChange"
        :style="{ borderColor: labelColor }"
        class="custom-radio"
      />
      <label :for="getOptionId(index)" :style="{ color: labelColor }" class="radio-option-label">{{ option.label }}</label>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    label: String,
    options: Array,
    value: String,
    labelColor: {
      type: String,
      default: '#4a90e2', 
    },
  },
  data() {
    return {
      selectedOption: this.value || (this.options.length > 0 ? this.options[0].value : ''),
    };
  },
  methods: {
    handleOptionChange() {
      this.$emit('input', this.selectedOption);
    },
    getOptionId(index) {
      return `option-${index}`;
    },
  },
};
</script>

<style scoped>
.beautiful-radio {
  font-family: 'Arial', sans-serif;
  margin-bottom: 20px;
}

.radio-label {
  display: block;
  margin-bottom: 10px;
  font-weight: bold;
  font-size: 18px;
}

.radio-option {
  margin-bottom: 12px;
}

.custom-radio {
  margin-right: 8px;
  appearance: none;
  width: 16px;
  height: 16px;
  border: 2px solid; 
  border-radius: 50%;
  outline: none;
  transition: border-color 0.3s ease-in-out;
}

.custom-radio:checked {
  background-color: var(--label-color, #000000); 
  border-color: var(--label-color, #4a90e2);
}

.radio-option-label {
  font-size: 16px;
}
</style>
