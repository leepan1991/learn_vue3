<template>
  <div class="person">
    <h2>姓名：{{ person.name }}</h2>
    <h2>年龄：{{ person.age }}</h2>
    <h2>汽车：{{ person.car.c1 }} {{ person.car.c2 }}</h2>
    <button @click="changeName">点我修改名字</button>
    <button @click="changeAge">点我修改年龄</button>
    <button @click="changeC1">点我修改C1</button>
    <button @click="changeC2">点我修改C2</button>
    <button @click="changeCar">点我修改Car</button>
  </div>

</template>

<script lang="ts" setup name="Person">
import {reactive, watch} from "vue";

//数据
let person = reactive({
  name: '张三',
  age: 18,
  car: {
    c1: '奔驰',
    c2: '宝马'
  }
})

//方法
function changeName() {
  person.name += '~'
}

function changeAge() {
  person.age += 1
}

function changeC1() {
  person.car.c1 = '奥迪'
}

function changeC2() {
  person.car.c2 = '大众'
}

function changeCar() {
  person.car = {c1: '雅迪', c2: '艾玛'}
}

function changePerson() {
  Object.assign(person, {name: '李四', age: 90})
}

/*监视，情况四：监视上述多个数据*/
watch([() => person.car.c1, () => person.name], (newValue, oldValue) => {
  console.log('数据变化了', newValue, oldValue)
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