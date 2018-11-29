<template>
  <div id="chart">
    <svg xmlns="http://www.w3.org/2000/svg" 
        width="500" height="400" id="rect">
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
      chartData: [5, 8, 20, 3, 17, 14]
    }
  },
  methods: {
    barWidth(value) {
      return 500 / 20 * value;
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
