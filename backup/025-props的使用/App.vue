<template>
  <div class="app">
    <Person a="哈哈"/>
  </div>
</template>
<script lang="ts" setup name="App">
import Person from "@/components/Person.vue";
import {reactive} from "vue";
import {Persons} from "@/types/intex";

let x = 9

let personList = reactive<Persons>([
  {id: 'id01', name: "张三", age: 60},
  {id: 'id02', name: "李四", age: 18},
  {id: 'id03', name: "王五", age: 66}
])
</script>
<style>
.app {
  background-color: aliceblue;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}
</style>