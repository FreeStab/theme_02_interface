<template>
  <div class="home">
    <ChartManager v-for="chart in chartDatas" :key="chart.key" :chartData="chart"></ChartManager>
    <TestChart></TestChart>
    <WorkingTimes></WorkingTimes>
  </div>
</template>

<script>
// @ is an alias to /src
import ChartManager from "@/components/ChartManager.vue";
import WorkingTimes from "@/components/WorkingTimes.vue";
import PieChart from "@/components/Chart/PieChart.vue";
import DonutChart from '@/components/Chart/DonutChart.vue';
import TestChart from '@/components/Chart/TestChart.vue';


export default {
  name: "home",
  components: {
    ChartManager,
    WorkingTimes,
    TestChart
  },
  data() {
    return {
      chartDatas: [
        {
          component: PieChart,
          data: [
            { color: "#FDD835", value: 21, label: "Lundi" },
            { color: "#536DFE", value: 34, label: "Mardi" },
            { color: "#D50000", value: 22, label: "Mercredi" },
            { color: "orangered", value: 12, label: "Jeudi" },
            { color: "navy", value: 11, label: "Vendredi" }
          ]
        },
        {
          component: DonutChart,
          data: [
            { color: "#FDD835", value: 21, label: "Lundi" },
            { color: "#536DFE", value: 34, label: "Mardi" },
            { color: "#D50000", value: 22, label: "Mercredi" },
            { color: "orangered", value: 12, label: "Jeudi" },
            { color: "navy", value: 11, label: "Vendredi" }
          ]
        }
      ]
    }
  },
};
</script>

<style lang="scss" scoped>
.home {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  grid-template-rows: 1fr 1fr;
  grid-gap: 20px;
  grid-auto-flow: dense;
      align-items: center;
    justify-items: center;

}
.working-times {

}
</style>
