
<template>
    <div :class="textClass">
      <slot></slot>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      variant: {
        type: String,
        default: 'body',
        validator: (value) => ['headline', 'body', 'caption'].includes(value),
      },
    },
    computed: {
      textClass() {
        return `text-${this.variant}`;
      },
    },
  };
  </script>
  
  <style scoped>
 
  
  .text-headline {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 10px;
  }
  
  .text-body {
    font-size: 16px;
    line-height: 1.5;
    margin-bottom: 10px;
  }
  
  .text-caption {
    font-size: 14px;
    color: #666;
  }
  </style>
  