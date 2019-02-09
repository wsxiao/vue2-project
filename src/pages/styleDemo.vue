<template>
    <div class="style-demo-content">
        <div :style="[baseStyles,overridingStyles]">菜鸟教程</div>
    </div>
</template>

<script>
    export default {
        name: "style-demo",
        data(){
          return{
            baseStyles:{
              color:'green',
              fontSize:'30px'
            },
            overridingStyles:{
              fontWeight:'bold'
            }
          }
        },
    }
</script>

<style scoped>

</style>
