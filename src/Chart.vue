<template>
  <div id="chart">
    <svg xmlns="http://www.w3.org/2000/svg" 
        :width="chartWidth" :height="chartHeight" id="rect">
        <g
          v-for="(value, idx) in chartData"
          :transform="`translate(0, ${idx * 40})`">
          <rect height="30" :width="barWidth(value)" fill="orange"></rect>
          <text y="15">{{ value }}</text>
        </g>
    </svg>
  </div>
</template>

<script>
export default {
  name: 'chart',
  data () {
    return {
      chartWidth: 500,
      chartHeight: 400,
      chartData: [5, 8, 20, 25, 3, 17, 14]
    }
  },
  methods: {
    barWidth(value) {
      return this.chartWidth / this.dataMax * value;
    }
  },
  computed: {
    dataMax() {
      return Math.max(...this.chartData);
    }
  }
}
</script>

<style>
#chart {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#rect {
}
</style>
