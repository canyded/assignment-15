<!-- DatePickerComponent.vue -->
<template>
    <div>
      <label for="datepicker">Select a date:</label>
      <input
        type="date"
        id="datepicker"
        v-model="selectedDate"
        @input="handleDateInput"
      />
      <p>Selected Date: {{ selectedDate }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        selectedDate: null,
      };
    },
    methods: {
      handleDateInput(event) {
        this.selectedDate = event.target.value;
      },
    },
  };
  </script>
  
  <style>
 
  </style>
  