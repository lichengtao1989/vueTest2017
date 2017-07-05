<template>
<div class="header">
  <div class="content-warpper">
  <div v-if="seller.supports" class="support-count">
      <span class="count">{{seller.supports.length}}个</span>
      <i class="icon-thumb_up"></i>
    </div>  
    <div class="avatar">
      <img :src="seller.avatar" width="64" height="64" alt="">
    </div>
    <div class="content">
  
      <div class="title">
        <span class="brand"></span>
        <span class="name">{{seller.name}}</span>
      </div>
      <div class="description">
        {{seller.description}}/{{seller.deliveryTime}}分钟送达
      </div>
      <div v-if="seller.supports" class="support">
        <span class="icon" :class="classMap[seller.supports[0].type]"></span>
        <span class="text">{{seller.supports[0].description}}</span>
      </div>
    </div>
  </div>
  <div class="bulletin-warpper">
    <span class="bulletin-title"></span><span class="bulletin-text">{{seller.bulletin}}</span><i class="icon-thumb_up"></i>
  </div>
</div>
 
</template>

<script>
export default {
  name: 'header',
  props:{
    seller:{
      type:Object
    }
  },
  created(){
    this.classMap=['decrease','discount','special','invoice','guarantee'];
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
@import "../../common/stylus/mixin.styl";
@import "../../common/stylus/header.styl";
</style>
