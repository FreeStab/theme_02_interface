<template>
  <div v-if="workingTimeInfos != null" class="working-time">
    <span class="working-time--status"></span>
    <span>{{ workingTimeInfos.user.username }}</span>
  </div>
  <div v-else class="working-time add" :class="{active: active}">
    <span class="cross--button" @click="setActive()">+</span>
    <input v-model="username" type="text" name="user" id="user" placeholder="Username" />
    <input v-model="email" type="email" name="email" id="email" placeholder="Email" />
    <span class="add--button">Add</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      active: false,
      username: "",
      email: ""
    };
  },
  props: {
    workingTimeInfos: {
      type: Object
    }
  },
  methods: {
    createWorkingTime() {},
    updateWorkingTime() {},
    deleteWorkingTime() {},
    setActive() {
      this.active = !this.active;
    }
  }
};
</script>

<style lang="scss" scoped>
$add-size: 1.5rem;
.working-time {
  //cursor: pointer;
  width: 90%;
  height: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0.3rem;

  & + .working-time {
    border-top: 1px solid grey;
  }
  &.add {
    height: unset;
    flex-direction: column;
    position: relative;
    .cross--button {
      cursor: pointer;
      position: absolute;
      font-size: $add-size;
      height: $add-size;
      width: $add-size;
      line-height: $add-size;
      padding: 0.2rem;
      border: 1px solid black;
      border-radius: 50%;
      z-index: 2;
      transition: right 500ms, transform 500ms;
      right: calc(50% - 0.5rem);
      transform: rotate(0deg);
    }
    .add--button {
      cursor: pointer;
      padding: 0.2rem 0.5rem;
      position: relative;
      &:before,
      &:after {
        content: "";
        position: absolute;
        width: 100%;
        height: 100%;
        transform: scaleX(0) scaleY(0);
        transition: transform 500ms;
      }
      &:before {
        border-bottom: 1px solid black;
        border-left: 1px solid black;
        transform-origin: bottom left;
        left: 0;
        top: 0;
      }
      &:after {
        border-top: 1px solid black;
        border-right: 1px solid black;
        transform-origin: top right;
        right: 0;
        top: 0;
      }
    }
    input,
    .add--button {
      opacity: 0;
      transition: opacity 500ms;
      margin: 0.2rem;
    }
  }
  &.active {
    .add--button,
    input {
      opacity: 1;
    }
    .add--button {
      &,
      input {
        opacity: 1;
      }
      &:hover {
        &:before,
        &:after {
          transform: scaleX(.97) scaleY(.97);
        }
      }
      &:before,
      &:after {
        transform: scaleX(0.5) scaleY(0.5);
      }
    }
    .cross--button {
      right: 0;
      transform: rotate(315deg);
    }
  }
}
</style>