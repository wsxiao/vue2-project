<template>
  <div class="main-content layui-row">
    <!--Header Top-->
    <div class="header-top">
      <!--Logo-->
      <div class="header-logo-box layui-col-xs12 layui-col-sm4">
        <img class="logo-img" src="../../static/img/logo.png" alt="logo">
      </div>

      <!--Menu-->
      <div class="header-menu-box layui-col-xs12 layui-row">
        <span class="logo-text">
        China’s Leading B2B  Bio's Tourism Consulting Agency
        </span>
        <br>
        <p class="menu-item" v-for="item of menuList" @click="activeMenu(item)" @mouseenter="moveMenu(item)">
        <span class="menu-item-border" :class="item.className">
          <span class="sanjiao" v-if="item.activeStatus"></span>
        </span>
          <span class="menu-text">{{item.menuName}}</span>
        </p>
      </div>
    </div>

    <!--Carousel-->
    <div class="layui-carousel" id="carousel">
      <div carousel-item>
        <div v-for="item of carouselList">
          <img class="carousel-img" :src='item.src' alt="">
        </div>
      </div>
    </div>

    <!--Header Footer-->
    <div class="header-footer">
      <p class="footer-content">
        <span>Create Consulting Co.,Limited</span>
        <img src="../../static/img/smLogo.png" alt="">
      </p>

    </div>


  </div>
</template>

<script>
  export default {
    name: "Header",
    data() {
      return {
        message: 'Hahahha',
        headerShow: true,
        menuList: [],
        carouselList: [],
      }
    },
    mounted(){
      layui.use('carousel', function(){
        var carousel = layui.carousel;
        //建造实例
        carousel.render({
          elem: '#carousel'
          ,width: '10rem' //设置容器宽度
          ,height: '3.6rem'
          ,arrow: 'hover' //始终显示箭头
          ,anim: 'default' //切换动画方式
        });
      });

      this.getMenuList()
      this.getCarouselList()
    },
    methods:{
      // 获取菜单列表
      getMenuList(){
        this.menuList = [
          {className:'menu-item-border8373ce', activeStatus:false, menuName:'About Us'},
          {className:'menu-item-borderf8b54d', activeStatus:false, menuName:'Service'},
          {className:'menu-item-borderffc5b4e', activeStatus:false, menuName:'Experience'},
          {className:'menu-item-border35a3f0', activeStatus:false, menuName:'Knowledge'},
        ]
      },

      // 点击菜单
      activeMenu(menu){
        this.moveMenu(menu)
      },

      // 鼠标移过出现三角
      moveMenu(menu){
        console.log('鼠标移入',menu)
        for(let item of this.menuList){
          item.activeStatus =  false;
        }
        menu.activeStatus = true;
      },

      // carousel 图片列表
      getCarouselList(){
        this.carouselList = [
          {index:0, src:'../../static/img/banner/1-DW.jpg', name:'01'},
          {index:1, src:'../../static/img/banner/2-DW EVENT.JPG', name:'01'},
          {index:2, src:'../../static/img/banner/3-ATC OFFICIAL.jpg', name:'01'},
          {index:3, src:'../../static/img/banner/4-ATC FAM.jpg', name:'01'},
          {index:4, src:'../../static/img/banner/5-JORDAN.jpg', name:'01'},
          {index:5, src:'../../static/img/banner/6-JORDAN KOL.jpg', name:'01'},
          {index:6, src:'../../static/img/banner/7-PERU..jpg', name:'01'},
          {index:7, src:'../../static/img/banner/8-VIKING.png', name:'01'},
          {index:8, src:'../../static/img/banner/9-Sunlover.jpg', name:'01'},
          {index:9, src:'../../static/img/banner/10-PF.png', name:'01'},
        ]

      }
    },


  }
</script>

<style lang="less" src="../assets/less/index.less" scoped></style>
