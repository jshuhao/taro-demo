<template>
  <view class="container">
    <view class="page-body">
      <view class="page-section">
        <view class="page-section-title">
          <text>Vertical Scroll - 纵向滚动</text>
        </view>
        <view class="page-section-spacing">
          <scroll-view :scroll-y="true"
                       style="height: 300rpx;"
                       @scrolltoupper="upper"
                       @scrolltolower="lower"
                       @scroll="scroll"
                       :scroll-into-view="toView"
                       :scroll-top="scrollTop">
            <view id="demo1"
                  class="scroll-view-item demo-text-1">1</view>
            <view id="demo2"
                  class="scroll-view-item demo-text-2">2</view>
            <view id="demo3"
                  class="scroll-view-item demo-text-3">3</view>
          </scroll-view>
        </view>
      </view>
      <view class="page-section">
        <view class="page-section-title">
          <text>Horizontal Scroll - 横向滚动</text>
        </view>
        <view class="page-section-spacing">
          <scroll-view class="scroll-view_H"
                       :scroll-x="true"
                       @scroll="scroll"
                       style="width: 100%">
            <view id="demo21"
                  class="scroll-view-item_H demo-text-1">a</view>
            <view id="demo22"
                  class="scroll-view-item_H demo-text-2">b</view>
            <view id="demo23"
                  class="scroll-view-item_H demo-text-3">c</view>
          </scroll-view>
        </view>
      </view>
    </view>
  </view>
</template>

<script>
const order = ['demo1', 'demo2', 'demo3']
export default {
  name: 'Index',
  data () {
    return {
      scrollTop: 0,
      toView: 'demo2'
			
    }
  },
  methods: {
    upper (e) {
      console.log('upper:', e)
    },

    lower (e) {
      console.log('lower:', e)
    },

    scroll (e) {
      console.log('scroll:', e)
    }
  }
}
</script>

<style>
.page-section-spacing {
  margin-top: 60rpx;
}
.scroll-view_H {
  white-space: nowrap;
}
.scroll-view-item {
  height: 300rpx;
}
.scroll-view-item_H {
  display: inline-block;
  width: 100%;
  height: 300rpx;
}

.demo-text-1 {
  background: #ccc;
}
.demo-text-2 {
  background: #999;
}
.demo-text-3 {
  background: #666;
}
</style>