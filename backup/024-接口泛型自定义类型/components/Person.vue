<template>
  <div class="person">
    ???
  </div>

</template>

<script lang="ts" setup name="Person">
import {PersonInter, Persons} from "@/types/intex";

let person: PersonInter = {id: 'id01', name: "张三", age: 60}

let personList: Persons = [
  {id: 'id01', name: "张三", age: 60},
  {id: 'id02', name: "李四", age: 18},
  {id: 'id03', name: "王五", age: 66}
]

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