<template>
  <div class="content">
    <left></left>
    <div class="center">
      <component
        v-for="item in componentData"
        :key="item.id"
        :is="item.component"
        :style="item.style"
        :propValue="item.propValue"
      />
    </div>
    <right></right>
  </div>
</template>

<script>
import left from "./left";
import right from "./right";
export default {
  data() {
    return {
      componentData: [],
    };
  },
  components: {
    left,
    right,
  },
};
</script>

<style lang="scss" scoped>
.content {
  display: flex;
  justify-content: space-around;
  .center {
    border: 1px solid #bbb;
    width: 30%;
    height: 500px;
    text-align: center;
  }
}
</style>