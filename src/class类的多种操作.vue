<script>
export default{
  data(){
    return {
      message: "helloWorld",
      isActive: true,
      error:null,
      classObj:{
        active:true,
        helloWorld:true
      }
    };
  },
  computed:{
    classObjCom(){
      return{
        active: this.isActive && !this.error,
        helloWorld: this.error
      };
    }
  }
};
</script>

<template>
  <div>
    <!-- 第一种：放置字符串，class="类名"，类定义于style标签中 -->
    <p class="active">hello</p>
    <!-- 第二种：绑定对象，v-bind:class="{类名：布尔值}" -->
    <p v-bind:class="{active:isActive}">hello绑定对象</p>
    <p :class="{active:isActive,helloWorld:isActive}">hello绑定对象</p>
    <button v-on:click="isActive=!isActive">改变isactive</button>
    <!-- 和普通类一起不会被覆盖，而是合并叠加 -->
    <p v-bind:class="{active:isActive}" class="helloWorld">hello绑定对象</p>
    <!-- 第三种：绑定class对象，仅v-bind方式可以让class绑定对象" -->
    <p :class="classObj">hello</p>
    <!-- 第四种：使用computed -->
    <p :class="classObjCom">helloComputed</p>
     <!-- 第五种：绑定数组，不常用 -->
     <p :class="[message]">hello数组</p>
     <!-- 数组与对象结合使用 -->
     <p :class="[message,{active: isActive}]">数组与对象</p>
  </div>
</template>

<style>
.active{
  font-size: 50px;
  color: blue;
}
.helloWorld{
  background-color: pink;
}
</style>
