
<template>
    <div class="user-profile">
      <img :src="imageSource" :alt="altText" class="user-image" />
      <div class="user-details">
        <span class="user-name">{{ userName }}</span>
        <span class="user-role">{{ userRole }}</span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      imageSource: {
        type: String,
        required: true,
      },
      altText: {
        type: String,
        required: true,
      },
      userName: {
        type: String,
        required: true,
      },
      userRole: {
        type: String,
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>
  /* Styled component-specific styles */
  
  .user-profile {
    display: flex;
    align-items: center;
  }
  
  .user-image {
    border-radius: 50%;
    margin-right: 15px;
    width: 80px;
    height: 80px;
    object-fit: cover;
  }
  
  .user-details {
    display: flex;
    flex-direction: column;
  }
  
  .user-name {
    font-size: 18px;
    font-weight: bold;
    color: #333;
  }
  
  .user-role {
    font-size: 14px;
    color: #666;
  }
  </style>
  