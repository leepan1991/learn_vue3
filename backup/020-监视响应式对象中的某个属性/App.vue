<template>
  <div class="app">
    <h1>监视，情况四：监视响应式对象中的某个属性</h1>
    <Person/>
  </div>
</template>
<script>
import Person from "@/components/Person.vue";

export default {
  name: 'App', //组件名
  components: {Person} //注册组件
}
</script>
<style>
.app {
  background-color: aliceblue;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}
</style>