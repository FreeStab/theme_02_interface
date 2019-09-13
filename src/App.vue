/* eslint-disable */
<template>
  <div id="app">
    <User></User>
    <router-view class="content"/>
  </div>
</template>

<script>
import User from '@/components/User.vue'
export default {
  components: {
    User
  },
}
</script>

<style lang="scss">
body {
  margin: 0;
  padding: 0;
}
.content {
  width: 100%;
  height: 100%;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
