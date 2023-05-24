<template>
    <view class="movement-main">
        <view class="movement-headers">
            <image src="./image/bg@2x.png" mode="widthFix" class="headers-bg"></image>
            <view class="movement-box">
                <view class="box-clmue">
                    <image src="./image/bz13@2x.png" class="box-image" @click="hangleToNotice"></image>
                    <view class="right-box">
                        <image src="./image/bj3@2x(1).png" class="box-image-right"></image>
                        <text class="box-text">32</text>
                    </view>
                </view>
                <view class="box-clmue margin-box">
                    <image src="./image/bz13bf@2x.png" class="box-image"></image>
                    <view class="right-box">
                        <image src="./image/bj3@2x.png" class="box-image-right"></image>
                        <text class="box-text-two">已签到</text>
                    </view>
                </view>
                <view class="bubble-list">
                    <view class="bubble-box fisrt">
                        <text class="bubble-text">支付成功</text>
                        <image src="./image/bz4bf6@2x(2).png" class="bubble-bg"></image>
                    </view>
                    <view class="bubble-box">
                        <text class="bubble-text">运动步数</text>
                        <image src="./image/bz4bf6@2x(2).png" class="bubble-bg"></image>
                    </view>
                    <view class="bubble-box center">
                        <text class="bubble-text">支付成功</text>
                        <image src="./image/bz4bf6@2x(2).png" class="bubble-bg"></image>
                    </view>
                    <view class="bubble-box">
                        <text class="bubble-text">运动步数</text>
                        <image src="./image/bz4bf6@2x(2).png" class="bubble-bg"></image>
                    </view>
                    <view class="bubble-box last">
                        <text class="bubble-text">支付成功</text>
                        <image src="./image/bz4bf6@2x(2).png" class="bubble-bg"></image>
                    </view>
                </view>
                <view class="bubble-main">
                    <view class="bubble-text">
                        <view class="today-text">今日步数</view>
                        <view class="movement-num">2748</view>
                        <view class="movement-text">每日24:00自动清零</view>
                    </view>
                    <image src="./image/boy@2x.png" class="boy"></image>
                    <image src="./image/girl@2x.png" class="girl"></image>
                    <view class="bubble-btn">
                        瓜分999现金
                    </view>
                </view>
            </view>
        </view>
        <view class="movement-center-content">
            <view class="movement-center">
                <view class="line"></view>
                <view class="center-title">租币当钱花</view>
                <view class="center-list">
                    <image class="list-item" src="./image/pic_shop@2x.png" @click="hangleShop"></image>
                    <image class="list-item margin-left" src="./image/pic_task@2x.png" @click="handleShow(true)"></image>
                    <image class="list-item margin-left" src="./image/pic_cash@2x.png"></image>
                </view>
            </view>
            <view class="movement-shop">
                <view class="center-title">租物推荐</view>
                <view class="shop-list">
                    <view class="shop-card">
                        <image class="card-item" src="./image/Bitmap@2x(1).png" mode="widthFix"></image>
                        <view class="card-title">顶配 iPhone Xs 256…</view>
                        <view class="card-tag">免押金</view>
                        <view class="card-pirce">
                            <view class="price">￥6.66/天</view>
                            <view class="today">30天起租</view>
                        </view>
                    </view>
                    <view class="shop-card margin-left-xl">
                        <image class="card-item" src="./image/Bitmap@2x(1).png" mode="widthFix"></image>
                        <view class="card-title">顶配 iPhone Xs 256…</view>
                        <view class="card-tag">免押金</view>
                        <view class="card-pirce">
                            <view class="price">￥6.66/天</view>
                            <view class="today">30天起租</view>
                        </view>
                    </view>
                    <view class="shop-card margin-top">
                        <image class="card-item" src="./image/Bitmap@2x(1).png" mode="widthFix"></image>
                        <view class="card-title">顶配 iPhone Xs 256…</view>
                        <view class="card-tag">免押金</view>
                        <view class="card-pirce">
                            <view class="price">￥6.66/天</view>
                            <view class="today">30天起租</view>
                        </view>
                    </view>

                    <view class="shop-card margin-top margin-left-xl">
                        <image class="card-item" src="./image/Bitmap@2x(1).png" mode="widthFix"></image>
                        <view class="card-title">顶配 iPhone Xs 256…</view>
                        <view class="card-tag">免押金</view>
                        <view class="card-pirce">
                            <view class="price">￥6.66/天</view>
                            <view class="today">30天起租</view>
                        </view>
                    </view>

                </view>
                <view class="more-block">
                    <view class="more-btn">
                        <text>查看更多</text>
                        <image src="./image/DisclosureIndicator@2x.png" class="icon"></image>
                    </view>
                </view>
            </view>
        </view>
        <TaskModel :isShow="isShow" @handleShow="handleShow"></TaskModel>
    </view>
