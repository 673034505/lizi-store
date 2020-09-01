
<template>
  <view class="container"  :style="{backgroundColor:titleNViewBackground}">
    <!-- 小程序头部兼容 -->
    <!-- #ifdef MP -->
    <view class="mp-search-box">
      <input class="ser-input" type="text" value="输入关键字搜索" disabled />
    </view>
    <!-- #endif -->
    <view class="banner-scroll">
        <view class="banner-item" >
            <u-tabs :list="banner" :is-scroll="true" :current="current" @change="handleClick"></u-tabs>
            <!-- <text class="item" @click="handleClick(index)" :class="active==index?'home':''" v-for="(item,index) in banner" :key="index">{{item}}</text> -->
            </view>
        <view class="banner-more">
            <u-icon name="list" size='40'></u-icon>
            <!-- <u-button type="primary">主要按钮</u-button> -->
        </view>

    </view>
  </view>
</template>
<script>
import uButton from "uview-ui/components/u-button/u-button.vue";
import uIcon from "uview-ui/components/u-icon/u-icon.vue";
import uTabs from "uview-ui/components/u-tabs/u-tabs.vue";
export default {
    components: {
            uButton,
            uIcon,
            uTabs
		},
  name: "index",
  data() {
    return {
        banner:[{name:'首页'},{name:'百货'},{name:'洗漱'},{name:'美妆'},{name:'手机'},{name:'女装'},{name:'医药'},{name:'数码'},{name:'男装'},{name:'运动'},{name:'进口'},{name:'食品'},],
        current:0,
        titleNViewBackground:'#f9f9f9'
    };
  },
  onLoad() {
    setTimeout(function () {
      //关闭启动界面。app端才会执行 其他不执行
      // #ifdef  APP-PLUS
      plus.navigator.closeSplashscreen();
      // #endif
    }, 3000);
  },
  methods: {
      handleClick(index){
          this.current = index
      }
  },
};
</script>
<style lang="less" scoped>
.container {
  padding-top: 3rem;
  background: #f9f9f9;
  color: #333;
  min-height: 98vh;
}
.banner-scroll{
    width: 100%;
    height: 2rem;
    display: flex;
    justify-content:space-between;
    align-items: center;
}
.banner-item{
    flex: 1;
    overflow-y: hidden;
    display: -webkit-box;
    overflow-x: scroll;
    .item{
        width: 3rem;
        line-height: 1.82rem;
        text-align: center;
        padding: .16rem;
        display: block;
        color: #333;
    }
    .home{
        font-size: 1.25rem;
        color: #D94569;
    }
}
.banner-more{
    width: 1.85rem;
    height: 1.25rem;
    text-align: center;
    background: #fff;
    line-height:1.25rem ;
    box-shadow: -5px 0px 4px  #888888;
    display: flex;
    justify-content: center;
}
</style>