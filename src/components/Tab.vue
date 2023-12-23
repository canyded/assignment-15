
<template>
    <div class="tabs">
      <div class="tab-header">
        <div
          v-for="(tab, index) in tabs"
          :key="index"
          @click="changeTab(index)"
          :class="{ 'active': currentTab === index }"
          class="tab-item"
        >
          {{ tab.label }}
        </div>
      </div>
      <div class="tab-content">
        {{ tabs[currentTab].content }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        currentTab: 0,
      };
    },
    props: {
      tabs: {
        type: Array,
        required: true,
      },
    },
    methods: {
      changeTab(index) {
        this.currentTab = index;
      },
    },
  };
  </script>
  
  <style scoped>
  /* Styled component-specific styles */
  
  .tabs {
    width: 100%;
  }
  
  .tab-header {
    display: flex;
    background-color: #3498db;
    color: #fff;
  }
  
  .tab-item {
    padding: 10px;
    cursor: pointer;
    flex: 1;
    text-align: center;
  }
  
  .tab-item.active {
    background-color: #fff;
    color: #3498db;
  }
  
  .tab-content {
    padding: 20px;
    border: 1px solid #ddd;
    border-top: none;
  }
  </style>
  