</template>

<script setup lang="ts">
import TaskModel from './componment/taskModel/index.vue'
import { ref } from 'vue'

const isShow = ref(false)
const handleShow = (value: boolean) => {
    isShow.value = value
}
const hangleToNotice = () => {
    uni.navigateTo({
        url: '/pages/noticeList/index'
    })
}
const hangleShop = () => {
    uni.navigateTo({
        url: '/pages/shop/index'
    })
}
</script>

<style scoped >
.movement-center-content{
  background: #FFFFFF;
  position: absolute;
  top: 770rpx;
  width:100%;
  border-radius: 48rpx 48rpx 0rpx 0rpx;
}
.movement-main {
    position: relative;
    height: 100vh;
    width: 100vw;
    overflow: auto;
}

.movement-headers {
  position: fixed;
  top: 70rpx;
  width: 100%;
}

.movement-box {
    position: absolute;
    top: 0;
    width: 100%;
    height: 100%;
}

.box-clmue {
    display: flex;
    width: 100%;
    justify-content: space-between;
    margin-top: 30rpx;

}

.right-box {
    width: 140rpx;
    height: 60rpx;
    background: #FFFFFF;
    border-radius: 27rpx 0rpx 0rpx 27rpx;
    opacity: 0.7;
    display: flex;
    align-items: center;
}

.box-image {
    width: 56rpx;
    height: 72rpx;
    margin-left: 20rpx;
}

.box-image-right {
    width: 49rpx;
    height: 55rpx;
    margin-left: 10rpx;
}

.headers-bg {
    width: 100%;
}

.box-text {
    margin-left: 5rpx;
    font-size: 32rpx;
    font-family: DINAlternate-Bold, DINAlternate;
    font-weight: bold;
    color: #027C64;
}

.box-text-two {
    margin-left: 5rpx;
    font-size: 22rpx;
    font-family: PingFangSC-Medium, PingFang SC;
    font-weight: 500;
    color: #105B50;
}

.margin-box {
    margin-top: 18rpx;
}

.bubble-box {
    display: flex;
    flex-direction: column;

}

.bubble-text {
    font-size: 22rpx;
    font-family: PingFangSC-Medium, PingFang SC;
    font-weight: 500;
    color: #105B50;
}

.bubble-bg {
    width: 92rpx;
    height: 86rpx;
}

.bubble-list {
    display: flex;
    width: 100%;
    justify-content: space-around;
    position: absolute;
    top: 185rpx;
}

.fisrt {
    margin-left: 60rpx;
    margin-top: 100rpx;
}

.last {
    margin-top: 100rpx;
    margin-right: 60rpx;
}

.center {
    margin-top: 14rpx;
}

