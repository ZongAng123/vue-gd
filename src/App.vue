<template>
  <div id="app">
    <GunDong v-if="seen" class="hhhhhh"/>
    <p>单画面</p>
    <el-switch active-color="#13ce66"
    inactive-color="#ff4949" class="switch-vb" v-model="danduohua" @change="turnOnOff()">
    </el-switch>
    <p>多画面</p>
    <div v-if="dhm" class="jkl-jk"></div>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import GunDong from './components/GunDong.vue'

export default {
  name: 'App',
  data() {
    return {
      danduohua: true,
      dhm:false,
      seen: true
    }
  },
  created() {
   
  },
  methods: {
    turnOnOff() {
      if (this.danduohua == true) {
        console.log('单画面');
        this.seen = true;
        this.dhm = false;
      } else {
        console.log('多画面');
        this.seen = false;
        this.dhm = true;
      }
    },
  },
  components: {
    GunDong
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
.hhhhhh{
  margin-top: 8em;
  width: 90ex;
}
.jkl-jk{
  background-color: bisque;
  margin-top: 10em;
  height: 300px;
  width: 90ex;
}
/*讲switch开关旋转立起来*/
.switch-vb{
  transform: rotate(90deg);
  -o-transform: rotate(90deg);
  -webkit-transform: rotate(90deg);
  -moz-transform: rotate(90deg);
}
</style>
