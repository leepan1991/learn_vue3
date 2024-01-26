<template>
  <div class="person">
    <h2>名字：{{ person.name }}</h2>
    <h2>年龄：{{ person.age }} {{nl}}</h2>
    <button @click="changeName">修改名称</button>
    <button @click="changeAge">修改年龄</button>
  </div>

</template>

<script lang="ts" setup name="Person">
//引入reactive创建对象类型的响应数据
import {reactive, toRef, toRefs} from "vue";

let person = reactive({
  name: '张三',
  age: 18
})

let {name, age} = toRefs(person)

let nl = toRef(person, 'age')

function changeName() {
  name.value += '#'
}

function changeAge() {
  age.value += 1
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