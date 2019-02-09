<template>
  <div>
    //复选框如果是一个为逻辑值，如果是多个则绑定到同一个数组：
    <p>单个复选框：</p>
    <input type="checkbox" id="checkbox" v-model="checked"/>
    <label for="checkbox">{{checked}}</label>

    <p>多个复选框</p>
    <input type="checkbox" id="runoob" value="Runoob" v-model="checkedNames">
    <label for="runoob">Runoob</label>
    <input type="checkbox" id="google" value="Google" v-model="checkedNames">
    <label for="google">Google</label>
    <input type="checkbox" id="baidu" value="Baidu" v-model="checkedNames">
    <label for="baidu">Baidu</label>
    <br>
    <span>选择的值为：{{checkedNames}}</span>
  </div>

</template>

<script>
    export default {
        name: "checked-box-demo",
        data(){
          return{
            checked:false,
            checkedNames:[],
          }
        }
    }
</script>

<style scoped>

</style>
