<template >
  <div class="tyt">
    <input type="text" v-model="newPerson.name" placeholder="姓名" class="put">
    <input type="text" v-model="newPerson.age" placeholder="年龄" class="put" @keyup.enter="addPerson">
     <button @click="addPerson"> 添加</button>
    <button @click="delPerson">删除</button>
    <First v-for="(item,index) in persons" :age="item.age" :name="item.name" :key="index"/>
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
           age:''
         }
      }
    },
    methods: {
      addPerson(){
          this.persons.push({
            name: this.newPerson.name,
            age: this.newPerson.age
          })
      },
      delPerson(){
        this.persons.pop();
        
      }
    },
    components: {
      First
    }
}
</script>

<style lang="less">
.tyt{
  padding: 40px;
  background: pink;
  margin: 40 auto;
  .put {
    width: 50px;
    height: 25px;
    margin-right: 11px;
  }
}
</style>
