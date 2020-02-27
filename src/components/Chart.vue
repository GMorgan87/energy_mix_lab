<template lang="html">
  <div class="">
    <!-- <p>{{generationMix}}</p> -->
    <GChart
    type="PieChart"
    :data="generationMix"
    />
  </div>

</template>

<script>
import {GChart} from "vue-google-charts";
export default {
  components: {
    GChart
  },
  props: ['generationMix'],
  data(){
    return {
      "dummyData": [['fuel', 'percentage'], ['biomass', 45], ['coal', 55]]
    }
  }
}
</script>

<style lang="css" scoped>
</style>
