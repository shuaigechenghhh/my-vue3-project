<template>
    <view class="shop-mian">
        <view class="shop-headear">
            <view class="header-personal-block">
                <view class="personal-block">
                    <image class="personal-image" src="./image/20235221603(3).png"></image>
                    <view class="personal-name">租币当钱花</view>
                </view>
                <view class="rule-block">
                    <image class="rule-icon" src="./image/2023522help2.png"></image>
                    <view class="rule-text">规则</view>
                </view>
            </view>
            <view class="cion-mian-block">
                <view class="cion-block">
                    <view class="cion-text">可用租币</view>
                    <view class="cion-numbel">1560</view>
                </view>
                <image class="cion-go" src="./image/2023522bianjian3.png"></image>
            </view>
        </view>
        <view class="shop-center">
            <view class="item">
            </view>
            <view class="item">
            </view>
            <view class="item">
            </view>
            <view class="item">
            </view>
        </view>
        <view class="exchange-title">
            <view class="title-block">
                <view class="title">兑换商店</view>
                <image class="icon" src="./image/system-help@2x.png"></image>
            </view>
            <view class="record-mian-block">
                <view class="record">兑换记录</view>
                <image class="icon" src="./image/2023522baianji2.png"></image>
            </view>
        </view>
        <view class="tag-list">
            <view class="tag-item active">全部</view>
            <view class="tag-item">1-100</view>
            <view class="tag-item">100-1000</view>
            <view class="tag-item">1000-10000</view>
        </view>
        <!-- <z-paging ref="paging" v-model="shopList" @query="queryList" :fixed="false" default-page-size='5' class="shop-content-list"> -->
        <view class="shop-content-list">
            <z-paging ref="paging" v-model="shopList" @query="queryList" :fixed="false" default-page-size='5'>
                <!-- <view class="shop-content-list"> -->
                <view class="content-card" v-for="item, index in shopList" :key="index">
                    <image class="card-image" src="./image/20235221603(2).png"></image>
                    <view class="title">顶配 iPhone Xs 256…</view>
                    <view class="price">200租币 +9.9元</view>
                    <view class="num"><text>16.2元</text><text>已兑2513件</text></view>
                </view>
            <!-- </view> -->
            </z-paging>
            <!-- <view class="content-card">
                <image class="card-image" src="./image/20235221603(2).png"></image>
                <view class="title">顶配 iPhone Xs 256…</view>
                <view class="price">200租币 +9.9元</view>
                <view class="num"><text>16.2元</text><text>已兑2513件</text></view>
            </view>
            <view class="content-card">
                <image class="card-image" src="./image/20235221603(2).png"></image>
                <view class="title">顶配 iPhone Xs 256…</view>
                <view class="price">200租币 +9.9元</view>
                <view class="num"><text>16.2元</text><text>已兑2513件</text></view>
            </view>
            <view class="content-card">
                <image class="card-image" src="./image/20235221603(2).png"></image>
                <view class="title">顶配 iPhone Xs 256…</view>
                <view class="price">200租币 +9.9元</view>
                <view class="num"><text>16.2元</text><text>已兑2513件</text></view>
            </view>
            <view class="content-card">
                <image class="card-image" src="./image/20235221603(2).png"></image>
                <view class="title">顶配 iPhone Xs 256…</view>
                <view class="price">200租币 +9.9元</view>
                <view class="num"><text>16.2元</text><text>已兑2513件</text></view>
            </view> -->
        </view>
    <!-- </z-paging> -->
        <view class="footer">
            <view class="footer-btn">
                <view class="btn-tetx">赚取更多租币</view>
                <image src="./image/2023522bainji.png" class="icon"></image>
            </view>
        </view>
    </view>
