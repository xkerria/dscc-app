<template>
  <view class="user-panel">
    <view class="left">
      <view class="avatar">
        <open-data type="userAvatarUrl"></open-data>
      </view>
      <view class="base">
        <view class="nickname">
          <open-data type="userNickName"></open-data>
        </view>
        <image v-if="user.vip" :src="user.vip.icon_url" class="vip" mode="heightFix" />
      </view>
    </view>

    <view class="right">
      <slot></slot>
    </view>
  </view>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'user-panel',
  computed: {
    ...mapState('auth', ['user'])
  }
}
</script>

<style lang="scss" scoped>
.user-panel {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 66rpx 20rpx 50rpx 20rpx;

  .left {
    display: flex;
    align-items: center;

    .avatar {
      width: 120rpx;
      height: 120rpx;
      border-radius: 50%;
      overflow: hidden;
      box-shadow: 0 0 20rpx 0 rgba(0, 0, 0, 0.1);
    }

    .base {
      margin-left: 40rpx;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: flex-start;

      .nickname {
        font-size: 36rpx;
        line-height: 1;
        color: #fff;
        font-weight: 500;
      }

      .vip {
        display: inline-block;
        margin-top: 20rpx;
        height: 36rpx;
      }
    }
  }

  .right {
  }
}
</style>
