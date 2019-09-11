<template>
  <div>

  </div>
</template>

<script>
  export default {
    data() {
      return {
        startDateTime: null,
        clockIn: false
      }
    },
    methods: {
      refresh() {
        
      },
      clock() {
       clockIn = !clockIn; 
      }
    },
  }
</script>

<style lang="scss" scoped>

</style>