<template>
  <div class="piechart-layout">
    <svg viewBox="0 0 20 20">
      <circle cx="10" cy="10" r="10" />
      <circle
        v-for="(item, key) in data"
        :data-key="key"
        :data-is="percentList[key]"
        :key="item.id"
        cx="10"
        cy="10"
        r="5"
        :stroke="item.color"
        :stroke-width="10"
        fill="none"
        :stroke-dasharray="calcPercent(item.value)"
        :stroke-dashoffset="calcOffset(percentList[key])"
      />
    </svg>
    <div class="label-list">
      <div class="list-item__label" v-for="(item, key) in data" :key="key">
        <span class="label__color" :style="`background-color: ${item.color}`"></span>
        <p>{{ item.label }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Array
    }
  },
  methods: {
    calcPercent(percent) {
      let value = (percent * 31.42) / 100;
      return `${value} 31.42`;
    },
    calcOffset(percent) {
      let value = (-percent * 31.42) / 100;
      return `${value}`;
    }
  },
  computed: {
    percentList() {
      var percentList = this.data;
      var tempData = 0;

      return percentList.map((index, key) => {
        if (key != 0) tempData += percentList[key - 1].value;
        return tempData;
      });
    }
  }
};
</script>

<style lang="scss" scoped>
.piechart-layout {
    display: flex;
}
svg {
    width: 150px;
    margin: 0 1rem;
}

.label-list {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
}

.list-item__label {
  display: flex;
  justify-content: center;
  align-items: center;
}
.label__color {
  cursor: not-allowed;
  display: block;
  margin: 0 .2rem;
  height: 20px;
  width: 20px;
  border:1px solid black;
  border-radius: 3px;
}
</style>