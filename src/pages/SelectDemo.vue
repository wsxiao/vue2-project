<template>
    <div id="app">
      <select name="fruit" v-model="selected">
        <option value="">选择一个网站</option>
        <option value="www.gxcards.com">gxcards</option>
        <option value="www.baidu.com">baidu</option>
        <option value="www.google.com">google</option>
      </select>
      <div>
        选择的网站是：{{selected}}
      </div>

    </div>
</template>

<script>
    export default {
        name: "select-demo",
        data(){
          return{
            selected:'',
          }
        }
    }
</script>

<style scoped>

</style>
