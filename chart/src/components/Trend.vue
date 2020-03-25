<template>
  <canvas ref="line-chart"></canvas>
</template>

<script>
// import { Line } from 'vue-chartjs'

// export default {
//   props: ['data', 'options'],
//   mixins: [Line],
//   mounted () {
//     this.renderChart(this.data, this.options)
//   },
//   watch: {
//     data () {
//       this.renderChart(this.data, this.options)
//     }
//   }
// }

import Chart from 'chart.js'

export default {
  props: ['data', 'options'],
  mounted () {
    const ctx = this.$refs['line-chart'];
    new Chart(ctx, {
      type: 'line',
      data: this.data,
      options: this.options,
    });
  },
  watch: {
    data () {
      const ctx = this.$refs['line-chart'];
      new Chart(ctx, {
        type: 'line',
        data: this.data,
        options: this.options,
      });
    }
  }
}


</script>

<style>
</style>
