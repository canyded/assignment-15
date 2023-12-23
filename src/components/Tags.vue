
<template>
    <div class="tags">
      <div v-for="(tag, index) in tags" :key="index" class="tag">
        {{ tag }}
        <span @click="() => removeTag(index)">&times;</span>
      </div>
      <input v-model="newTag" @keydown.enter="addTag" placeholder="Add a tag" />
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        tags: ['sdfsdfsdf','sdfsdfsdf'],
        newTag: '',
      };
    },
    methods: {
      addTag() {
        const trimmedTag = this.newTag.trim();
        if (trimmedTag && !this.tags.includes(trimmedTag)) {
          this.tags.push(trimmedTag);
          this.newTag = '';
        }
      },
      removeTag(index) {
        this.tags.splice(index, 1);
      },
    },
  };
  </script>
  
  <style scoped>
  
  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  
  .tag {
    background-color: #3498db;
    color: #fff;
    padding: 5px 10px;
    border-radius: 4px;
    display: flex;
    align-items: center;
  }
  
  .tag span {
    margin-left: 8px;
    cursor: pointer;
  }
  
  input {
    padding: 5px 10px;
    border: 1px solid #ddd;
    border-radius: 4px;
    margin-top: 8px;
  }
  </style>
  