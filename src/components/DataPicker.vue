<template>
    <div class="datetime-picker">
      <label class="label" for="date">Date:</label>
      <input class="input" type="date" id="date" v-model="selectedDate" @input="updateDateTime" />
  
      <label class="label" for="time">Time:</label>
      <input class="input" type="time" id="time" v-model="selectedTime" @input="updateDateTime" />
  
      <p class="result">Selected Date & Time: {{ selectedDateTime }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      const currentDatetime = new Date();
  
      return {
        selectedDate: this.formatDate(currentDatetime),
        selectedTime: this.formatTime(currentDatetime),
      };
    },
    computed: {
      selectedDateTime() {
        return `${this.selectedDate} ${this.selectedTime}`;
      },
    },
    methods: {
      updateDateTime() {
        // Handle the selected date and time logic here
        console.log("Selected Date:", this.selectedDate);
        console.log("Selected Time:", this.selectedTime);
        console.log("Selected Date & Time:", this.selectedDateTime);
      },
      formatDate(date) {
        return date.toISOString().slice(0, 10);
      },
      formatTime(date) {
        return date.toTimeString().slice(0, 5);
      },
    },
  };
  </script>
  
  <style scoped>
  .datetime-picker {
    font-family: 'Arial', sans-serif;
    max-width: 300px;
    margin: 20px auto;
    padding: 20px;
    background-color: #f4f4f4;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  
  .label {
    display: block;
    margin-bottom: 5px;
    color: #333;
    font-weight: bold;
  }
  
  .input {
    width: 100%;
    padding: 8px;
    margin-bottom: 15px;
    box-sizing: border-box;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 14px;
  }
  
  .result {
    font-size: 16px;
    font-weight: bold;
    color: #333;
  }
  </style>
  