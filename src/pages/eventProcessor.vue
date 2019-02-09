<template>
    <div>
      <button @click="counter += 1">增加1</button>
      <p>这个按钮被点击了{{counter}}</p>

    </div>
</template>

<script>
    export default {
        name: "event-processor",
        data(){
          return{
            counter:0
          }
        }
    }
</script>

<style scoped>

</style>
