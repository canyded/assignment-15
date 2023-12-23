
<template>
    <div class="accordion">
      <div v-for="(item, index) in items" :key="index" class="accordion-item">
        <div class="accordion-header" @click="toggleAccordion(index)">
          <h3>{{ item.title }}</h3>
          <span :class="{ 'rotate-icon': activeIndex === index }">&#9660;</span>
        </div>
        <div v-if="activeIndex === index" class="accordion-content">
          <p>{{ item.content }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        activeIndex: null,
        items: [
          {
            title: 'Section 1',
            content: 'Content asdasd',
          },
          {
            title: 'Section 2',
            content: 'sdfsdfsdfsdf',
          },
          {
            title: 'Section 3',
            content: 'dfsdfsdfsdf',
          },
        ],
      };
    },
    methods: {
      toggleAccordion(index) {
        this.activeIndex = this.activeIndex === index ? null : index;
      },
    },
  };
  </script>
  
  <style scoped>
  
  .accordion {
    max-width: 400px;
    margin: 20px auto;
  }
  
  .accordion-item {
    border: 1px solid #ddd;
    border-radius: 4px;
    margin-bottom: 10px;
    overflow: hidden;
  }
  
  .accordion-header {
    padding: 10px;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    background-color: #f4f4f4;
  }
  
  .rotate-icon {
    transform: rotate(180deg);
    transition: transform 0.3s ease-in-out;
  }
  
  .accordion-content {
    padding: 10px;
    background-color: #fff;
  }
  </style>
  