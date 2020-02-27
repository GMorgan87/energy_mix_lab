<template lang="html">
  <div class="">
    <p>{{this.chartOptions.chart.title}}</p>
    <p>Showing Data from {{chartTimes.start}} to {{chartTimes.end}}</p>
    <GChart
    type="PieChart"
    :data="generationMix"
    :options="chartOptions"
    />
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
        chart: {
         title: 'Energy Generation Chart',
       }
      }
    }
  }
}
</script>

<style lang="css" scoped>
rect {
  height: 500px;
}

</style>
