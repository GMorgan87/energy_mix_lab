<template>
  <div id="app">
    <button @click="formatData()">Get Data</button>
    <chart :generationMix="generationMix"></chart>
  </div>
</template>

<script>
import Chart from './components/Chart.vue'

export default {
  name: 'App',
  components: {
    'chart': Chart
  },
  data(){
    return{
      generationMix: [["fuel", "Percentage"]]
    }
  },
  mounted(){
    fetch('https://api.carbonintensity.org.uk/generation')
    .then(res => res.json())
    .then(data => {
      this.formatData(data.data.generationmix)
      console.log(this.generationMix);
    })
  },
  methods: {
    formatData: function(energyData){
      for (let energy of energyData) {
        let energyArray = []
        energyArray.push(energy.fuel);
        energyArray.push(energy.perc)
        this.generationMix.push(energyArray);
      }

      }
    }
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
