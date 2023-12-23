
<template>
    <div>
      <canvas ref="chartCanvas"></canvas>
    </div>
  </template>
  
  <script>
  import { Line, Bar, Pie } from 'chart.js';
  
  export default {
    props: {
      chartType: {
        type: String,
        required: true,
      },
      chartData: {
        type: Object,
        required: true,
      },
    },
    data() {
      return {
        chart: null,
      };
    },
    mounted() {
      this.renderChart();
    },
    methods: {
      renderChart() {
        const ctx = this.$refs.chartCanvas.getContext('2d');
  
        switch (this.chartType) {
          case 'line':
            this.chart = new Line(ctx, {
              data: this.chartData,
            });
            break;
          case 'bar':
            this.chart = new Bar(ctx, {
              data: this.chartData,
            });
            break;
          case 'pie':
            this.chart = new Pie(ctx, {
              data: this.chartData,
            });
            break;
          default:
            console.error('Invalid chart type');
        }
      },
    },
  };
  </script>
  
  <style scoped>

  </style>
  