<template>
  <div class="tab-control">
    <div v-for="(item, index) in titles"
         class="tab-control-item" :class="{active: index === currentIndex}" @click="itemClick(index)">
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>
  export default {
    name: "TabControl",
    props: {
      titles: {
        type: Array,
        default() {
          return []
        }
      }
    },
    data() {
      return {
        currentIndex: 0
      }
    },
    methods: {
      itemClick(index) {
        this.currentIndex = index
        this.$emit('tabClick', index)
      }
    }
  }
</script>

<style scoped>
  .tab-control {
    display: flex;
    height: 40px;
    text-align: center;
    line-height: 40px;
    font-size: 15px;
    z-index: 9;
  }

  .tab-control-item {
    flex: 1;
  }
  .active {
    color: var(--color-high-text);

  }
  .active span {
    border-bottom: 3px solid var(--color-tint);
    padding: 5px;
  }
</style>
