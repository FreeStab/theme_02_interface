<template>
  <div class="user-sidebar">
    <h2 class="user__name" :class="{ connected: connected }">Bruce Wayne</h2>
    <h3 class="connect--button" @click="connected = !connected">
      <span v-if="connected">DISCONNECT</span>
      <span v-else>CONNECT</span>
    </h3>
  </div>
</template>

<script>
export default {
  data() {
    return {
      connected: true
    };
  },
  methods: {
    createUser() {},
    updateUser() {},
    getUser() {},
    deleteUser() {}
  }
};
</script>

<style lang="scss" scoped>
$light-size: 20px;

.user-sidebar {
  width: 90%;
  height: 60px;
  background-color: #404040;
  color: white;
  display: flex;
  padding: 1rem;
  justify-content: space-between;
  //flex-direction: column;

  align-items: center;
  border-bottom-right-radius: 20px;
  border-bottom-left-radius: 20px;

  .user__name {
    position: relative;
    width: min-content;
    height: min-content;
    &:after {
      position: absolute;
      content: "";
      width: $light-size;
      height: $light-size;
      border-radius: 50%;
      background-color: red;
      right: -$light-size * 1.5;
      bottom: 20%;
      box-shadow: 0px 0px 7px 0px #ffffff45;
      transition: background-color 300ms;
    }
  }
  .connected {
    &:after {
      background-color: rgb(53, 163, 10);
    }
  }
  .connect--button {
    cursor: pointer;
    border: 2px solid white;
    border-radius: 3px;
    box-shadow: 4px 4px white;
    padding: 0.2rem;
    transition: box-shadow 300ms, transform 300ms;
    &:hover {
      transform: translateX(4px) translateY(4px);
      box-shadow: 0px 0px white;
    }
  }
}
</style>