<template>
  <div class="home">
      <router-link to="/">Home</router-link>
    <h1>La partie Admin</h1>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';

export default {
  name: 'home',
  components: {
    HelloWorld,
  },
};
</script>
