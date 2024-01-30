<template>
  <div class="person">
    <ul>
      <li v-for="p in list" :key="p.id">
        {{ p.name }} -- {{ p.age }}
      </li>
    </ul>
  </div>

</template>

<script lang="ts" setup name="Person">
import {withDefaults} from "vue";
import {Persons} from "@/types/intex";

// //只接收list
// defineProps(['list'])
//
// //接收list+限制类型
// defineProps<{list:Persons}>()

//接收list+限制类型+限制必要性+指定默认值
withDefaults(defineProps<{list?:Persons}>(),{
  list:()=> [{id:'id04',name:'六子',age:9}]
})

// //接收list，同时将props保存起来
// let x = defineProps(['list'])
// console.log(x.list)

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