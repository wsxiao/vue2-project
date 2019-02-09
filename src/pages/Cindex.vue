<template>
  <div>
    <v-header></v-header>
    <!--<span>{{message}}</span>-->
  </div>

</template>

<script>
  import vHeader from '../components/header'

  export default {
    name: "Index",
    data() {
      return {
        message: 'Welcome to Your Index'
      }
    },
    components: {
      vHeader
    },
  }
</script>

<style src="../assets/less/index.less" scoped></style>

<!--<style scoped>-->

<!--</style>-->
