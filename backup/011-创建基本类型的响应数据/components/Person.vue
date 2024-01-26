<template>
  <div class="person">
    <h2>姓名：{{ name }}</h2>
    <h2>年龄：{{ age }}</h2>
    <button @click="changeName">修改名称</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">查看联系方式</button>
  </div>

</template>

<script lang="ts" setup name="Person">
//引入ref创建基本类型的响应数据
import {ref} from "vue";
//数据,原来都是写在data中的，此时的name，age，tel都不是响应式的数据
let name = ref('张三')
let age = ref(18)
let tel = '135225522'

//方法
function changeName() {
  name.value = 'zhang.san' //注意：这样修改name，页面是没有变化的
  console.log(name.value)//name确实修改了，但name不是响应式的
}

function changeAge() {
  age.value += 1 //注意：这样修改age，页面是没有变化的
  console.log(age.value) //age确实修改了，但age不是响应式的
}

function showTel() {
  alert(tel)

}
</script>

<style scoped>
.person {
  background-color: #2c3e50;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}

button {
  margin: 5px;
}
</style>