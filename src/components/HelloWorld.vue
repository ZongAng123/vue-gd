<template>
  <!-- <div class="hellow"> -->
    <div class="wrapper_box" ref="wrapper">
      <div class="content" ref="wrapperChild">
        <div class="imgItem">
          <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
          <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
          <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
          <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
          <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
          <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
          <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
          <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
          <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
          <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
          <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
      </div>
    </div>
  <!-- </div> -->
</template>

<script>
import BScroll from 'better-scroll'

export default {
  name: 'HelloWorld',
  data() {
    return {
      currentImgList: [
        { img: require("../assets/logo.png") },
        { img: require("../assets/logo.png") },
        { img: require("../assets/logo.png") }
      ],
    }
  },
  methods: {
    // 初始化
    _initScroll() {
      if (!this.scroll) {
        this.scroll = new BScroll(this.$refs.wrapper, { // 实例化BScroll接受两个参数，第一个为父盒子的dom节点
          startX: 0, /// 配置的详细信息请参考better-scroll的官方文档，这里不再赘述
          click: true,
          scrollX: true,
          scrollY: false, // 忽略竖直方向的滚动
          eventPassthrough: "vertical",
          useTransition: false // 防止快速滑动触发的异常回弹
        });
      } else {
        this.scroll.refresh(); //如果dom结构发生改变调用该方法重新计算来确保滚动效果的正常
      }
    },
    // 计算宽度
    // _calculateWidth() {
    //   // 获取类名为 imgItem 的标签
    //   let rampageList = this.$refs.wrapperChild.getElementsByClassName(
    //     "imgItem"
    //   );
    //   // 设置一个起始宽度
    //   let initWidth = 0;
    //   // 遍历标签
    //   for (let i = 0; i < rampageList.length; i++) {
    //     const item = rampageList[i];
    //     // 将每一个标签宽度相加
    //     initWidth += item.clientWidth;
    //   }
    //   // 设置可滚动的宽度
    //   this.$refs.wrapperChild.style.width = `${initWidth}px`;
    // },
    slide_x() {
      this.$nextTick(() => { //this.$nextTick 是一个异步函数，为了确保 DOM 已经渲染完毕
        this._initScroll(); // 初始化
        // this._calculateWidth(); // 计算宽度
      });
    },

  },
  mounted() {
    this.slide_x(); //横向滚动
  },
  beforeDestroy() {

  },
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hellow{
  background-color: rgb(93, 30, 151);
  height: 200px;
  width: 80%;
}
.wrapper_box{
  background-color: blue;
  width: 100%;
}
.content{
  background-color: aquamarine;
  height: 100px;
  display: flex;
  margin-right: 3ch;
  width: 100%;
}
.imgItem{
  background-color: rgb(74, 11, 31);
  margin-left: 1em;
}
.img{
  height: 100px;
  width: 100px;
}
</style>
