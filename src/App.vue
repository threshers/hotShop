<template>
  <div id="app" style="height:100%;">
    <view-box ref="viewBox">
      <router-view></router-view>
    </view-box>
    <tabbar>
      <tabbar-item selected link="/">
        <img slot="icon"  src="@/assets/home.png">
        <span slot="label">首页</span>
      </tabbar-item>
      <tabbar-item show-dot>
        <img slot="icon" src="@/assets/goods.png">
        <span slot="label">好物</span>
      </tabbar-item>
      <tabbar-item  link="/component/demo">
        <img slot="icon" src="@/assets/area.png">
        <span slot="label">好地</span>
      </tabbar-item>
      <tabbar-item badge="2">
        <img slot="icon" src="@/assets/my.png">
        <span slot="label">我</span>
      </tabbar-item>
    </tabbar>
  </div>
</template>

<script>
  import {ViewBox, Tabbar, TabbarItem,} from 'vux'

  export default {
    name: 'app',
    components:{
      ViewBox,
      Tabbar,
      TabbarItem
    }
  }
</script>

<style lang="less">
@import '~vux/src/styles/reset.less';
html, body {
  height: 100%;
  width: 100%;
  overflow-x: hidden;
}

</style>
