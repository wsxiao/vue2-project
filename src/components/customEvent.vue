<template>
    <button v-on:click="incrementHandler">{{counter}}</button>
</template>

<script>
    export default {
        name: "custom-event",
        data:function(){
          return{
            counter:0
          }
        },
      methods:{
        incrementHandler:function () {
          this.counter += 1;
          this.$emit('increment')
        }
      }
    }
</script>

<style scoped>

</style>
