<template>
  <div class="home">
    <h1 style="color:red">请看这<br>{{day}}</h1>
    <h1>现在时间：{{date}}</h1>
    <router-link to="/login">前往登录界面</router-link>
  </div>
</template>

<script>
/**
 * Home页面书写
 * 作者：曹显禾
 * 联系方式：502623564@qq.com
 * 时间：2021/1/20
 * 描述：没有...............
 * */


export default {
  name: 'Home',
  data(){
    return{
      day:"傻妞请开始写登录界面",
      date:new Date()
    }
  },
  methods:{
    changedate(){
      this.timer = setInterval(()=>{
        this.date=new Date()
      },1000) //定时函数
    },
    clearTimer(){

    }
  },
  mounted() {
     let _this = this; // 声明一个变量指向Vue实例this，保证作用域一致
    _this.changedate()
  },
  destroyed() {
     if (this.timer) {
       alert("定时函数销毁")
      clearInterval(this.timer); // 在Vue实例销毁时，清除我们的定时器
    }
  }

}
</script>
<style scoped>
  .home{
    width: 500px;
    margin: 0 auto;
  }

</style>
