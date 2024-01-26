<template>
  <div class="person">
    <h2>一辆汽车{{ car.brand }}车，价值{{ car.price }}万</h2>
    <button @click="changePrice">修改骑车的价格</button>
    <h2>游戏列表：</h2>
    <ul>
      <li v-for="g in games" :key="g.id">{{g.name}}</li>
    </ul>
    <button @click="changeFirstName">修改第一个游戏名称</button>
  </div>

</template>

<script lang="ts" setup name="Person">
//引入reactive创建对象类型的响应数据
import {reactive} from "vue";

let car = reactive({brand: "奔驰", price: 100})

let games = reactive([
  {id: 'g1', name: "王者荣耀1"},
  {id: 'g2', name: "王者荣耀2"},
  {id: 'g3', name: "王者荣耀3"}
])

function changePrice() {
  car.price += 10
}

function changeFirstName() {
  games[0].name='元生鲜'
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