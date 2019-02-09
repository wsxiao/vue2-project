<template>
  <div>
    <p>页面载入时，input元素自动获取焦点：</p>
    <input v-focus>
    <div v-runoob:hello.a.b="message"></div>
  </div>
</template>

<script>
    export default {
        name: "custom-instructions",
        data(){
          return{
            message:'菜鸟教程'
          }
        },
        directives:{
          //注册一个局部的自定义指令 v-focus
          focus:{
            inserted:function (el) {
              el.focus()
            }
          },
          runoob:{
            bind:function (el, binding, vnode) {
              var s = JSON.stringify;
              el.innerHTML =
                'name:'        + s(binding.name) + '<br>' +
                'value:'       + s(binding.value) + '<br>' +
                'expression:'  + s(binding.expression) + '<br>' +
                'argument:'    + s(binding.arg) + '<br>' +
                'modifiers:'   + s(binding.modifiers) + '<br>' +
                'vnode keys:'  + Object.keys(vnode).join(',')
            }
          }

        }
    }
    // Vue.directive('focus',{
    //   inserted:function (el) {
    //     el.focus();
    //
    //   }
    // })
</script>

<style scoped>

</style>
