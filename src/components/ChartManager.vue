<template>
  <div class="chart-manager">
    <component :is="chartData.component" :data="chartData.data"></component>
  </div>
</template>

<script>
import PieChart from "@/components/Chart/PieChart.vue";
import DonutChart from '@/components/Chart/DonutChart.vue';
export default {
  props: {
    chartData: {
      type: Object,
      
    },
  },
  data() {
    return {
      chartData: [
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
    };
  },
  components: {
    PieChart,
    DonutChart
  }
};
</script>

<style lang="scss" scoped>
</style>
