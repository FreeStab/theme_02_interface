<template>
  <div class="home">
    <ChartManager></ChartManager>
    <WorkingTimes></WorkingTimes>
  </div>
</template>

<script>
// @ is an alias to /src
import ChartManager from "@/components/ChartManager.vue";
import WorkingTimes from "@/components/WorkingTimes.vue";

export default {
  name: "home",
  components: {
    ChartManager,
    WorkingTimes
  }
};
</script>

<style lang="scss" scoped>
.home {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  grid-gap: 20px;
}
.working-times {

}
</style>
