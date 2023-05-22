<template>
    <view class="detail-main" v-if="isShow">
        <view class="detail-content">
            <view class="title">活动通知</view>
            <view class="content margin-top">恭喜获得20个租币，请查收。为了感谢其长久以来的陪伴，这里的文字请忽略。活动期间每天 11 点还会上线限量礼包，数量有限先到先得，用户们千万不要错过！ </view>
            <view class="title margin-top">小标题</view>
            <view class="content margin-top">此外，对于所有有贡献的用户。</view>
        </view>
        <view class="detail-btn-block">
                <view class="detele-btn" @click="$emit('handleDetail')">删除</view>
                <view class="comfirm-btn" @click="$emit('handleDetail')">确认</view>
            </view>
    </view>
</template>
<script setup  lang="ts">
defineProps({
    isShow: {
        type: Boolean,
        default: false
    },
})
</script>
<style lang="scss">
.detail-main {
    width: 100vw;
    height: 100vh;
    background-color: #33333390;
    position: fixed;
    top: 0;
    z-index: 20;

    .detail-content {
        width: 100%;
        height: 837rpx;
        background: #FFFFFF;
        border-radius: 30rpx 30rpx 0rpx 0rpx;
        position: absolute;
        bottom: 0;
        padding: 70rpx 30rpx 0rpx 30rpx;
        box-sizing: border-box;

        .title {
            font-size: 36rpx;
            font-family: PingFangSC-Regular, PingFang SC;
            font-weight: 400;
            color: #333333;
        }

        .content {
            font-size: 28rpx;
            font-family: PingFangSC-Regular, PingFang SC;
            font-weight: 400;
            color: #999999
        }

    }
    .detail-btn-block {
            position: absolute;
            bottom: 0;
            display: flex;
            width: 100%;

            .detele-btn {
          flex: 1;
                height: 100rpx;
                background: #F2F2F2;
                font-size: 36rpx;
                font-family: PingFangSC-Regular, PingFang SC;
                font-weight: 400;
                color: #BFBFBF;
                display: flex;
                justify-content: center;
                align-items: center;
            }

            .comfirm-btn {
         flex: 2;
                height: 100rpx;
                background: #00C8BE;
                font-size: 36rpx;
                font-family: PingFangSC-Regular, PingFang SC;
                font-weight: 400;
                color: #FFFFFF;
                display: flex;
                justify-content: center;
                align-items: center;
            }
        }
}
.margin-top{
    margin-top: 20rpx;
}
</style>