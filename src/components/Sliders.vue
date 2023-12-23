

<template>
    <div class="sliders">
      <div v-for="(slider, index) in sliders" :key="index" class="slider-container">
        <label :for="slider.id" class="slider-label">{{ slider.label }}</label>
        <input
          :id="slider.id"
          type="range"
          :min="slider.min"
          :max="slider.max"
          :value="slider.value"
          @input="updateSlider(index, $event.target.value)"
          class="custom-slider"
        />
        <span class="slider-value">{{ slider.value }}</span>
      </div>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    props: {
      sliders: Array,
    },
    setup(props, { emit }) {
      const updateSlider = (index, value) => {
        const updatedSliders = [...props.sliders];
        updatedSliders[index].value = value;
        emit('update:sliders', updatedSliders);
      };
  
      return { updateSlider };
    },
  };
  </script>
  
  <style scoped>
  .sliders {
    display: flex;
    flex-direction: column;
  }
  
  .slider-container {
    margin-bottom: 20px;
  }
  
  .slider-label {
    margin-bottom: 8px;
    color: #333;
    font-weight: bold;
  }
  
  .custom-slider {
    width: 100%;
  }
  
  .slider-value {
    display: inline-block;
    margin-left: 8px;
    color: #333;
  }
  </style>
  