<template >
  <div>
    <First v-for="(item,index) in persons" :age="item.age" :name="item.name" :key="index"/>
    <input type="text" v-model="newPerson.name">
    <input type="text" v-model="newPerson.age">
    <button @click="addPerson"> 添加</button>
    <button @click="delPerson">删除</button>
  </div>
</template>

<script>
import First from "./components/First"
export default {
     data: function (){
       return {
         persons: [
            {name:'小花',age:'21'},
            {name:'小狼',age:'23'},
            {name:'小红',age:'19'},
         ],
         newPerson:{
           name: '',
           age:0
         }
      }
    },
    methods: {
      addPerson(){
          this.persons.push(this.newPerson)
      },
      delPerson(){
        this.persons.pop()
      }
    },
    components: {
      First
    }
}
</script>

<style>

</style>
