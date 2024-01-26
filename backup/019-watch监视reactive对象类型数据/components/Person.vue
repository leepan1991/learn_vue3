<template>
  <div class="person">
    <h2>姓名：{{ person.name }}</h2>
    <h2>年龄：{{ person.age }}</h2>
    <button @click="changeName">点我修改名字</button>
    <button @click="changeAge">点我修改年龄</button>
    <button @click="changePerson">点我修改人</button>
  </div>

</template>

<script lang="ts" setup name="Person">
import {reactive, watch} from "vue";

//数据
let person = reactive({
  name: '张三',
  age: 18
})

//方法
function changeName() {
  person.name += '~'
}

function changeAge() {
  person.age += 1
}

function changePerson() {
  Object.assign(person, {name: '李四', age: 90})
}

/*监视，情况一：监视【reactive】定义的【对象类型】数据，且默认是开启深度监视的*/
watch(person, (newValue, oldValue) => {
  console.log('Person变化了', newValue, oldValue)
}, {deep: true})


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