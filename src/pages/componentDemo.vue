<template>
    <div>
      <input v-model="parentMsg">
      <br>
      <v-customComponent :message="parentMsg"></v-customComponent>
      <br>
      <br>
      <ol>
        <todo-item v-for="item in sites" :todo="item"></todo-item>
      </ol>

      <div>
        <p>{{total}}</p>
        <button-counter v-on:increment="incrementTotal"></button-counter>
        <button-counter v-on:increment="incrementTotal"></button-counter>
      </div>
    </div>
</template>

<script>
   import customComponent from '../components/customComponent'
   import todoItem from '../components/todoItem'
   import customEvent from '../components/customEvent'

    export default {
        name: "component-demo",
        components:{
          'v-customComponent':customComponent,
          'todo-item':todoItem,
          'button-counter':customEvent,
        },
       data(){
          return{
            parentMsg:'父组件内容',
            sites:[
              {text:'Runoob'},
              {text:'Google'},
              {text:'Taobao'}
            ],
            total:0,
          }
       },
      methods:{
        incrementTotal:function () {
          this.total += 1;
        }
      }
    }
</script>

<style scoped>

</style>
