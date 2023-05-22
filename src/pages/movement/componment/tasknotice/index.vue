<template>
 <view class="model-notice" v-show="isShow">
            <view class="image-box">
                <image src="../../image/2023522930.png" class="notice-image"></image>
                <view class="content-box">
                    <view class="title-box">恭喜获得{{cion}}个租币！</view>
                    <view class="notice-box">任务完成</view>
                </view>
            </view>
            <view class="notice-cion">+{{ cion }}</view>
        </view>
</template>
<script  setup lang="ts">
defineProps({
    isShow: {
        type: Boolean,
        default: false
    },
    cion:{
        type:String || Number,
        default :'0'
    }
})
</script>
<style lang="scss">
.model-notice {
    width: 660rpx;
    height: 111rpx;
    background: rgba(0, 0, 0, 0.72);
    border-radius: 12rpx;
    position: absolute;
    z-index: 999;
    bottom: 80rpx;
    display: flex;
    align-items: center;
    justify-content: space-between;
    left: 0;
    right: 0;
    margin: auto;
    padding: 10rpx;
}

.image-box {
    display: flex;
    align-items: center;
    justify-content: space-between;
    .notice-image {
    width: 82rpx;
    height: 82rpx;
}


}

.content-box {
    margin-left: 20rpx;
}

.title-box {
    font-size: 30rpx;
    font-family: PingFangSC-Regular, PingFang SC;
    font-weight: 400;
    color: #FFFFFF;
}

.notice-box {
    margin-top: 10rpx;
    font-size: 24rpx;
    font-family: PingFangSC-Regular, PingFang SC;
    font-weight: 400;
    color: #FFFFFF;
}

.notice-cion {
    font-size: 38rpx;
    font-family: PingFangSC-Medium, PingFang SC;
    font-weight: 500;
    color: #FFFFFF;
}
</style>