<template>
  <div class="class-object-content">
    <div v-bind:class="classObject"></div>
  </div>
</template>

<script>
    export default {
        name: "class-object",
      data(){
          return{
            isActive:true,
            error:{
              value:true,
              type:'fatal'
            }
          }
      },
      computed:{
        classObject:function () {
          return{
            base:true,
            active:this.isActive && !this.error.value,
            'text-danger':this.error.value && this.error.type === 'fatal',
          }
        }
      }
    }
</script>

<!--<style scoped>-->
  <!--.base{-->
    <!--width: 100px;-->
    <!--height: 100px;-->
  <!--}-->

  <!--.active{-->
    <!--background: green;-->
  <!--}-->

  <!--.text-danger{-->
    <!--background: red;-->
  <!--}-->
<!--</style>-->
<style scoped lang="less" src="../assets/less/classObject.less"></style>
