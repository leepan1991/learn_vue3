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
import {ref, watch} from "vue";

//数据
let person = ref({
  name: '张三',
  age: 18
})

//方法
function changeName() {
  person.value.name += '~'
}

function changeAge() {
  person.value.age += 1
}

function changePerson() {
  person.value = {name: '李四', age: 90}
}

/*监视，情况一：监视【ref】定义的【对象类型】数据，若想监视对象内部属性变化，需要手动开启
watch的第一个参数是：被监视的数据
watch的第二个参数是：被监视的回调
watch的第三个参数是：配置对象（deep，immediate）*/
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