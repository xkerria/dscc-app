<template>
  <view class="action" @click="$emit('click')">
    <view class="icon">
      <image
        class="image"
        :src="`https://project-dscc.oss-cn-chengdu.aliyuncs.com/static/images/icon-${icon}.png`"
        mode="aspectFit"
      />
    </view>
    <view class="text" :style="{ borderBottom: borderBottom ? '1rpx solid #eee' : 'none' }">
      <slot></slot>
    </view>
  </view>
</template>

<script>
export default {
  name: 'action',
  props: {
    icon: {
      type: String,
      required: true
    },
    borderBottom: {
      type: Boolean,
      default: true
    }
  }
}
</script>

<style lang="scss" scoped>
.action {
  display: flex;
  align-items: center;
  padding-right: 30rpx;

  .icon {
    width: 96rpx;
    display: flex;
    justify-content: center;
    align-items: center;

    .image {
      width: 36rpx;
      height: 36rpx;
    }
  }

  .text {
    flex: 1;
    padding: 32rpx 0;
    border-bottom: 1rpx solid #eee;
  }
}
</style>
