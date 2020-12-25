<template>
  <div class="center">
    <div @dragstart="handleDragStart" class="component-list">
      <div
        v-for="(item, index) in componentList"
        :key="index"
        class="list"
        draggable
        :data-index="index"
      >
        <i :class="item.icon"></i>
        <span>{{ item.label }}</span>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      componentList: [
        {
          component: "v-text", // 组件名称，需要提前注册到 Vue
          label: "文字", // 左侧组件列表中显示的名字
          propValue: "文字", // 组件所使用的值
          icon: "el-icon-edit", // 左侧组件列表中显示的名字
        },
        {
          component: "v-button", // 组件名称，需要提前注册到 Vue
          label: "btn", // 左侧组件列表中显示的名字
          propValue: "btn", // 组件所使用的值
          icon: "el-icon-thumb", // 左侧组件列表中显示的名字
        },
        {
          component: "v-img", // 组件名称，需要提前注册到 Vue
          label: "图片", // 左侧组件列表中显示的名字
          propValue: "图片", // 组件所使用的值
          icon: "el-icon-sugar", // 左侧组件列表中显示的名字
        },
      ],
    };
  },
  methods: {
    handleDragStart(e) {
      e.dataTransfer.setData("index", e.target.dataset.index);
    },
  },
};
</script>

<style lang="scss" scoped>
.center {
  border: 1px solid #bbb;
  width: 20%;
  height: 500px;
  text-align: center;
  .component-list {
    margin-top: 20px;
    display: flex;
    justify-content: space-around;
  }
}
</style>