</template>
<script setup lang="ts">
import { reactive, ref } from 'vue'
let shopList = reactive([{
    "cover": ["/uploads/imageUpload/2007/09/s/7hiAeYO5f06da2ed7492.jpg"],
    "id": 99,
    "imgOssServer": "https://img-t1.rrzuji.cn",
    "init_sell_num": 450,
    "is_free_shipping": 1,
    "need_coin": 1650,
    "need_pay": "0.00",
    "position_sign": "61ad74b6cef0b9b566c6134f9c8d3fac",
    "price": "26.00",
    "sell_num": 0,
    "sort": 9994,
    "tags": "新品",
    "target_id": "",
    "title": "便携式勺筷餐具套装",
    "total_num": 999,
    "type": 1
}, {
    "cover": ["/uploads/imageUpload/2007/09/s/7hiAeYO5f06da2ed7492.jpg"],
    "id": 99,
    "imgOssServer": "https://img-t1.rrzuji.cn",
    "init_sell_num": 450,
    "is_free_shipping": 1,
    "need_coin": 1650,
    "need_pay": "0.00",
    "position_sign": "61ad74b6cef0b9b566c6134f9c8d3fac",
    "price": "26.00",
    "sell_num": 0,
    "sort": 9994,
    "tags": "新品",
    "target_id": "",
    "title": "便携式勺筷餐具套装",
    "total_num": 999,
    "type": 1
}, {
    "cover": ["/uploads/imageUpload/2007/09/s/7hiAeYO5f06da2ed7492.jpg"],
    "id": 99,
    "imgOssServer": "https://img-t1.rrzuji.cn",
    "init_sell_num": 450,
    "is_free_shipping": 1,
    "need_coin": 1650,
    "need_pay": "0.00",
    "position_sign": "61ad74b6cef0b9b566c6134f9c8d3fac",
    "price": "26.00",
    "sell_num": 0,
    "sort": 9994,
    "tags": "新品",
    "target_id": "",
    "title": "便携式勺筷餐具套装",
    "total_num": 999,
    "type": 1
}, {
    "cover": ["/uploads/imageUpload/2007/09/s/7hiAeYO5f06da2ed7492.jpg"],
    "id": 99,
    "imgOssServer": "https://img-t1.rrzuji.cn",
    "init_sell_num": 450,
    "is_free_shipping": 1,
    "need_coin": 1650,
    "need_pay": "0.00",
    "position_sign": "61ad74b6cef0b9b566c6134f9c8d3fac",
    "price": "26.00",
    "sell_num": 0,
    "sort": 9994,
    "tags": "新品",
    "target_id": "",
    "title": "便携式勺筷餐具套装",
    "total_num": 999,
    "type": 1
}])
const paging = ref<null>(null)
const queryList = (pageNo: Number, pageSize: Number) => {
    const res = [
        {
            "cover": ["/uploads/imageUpload/2007/09/s/7hiAeYO5f06da2ed7492.jpg"],
            "id": 99,
            "imgOssServer": "https://img-t1.rrzuji.cn",
            "init_sell_num": 450,
            "is_free_shipping": 1,
            "need_coin": 1650,
            "need_pay": "0.00",
            "position_sign": "61ad74b6cef0b9b566c6134f9c8d3fac",
            "price": "26.00",
            "sell_num": 0,
            "sort": 9994,
            "tags": "新品",
            "target_id": "",
            "title": "便携式勺筷餐具套装",
            "total_num": 999,
            "type": 1
        }
    ]
    setTimeout(() => {
        paging.value && paging.value.completeByTotal(res, 20)
    }, 1000)
}
</script>
<style lang="scss">
.shop-mian {
    width: 100vw;
    height: 100vh;

    .shop-headear {
        width: 100%;
        height: 320rpx;
        background: linear-gradient(138deg, #FF8A3C 0%, #FF611C 100%);
        border-radius: 0rpx 0rpx 40rpx 40rpx;

        .header-personal-block {
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 20rpx 30rpx;
            box-sizing: border-box;

            .personal-block {
                display: flex;
                align-items: center;
            }

            .personal-image {
                width: 64rpx;
                height: 64rpx;
                border-radius: 64rpx;
            }

            .personal-name {
                font-size: 24rpx;
                font-family: PingFangSC-Regular, PingFang SC;
                font-weight: 400;
                color: #FFFFFF;
                margin-left: 26rpx;
            }

            .rule-block {
                display: flex;
                align-items: center;

                .rule-icon {
                    width: 28rpx;
                    height: 28rpx;
                }

                .rule-text {
                    font-size: 26rpx;
                    font-family: PingFangSC-Regular, PingFang SC;
                    font-weight: 400;
                    color: #FFFFFF;
                    margin-left: 5rpx;
                }
            }

        }

        .cion-mian-block {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0rpx 30rpx;

            .cion-text {
                font-size: 24rpx;
                font-family: PingFangSC-Regular, PingFang SC;
                font-weight: 400;
                color: #FFFFFF
            }

            .cion-numbel {
                font-size: 80rpx;
                font-family: DINAlternate-Bold, DINAlternate;
                font-weight: bold;
                color: #FFFFFF;
            }

            .cion-go {
                width: 260rpx;
                height: 120rpx;
            }
        }
    }

    .shop-center {
        display: flex;
        align-items: center;
        position: absolute;
        top: 255rpx;

        .item {
            width: 268rpx;
            height: 138rpx;
            background: #fffbd0;
            border-radius: 12rpx;
            margin-left: 30rpx;
        }
    }

    .exchange-title {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-top: 100rpx;
        padding: 0rpx 30rpx;

        .title-block {
            display: flex;
            align-items: center;

            .title {
                font-size: 32rpx;
                font-family: PingFangSC-Medium, PingFang SC;
                font-weight: 500;
                color: #222222;
            }

            .icon {
                width: 30rpx;
                height: 30rpx;
                margin-left: 10rpx;
            }
        }

        .record-mian-block {
            display: flex;
            align-items: center;

            .record {
                font-size: 28rpx;
                font-family: PingFangSC-Regular, PingFang SC;
                font-weight: 400;
                color: #999999;
            }

            .icon {
                width: 20rpx;
                height: 20rpx;
                margin-left: 10rpx;
            }
        }
    }

    .tag-list {
        display: flex;
        align-items: center;
        margin-top: 50rpx;

        .tag-item {
            border-radius: 22rpx;
            border: 2rpx solid #E6E6E6;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 44rpx;
            margin-left: 30rpx;
            font-size: 24rpx;
            font-family: PingFangSC-Medium, PingFang SC;
            font-weight: 500;
            color: #999999;
            padding: 20rpx;
            box-sizing: border-box;
        }

        .active {
            height: 44rpx;
            background: #FF673710;
            border-radius: 22rpx;
            // opacity: 0.1;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 24rpx;
            font-family: PingFangSC-Medium, PingFang SC;
            font-weight: 500;
            color: #FF6737;
            padding: 20rpx;
            box-sizing: border-box;
        }
    }

    .shop-content-list {
        display: flex;
        flex-wrap: wrap;
        // padding: 30rpx;
        box-sizing: border-box;
        height: 50%;
        overflow: auto;

        .content-card {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            margin-left: 30rpx;
            margin-top: 30rpx;

            .card-image {
                width: 335rpx;
                height: 272rpx;
            }

            .title {
                font-size: 28rpx;
                font-family: PingFangSC-Medium, PingFang SC;
                font-weight: 500;
                color: #333333;
                margin-top: 11rpx;
            }

            .price {
                font-size: 28rpx;
                font-family: PingFangSC-Regular, PingFang SC;
                font-weight: 400;
                color: #FF6737;
                margin-top: 10rpx;
            }

            .num {
                font-size: 24rpx;
                font-family: PingFangSC-Regular, PingFang SC;
                font-weight: 400;
                color: #999999;
                margin-top: 16rpx;
            }
        }
    }

    .footer {
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 30rpx;

        .footer-btn {
            width: 256rpx;
            height: 61rpx;
            border-radius: 31rpx;

            border: 2rpx solid #FF673730;
            font-size: 28rpx;
            font-family: PingFangSC-Regular, PingFang SC;
            font-weight: 400;
            color: #FF6737;
            display: flex;
            justify-content: center;
            align-items: center;

            .icon {
                width: 20rpx;
                height: 20rpx;
                margin-left: 10rpx;
            }
        }
    }
}
.height{
    width: 100%;
    height: 100%;
}
</style>