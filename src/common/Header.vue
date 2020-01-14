<template>
  <div class="header">
     <div class="header-left">
        <img class="Logo-img" :src="logo">
        <span>AI.<i>ADMIN</i></span>
      </div> 
      <div class="header-right"> 
        <div class="user-avator">
          <img src="https://wpimg.wallstcn.com/f778738c-e4f8-4870-b634-56703b4acafe.gif?imageView2/1/w/80/h/80" />
        </div>
      </div>
  </div>  
</template>

<script>
import LogoImg from "../assets/img/logo.png"
export default {
  name : "HeaderNav",
  data() {
    return {
      logo : LogoImg
    }
  }
}
</script>

<style lang="stylus" scoped>
  .header
    position: relative
    width: 100%
    height: 70px
    background: #242f42
    .header-left
      float: left
      width: 180px
      line-height: 70px
      padding-left: 10px
      color: #fff
      font-size: 22px
      .Logo-img
        width: 40px
        margin-right: 10px
      i
        color: #FF6C60
    .header-right
      float: right 
      .user-avator
        img
          width 40px
          height 40px   
</style>
