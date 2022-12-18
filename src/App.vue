<script>
export default{
  data(){
    return {
      activeColor: 'red',
      fontSize: '50px',
      bcgColor: 'pink',
      stlyeObj: {
        color: 'red',
        fontSize: '100px',
        'background-color': 'pink'
      }
    };
  },
  computed:{
  }
};
</script>

<!-- 绑定内联样式 -->
<template>
  <div>
    <!-- 第一种：放置字符串，传统方式 -->
    <p style="color: red">字符串</p>
    <!-- 第二种：绑定对象 css属性名可以使用驼峰或-方式，后者需要加''引号，属性值可以用data中的变量-->
    <p :style="{color: activeColor, fontSize:fontSize, 'background-color':bcgColor}">绑定对象</p>
    <!-- 第三种：绑定对象 -->
    <p :style="stlyeObj">绑定对象</p>
    <!-- 第四种：绑定数组 -->
    <p :style="stlyeObj">绑定对象</p>
  </div>
</template>

<style>
</style>
