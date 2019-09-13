<template>
  <div class="working-times">
    <WorkingTime></WorkingTime>
    <h3>Clocked :</h3>
    <WorkingTime 
    v-for="workingTime in workingTimes" 
    :key="workingTime.id"
    :workingTimeInfos='workingTime'></WorkingTime>
  </div>
</template>

<script>
import moment from "moment";
import WorkingTime from "@/components/WorkingTime.vue";
export default {
  components: {
    WorkingTime
  },
  data() {
    return {
      userId: "",
      workingTimes: [
        {
          user: {
            username: "Pablo Escobar",
            email: "Pablo@cartel.com"
          },
          start: moment("20111031").format("YYYY-MM-DD hh:mm:ss"),
          end: moment("20111101").format("YYYY-MM-DD hh:mm:ss")
        },
        {
          user: {
            username: "Didier Deschamps",
            email: "didi@fifa.com"
          },
          start: moment("20190831").format("YYYY-MM-DD hh:mm:ss"),
          end: moment("20190910").format("YYYY-MM-DD hh:mm:ss")
        },
        {
          user: {
            username: "Jean-Luc Hassaique",
            email: "jlh@gmail.com"
          },
          start: moment("20111031").format("YYYY-MM-DD hh:mm:ss"),
          end: moment("20111102").format("YYYY-MM-DD hh:mm:ss")
        },
        {
          user: {
            username: "Maria Stark",
            email: "maria.stark@msn.com"
          },
          start: moment("20131031").format("YYYY-MM-DD hh:mm:ss"),
          end: moment("20131102").format("YYYY-MM-DD hh:mm:ss")
        }
      ]
    };
  },
  methods: {
    getWorkingTimes() {}
  }
};
</script>

<style lang="scss" scoped>
.working-times {
  width: 100%;
  height: 100%;
  //background-color: red;
  grid-row: span 2;
  border-left: 1px solid #d4d4d470;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  flex-direction: column;
}
h3 {
  margin:.2rem;
}
</style>