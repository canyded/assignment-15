<template>
    <div class="tooltip-container" @mouseenter="showTooltipHandler" @mouseleave="hideTooltipHandler">
      <slot></slot>
      <div v-if="showTooltip" class="tooltip">
        {{ tooltipText }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        showTooltip: false,
      };
    },
    props: {
      tooltipText: String,
    },
    methods: {
      showTooltipHandler() {
        this.showTooltip = true;
      },
      hideTooltipHandler() {
        this.showTooltip = false;
      },
    },
  };
  </script>
  
  <style scoped>
  
  
  .tooltip-container {
    position: relative;
    display: inline-block;
  }
  
  .tooltip {
    position: absolute;
    top: -30px;
    left: 50%;
    transform: translateX(-50%);
    background-color: #007bff;
    color: #fff;
    padding: 8px;
    border-radius: 4px;
    font-size: 14px;
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.3s, visibility 0.3s;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
    z-index: 1;
  }
  
  .tooltip-container:hover .tooltip {
    opacity: 1;
    visibility: visible;
  }
  </style>
  