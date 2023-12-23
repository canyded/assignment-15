
<template>
    <nav class="pagination">
      <ul>
        <li @click="goToPage(1)" :class="{ 'disabled': currentPage === 1 }">&lt;&lt;</li>
        <li @click="prevPage" :class="{ 'disabled': currentPage === 1 }">&lt;</li>
  
        <li v-for="page in pages" :key="page" @click="goToPage(page)" :class="{ 'active': currentPage === page }">
          {{ page }}
        </li>
  
        <li @click="nextPage" :class="{ 'disabled': currentPage === totalPages }">&gt;</li>
        <li @click="goToPage(totalPages)" :class="{ 'disabled': currentPage === totalPages }">&gt;&gt;</li>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    props: {
      totalItems: {
        type: Number,
        required: true,
      },
      itemsPerPage: {
        type: Number,
        required: true,
      },
      currentPage: {
        type: Number,
        required: true,
      },
    },
    computed: {
      totalPages() {
        return Math.ceil(this.totalItems / this.itemsPerPage);
      },
      pages() {
        const start = Math.max(1, this.currentPage - 2);
        const end = Math.min(this.totalPages, start + 4);
  
        return Array.from({ length: end - start + 1 }, (_, i) => start + i);
      },
    },
    methods: {
      goToPage(page) {
        if (page >= 1 && page <= this.totalPages && page !== this.currentPage) {
          this.$emit('page-change', page);
        }
      },
      prevPage() {
        this.goToPage(this.currentPage - 1);
      },
      nextPage() {
        this.goToPage(this.currentPage + 1);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Styled component-specific styles */
  
  .pagination {
    margin-top: 20px;
  }
  
  ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
  }
  
  li {
    cursor: pointer;
    padding: 5px 10px;
    margin: 0 2px;
    border: 1px solid #ddd;
    border-radius: 4px;
    user-select: none;
    transition: background-color 0.3s ease, color 0.3s ease;
  }
  
  li:hover {
    background-color: #f4f4f4;
  }
  
  li.active {
    background-color: #3498db;
    color: #fff;
  }
  
  li.disabled {
    cursor: not-allowed;
    color: #aaa;
  }
  </style>
  