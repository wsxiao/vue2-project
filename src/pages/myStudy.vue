<template>
  <div>
    <table>
      <tr>
        <th>序号</th>
        <th>商品名称</th>
        <th>商品价格</th>
        <th>购买数量</th>
        <th>操作</th>
      </tr>
      <tr v-for="iphone in IP_Json">
        <td>{{iphone.id}}</td>
        <td>{{iphone.name}}</td>
        <td>{{iphone.price}}</td>
        <td>
          <button :disabled="iphone.count === 0" @click="iphone.count -= 1">-</button>
          {{iphone.count}}
          <button @click="iphone.count += 1">+</button>
        </td>
        <td>
          <button @click="iphone.count = 0">移除</button>
        </td>
      </tr>
    </table>
    总价：¥{{totalPrice()}}
    <button @click="classObject">classObject</button>
    <button @click="formDemoFunc">表单Demo</button>
    <button @click="eventProcessor">事件处理器</button>
    <button @click="styleClick">Vue.js style（内联样式）</button>
    <button @click="checkedBox">复选框</button>
    <button @click="RadioBox">单选框</button>
    <button @click="selectDemo">列表选择</button>
    <button @click="componentDemo">组件Demo</button>
    <button @click="customInstructions">自定义指令</button>
  </div>
</template>

<script>
    export default {
        name: "my-study",
      data(){
          return{
            IP_Json:[
              {
                id:1,
                name:'iphone 8',
                price:5099,
                count:1,
              },
              {
                id:2,
                name:'iphone xs',
                price:10299,
                count:1,
              },
              {
                id:1,
                name:'iphone xr',
                price:6099,
                count:1,
              },
              {
                id:1,
                name:'iphone 8P',
                price:5599,
                count:1,
              },
            ]
          }
      },
      methods:{
          totalPrice:function () {
            var totalP = 0;
            for(var i = 0,len = this.IP_Json.length;i < len;i++){
              totalP += this.IP_Json[i].price * this.IP_Json[i].count;
            }
            return totalP;
          },
        classObject:function () {
          this.$router.push({
            name:'classObject'
          })
        },
        formDemoFunc:function () {
          this.$router.push({
            name:'formDemo'
          })
        },
        eventProcessor:function () {
          this.$router.push({
            name:'eventProcessor'
          })
        },
        styleClick:function () {
          this.$router.push({
            name:'styleDemo'
          })
        },
        checkedBox:function () {
          this.$router.push({
            name:'checkedBoxDemo'
          })
        },
        RadioBox:function () {
          this.$router.push({
            name:'radioBox'
          })
        },
        selectDemo:function () {
          this.$router.push({
            name:'selectDemo',
          })
        },
        componentDemo:function () {
          this.$router.push({
            name:'componentDemo'
          })
        },
        customInstructions:function () {
          this.$router.push({
            name:'customInstructions'
          })
        }
      }
    }
</script>

<style scoped>
  table{
    border: 1px solid black;
  }
  table{
    width: 100%;
  }
  th{
    height: 50px;
  }
  th,td{
    border-bottom: 1px solid #ddd;
  }
</style>
