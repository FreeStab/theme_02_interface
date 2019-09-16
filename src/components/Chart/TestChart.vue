<template>
  <div>
    <!--<bar-chart 
                id="bar"
                :data="barData"
                xkey="year"
                ykeys='[ "and", "ios", "win" ]'
                resize="true"
                labels='[ "Android", "iOS", "Windows" ]'
                bar-colorssss='[ "#FF6384", "#36A2EB", "#FFCE56" ]'
                :bar-colors="osColors"
                grid="true" 
                grid-text-weight="bold">
              </bar-chart>
-->
  </div>
</template>

<script>
import Raphael from "raphael/raphael";
global.Raphael = Raphael;
import { DonutChart, BarChart  } from "vue-morris";
export default {
  name: "app",
  data() {
    return {
      donutData: [
        { label: "Red", value: 300 },
        { label: "Blue", value: 50 },
        { label: "Yellow", value: 100 }
      ],
      barData: [
        { year: "2013", and: 10, ios: 5, win: 2 },
        { year: "2014", and: 10, ios: 15, win: 3 },
        { year: "2015", and: 20, ios: 25, win: 2 },
        { year: "2016", and: 30, ios: 20, win: 1 }
      ]
    };
  },
  components: {
    DonutChart,
    BarChart
  }
};
</script>