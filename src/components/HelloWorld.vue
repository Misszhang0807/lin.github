<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>
      <el-button>同意</el-button>
      <div
        :style="[{ top: Ptop + 'px' }, { left: Pleft + 'px' }]"
        class="noAgree"
        @mouseenter="Enter(1)"
      >
        {{ title }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "老板，世界那么大，我想去看看",
      Ptop: 0,
      Pleft: 0,
      title: "不同意",
    };
  },
  methods: {
    Enter(type) {
      let num = Math.floor(Math.random() * 600 + 50);
      let num1 = Math.floor(Math.random() * 1000 + 50);
      this.Ptop = num;
      this.Pleft = num1;
      this.title = "哎，你点不着！哎，你气不气！！";
      console.log(num);
    },
  },
};
</script>

<style scoped lang='scss'>
h1 {
  font-weight: normal;
}
.noAgree {
  border: 1px solid #666;
  width: 300px;
  text-align: center;
  line-height: 40px;
  // margin: 20px auto;
  position: absolute;
  top: 0;
  cursor: pointer;
}
.activeClass {
  top: 20px;
  left: 40px;
}
</style>
