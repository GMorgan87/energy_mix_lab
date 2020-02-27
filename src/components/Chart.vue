<template lang="html">
  <div>
    <p>{{this.chartOptions.title}}</p>
    <p>Showing Data from {{chartTimes.start}} to {{chartTimes.end}}</p>
    <GChart  class="chart"
    :type="chartType"
    :data="generationMix"
    :options="chartOptions"
    />
    <label for="type-select">Select Chart Type</label>
    <select class="type-select" name="type-select" v-model="chartType">
      <option value="PieChart">Pie Chart</option>
      <option value="BarChart">Bar Chart</option>
      <option value="ColumnChart">Column Chart</option>
    </select>
  </div>

</template>

<script>
import {GChart} from "vue-google-charts";
export default {
  components: {
    GChart
  },
  props: ['generationMix', 'chartTimes'],
  data(){
    return {
      chartOptions: {
         title: 'Energy Generation Chart',
         is3D: 'true',
      },
      chartType: 'PieChart'
    }
  }
}
</script>

<style lang="css" scoped>
rect {
  height: 500px;
}

.chart {
  width: 900px;
  height: 500px;
}

</style>