.bubble-main {
    position: absolute;
    top: 390rpx;
    left: 50%;
    transform: translate(-220rpx);
    width: 440rpx;
    height: 440rpx;
    border-radius: 330rpx 330rpx 0 0;
    background: linear-gradient(360deg, rgba(255, 255, 255, 0) 0%, #FFFFFF 100%);
}

.boy {
    position: absolute;
    width: 65rpx;
    height: 124rpx;
    bottom: 165rpx;
    left: 20rpx;
}

.girl {
    position: absolute;
    width: 75rpx;
    height: 106rpx;
    bottom: 165rpx;
    right: 0rpx;
}

.bubble-text {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    /* margin-top: 40rpx; */
    padding-top: 40rpx;
}

.today-text {
    font-size: 24rpx;
    font-family: PingFangSC-Regular, PingFang SC;
    font-weight: 400;
    color: #999999;
}

.movement-num {
    font-size: 110rpx;
    font-family: DINCondensed-Bold, DINCondensed;
    font-weight: bold;
    color: #084F3E;
}

.movement-text {
    font-size: 24rpx;
    font-family: PingFangSC-Regular, PingFang SC;
    font-weight: 400;
    color: #999999;
}

.bubble-btn {
    position: absolute;
    bottom: 80rpx;
    width: 450rpx;
    height: 88rpx;
    background: linear-gradient(360deg, #FA5721 0%, #FFA901 100%);
    box-shadow: 0rpx 10rpx 40rpx 0rpx rgba(234, 255, 124, 0.8);
    border-radius: 50rpx;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 40rpx;
    font-family: PingFangSC-Medium, PingFang SC;
    font-weight: 500;
    color: #FFFFFF;
}

.movement-center {
    width:100%;
  background: #FFFFFF;
  border-radius: 48rpx 48rpx 0rpx 0rpx;
}

.line {
    width: 60rpx;
  height: 10rpx;
  background: #E2E2E2;
  border-radius: 5rpx;
  position: absolute;
  left: 50%;
  transform: translate(-30rpx);
  top: 20rpx;
}

.center-title {
    margin-top: 60rpx;
    margin-left: 30rpx;
    font-size: 36rpx;
    font-family: PingFangSC-Medium, PingFang SC;
    font-weight: 600;
    color: #222222;

}

.center-list {
    display: flex;
    padding: 30rpx;

}

.list-item {
    width: 200rpx;
    height: 240rpx;
}

.margin-left {
    margin-left: 10rpx;
}

.movement-shop {
    width: 750rpx;
  background: #FFFFFF;
  border-radius: 48rpx 48rpx 0rpx 0rpx;
}

.shop-list {
    display: flex;
    background-color: #f0f1f2;
    padding: 25rpx;
    flex-wrap: wrap;
}

.shop-card {
    background-color: #FFFFFF;
    border-radius: 12rpx;
    box-sizing: border-box;
    padding-bottom: 20rpx;
}

.card-item {
    /* width: 100%; */
    width: 340rpx;
    /* height: 424rpx; */

}

.card-title {
    font-size: 30rpx;
    font-family: PingFangSC-Regular, PingFang SC;
    font-weight: 400;
    color: #333333;
    margin-left: 18rpx;
}

.card-tag {
    margin-top: 10rpx;
    width: 84rpx;
    height: 32rpx;
    background: #FFFFFF;
    border-radius: 4rpx;
    border: 1rpx solid #00C8BE;
    font-size: 22rpx;
    font-family: PingFangSC-Regular, PingFang SC;
    font-weight: 400;
    color: #00C8BE;
    text-align: center;
    line-height: 30rpx;
    margin-left: 18rpx;
}

.card-pirce {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 6rpx;
}

.price {
    font-size: 24rpx;
    font-family: PingFangSC-Regular, PingFang SC;
    font-weight: 400;
    color: #F04F4F;
    margin-left: 18rpx;
}

.today {
    font-size: 24rpx;
    font-family: PingFangSC-Regular, PingFang SC;
    font-weight: 400;
    color: #AAAAAA;
    margin-right: 18rpx;
}

.margin-top {
    margin-top: 25rpx;
}

.margin-left-xl {
    margin-left: 20rpx;
}

.more-block {
    width: 100%;
    display: flex;
    justify-content: center;
    margin-top: 50rpx;
    margin-bottom: 100rpx;
}

.more-btn {
    width: 268rpx;
    height: 61rpx;
    border-radius: 31rpx;
    border: 1rpx solid #999999;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 268rpx;
    height: 61rpx;
    border-radius: 31rpx;
    border: 1rpx solid #999999;
    font-size: 30rpx;
    font-family: PingFangSC-Regular, PingFang SC;
    font-weight: 400;
    color: #999999;
}

.icon {
    margin-left: 10rpx;
    width: 16rpx;
    height: 26rpx;
}</style>
