<template>
  <div class="main-bg">
<!--    <div class="bg-desc">-->
<!--      <div class="title">{{data.title}}</div>-->
<!--      <div class="slogan" v-for="item in data.slogan" :key="item">{{item}}</div>-->
<!--      <div class="lz"></div>-->
<!--    </div>-->
<!--    <div class="main-breadcrumb">-->
<!--      <img src="assets/icons/address.png" class="icon" />-->
<!--      <span class="content">{{data.content}}</span>-->
<!--    </div>-->
    <div class="bg-img" :style="style" v-if="data.useStyle"></div>
    <img :src="data.img" alt="" class="bg-img" v-else>
  </div>
</template>

<script>
export default {
  name: 'PicAndBreadcrumb',
  props: {
    data: {
      type: Object,
      default: ()=>({
        slogan: [],
        title: '',
        content: '',
        img: ''
      })
    },
  },
  computed: {
    style() {
      return {
        background: `url(${this.data.img})`,
        backgroundSize: window.innerWidth+'px',
      }

    }
  },
  data() {
    return {
    }
  }
}
</script>

<style lang="less" scoped>
  .main-bg{
    color: #fff;
    img{
      width: 100%;
    }
  }
  .bg-img{
    width: 100%;
    /*height: 100vh;*/
    background-size: 1440px;
    background-position: center;
    background: #000;
  }
  .bg-desc{
    position: absolute;
    display: flex;
    flex-direction: column;
    left: 10%;
    bottom: 18%;
    .title{
      font-size: 24px;
      margin-bottom: 38px;
    }
    .slogan{
      font-size: 36px;
      margin-bottom: 25px;
    }
    .lz{
      margin-top: 25px;
      width: 44px;
      height: 1px;
      background: #fff;
    }
  }
  .main-breadcrumb{
    position: absolute;
    right: 10%;
    bottom: 18%;
    display: flex;
    font-size: 16px;
    .icon{
      width: 14px;
      height: 18px;
      margin-right: 10px;
    }
  }
</style>
