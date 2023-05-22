<template>
    <view class="notice-mian">
        <view class="notice-title">
            <view class="title-item" v-for="item, index in titleList" :key="index" :class="index === 0 ? '' : 'margin-two'"
                @click="handleTabSwitch(index)">
                <view :class="index === currentTitle ? 'title-active' : 'title'">{{ item.title }}</view>
                <view class="line" v-if="index === currentTitle"></view>
                <image src="./image/2023522dian.png" class="point-box" v-if="item.hasNotice"></image>
            </view>
        </view>
        <view class="notice-control-box">
            <view class="control-btn" @click="handleShowModel">
                <image class="btn-image" src="./image/2023522detele.png"></image>
                <view class="btn-text">删除已读</view>
            </view>
            <view class="line"></view>
            <view class="control-btn" @click="handleNotice">
                <image class="btn-image" src="./image/2023522feng.png"></image>
                <view class="btn-text">一键已读</view>
            </view>
        </view>
        <view class="notice-list-box">
            <z-paging ref="paging" v-model="noticeList" @query="queryList" :fixed="false" default-page-size='5'>
                <view class="notice-item" v-for="item, index in noticeList" :key="index" @click="handleDetail(true)">
                    <view class="item-title-box">
                        <view class="image-box">
                            <image src="./image/2023522dian.png" class="icon-point" v-if="item.hasRead"></image>
                            <image class="icon-box" src="./image/2023522notice.png" v-if="currentTitle === 0"></image>
                            <image class="icon-box" src="./image/2023522xiaox.png" v-if="currentTitle === 1"></image>
                            <view class="title">{{ item.title }}</view>
                        </view>
                        <view class="tiem">{{ item.time }}</view>
                    </view>
                    <view class="notice-content">{{ item.content }}</view>
                </view>
            </z-paging>

        </view>
        <TaskNotice :isShow="hasNotice" :cion="currentCion"></TaskNotice>
        <DetailModel :isShow="isDetailShow" @handleDetail="handleDetail(false)"></DetailModel>
    </view>
</template>
<script setup lang="ts">
import { reactive, ref } from 'vue'
import TaskNotice from '../movement/componment/tasknotice/index.vue'
import DetailModel from './componments/detailModel/index.vue'
type noticeList = {
    title: string,
    hasRead: boolean,
    time: string,
    content: string,
    coin: string

}
const titleList = reactive([{
    title: '活动公告',
    hasNotice: true
}, {
    title: '订单消息',
    hasNotice: false
}])
let noticeList = reactive([{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: false,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: true,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: false,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: true,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: false,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: true,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: false,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: true,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: false,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: true,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: false,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: true,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: false,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: true,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: false,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: true,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: false,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: true,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: false,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},
{
    title: '活动通知',
    time: '2020-03-23 14:30',
    hasRead: true,
    content: '恭喜获得20个租币，请查收',
    coin: '20'
},])
const currentTitle = ref(0)
const hasNotice = ref(false)
const isDetailShow=ref(false)
const currentCion = ref('20')
const paging = ref<null>(null)
const handleClose = () => {
    hasNotice.value = false
}
const handleDetail=(value:boolean)=>{
    isDetailShow.value=value
}

const handleNotice = () => {
    updateList()
    hasNotice.value = true
    setTimeout(() => {
        handleClose()
    }, 1000)
}
const updateList = () => {
    noticeList = noticeList.map(item => ({ ...item, hasRead: false }))
}
const handleTabSwitch = (index: number) => {
    currentTitle.value = index
}
const handleShowModel = () => {
    uni.showModal({
        title: '是否要删除已读通知',
        cancelText: '取消',
        confirmText: '确认删除',
        cancelColor: '#00C8BE',
        confirmColor: '#999999',
        success: (res) => {
            if (res.confirm) {
                console.log('用户点击确定');
            } else if (res.cancel) {
                console.log('用户点击取消');
            }
        }
    })
}
// onMounted(() => {
//     queryList(1, 20)
// })
const queryList = (pageNo: Number, pageSize: Number) => {
    const res = [{
        title: '活动通知',
        time: '2020-03-23 14:30',
        hasRead: true,
        content: '恭喜获得20个租币，请查收',
        coin: '20'
    },
    {
        title: '活动通知',
        time: '2020-03-23 14:30',
        hasRead: false,
        content: '恭喜获得20个租币，请查收',
        coin: '20'
    },
    {
        title: '活动通知',
        time: '2020-03-23 14:30',
        hasRead: true,
        content: '恭喜获得20个租币，请查收',
        coin: '20'
    },
    {
        title: '活动通知',
        time: '2020-03-23 14:30',
        hasRead: false,
        content: '恭喜获得20个租币，请查收',
        coin: '20'
    },
    {
        title: '活动通知',
        time: '2020-03-23 14:30',
        hasRead: true,
        content: '恭喜获得20个租币，请查收',
        coin: '20'
    }, {
        title: '活动通知',
        time: '2020-03-23 14:30',
        hasRead: false,
        content: '恭喜获得20个租币，请查收',
        coin: '20'
    },
    {
        title: '活动通知',
        time: '2020-03-23 14:30',
        hasRead: true,
        content: '恭喜获得20个租币，请查收',
        coin: '20'
    }]
    console.log(22222)
    setTimeout(() => {
        paging.value && paging.value.completeByTotal(res, 20)
    }, 1000)
}
</script>
<style lang="scss">
.notice-list-box {
    position: relative;
    flex: 1;
    padding-bottom: 100rpx;
}

.notice-mian {
    display: flex;
    width: 100vw;
    height: 100vh;
    flex-direction: column;

    .notice-title {
        display: flex;
        // align-items: center;

        .title-item {
            margin-left: 20rpx;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: center;
            position: relative;
            padding: 20rpx;

            .title {
                font-size: 32rpx;
                font-family: PingFangSC-Regular, PingFang SC;
                font-weight: 400;
                color: #666666;
            }

            .title-active {
                font-size: 40rpx;
                font-family: PingFangSC-Medium, PingFang SC;
                font-weight: 500;
                color: #333333;
            }

            .line {
                width: 40rpx;
                height: 8rpx;
                background: #00C8BE;
                border-radius: 5rpx;
                margin-top: 10rpx;
            }

            .point-box {
                width: 16rpx;
                height: 16rpx;
                position: absolute;
                top: 0rpx;
                right: 0rpx;
            }
        }

        .margin-two {
            margin-left: 30rpx;
        }
    }

    .notice-control-box {
        display: flex;
        align-items: center;
        padding: 30rpx;
        box-sizing: border-box;
        width: 100%;
    }

    .control-btn {
        display: flex;

        .btn-image {
            width: 24rpx;
            height: 24rpx;
        }

        .btn-text {
            font-size: 24rpx;
            font-family: PingFangSC-Regular, PingFang SC;
            font-weight: 400;
            color: #999999;
            margin-left: 4rpx;
        }
    }

    .line {
        width: 2rpx;
        height: 20rpx;
        margin-left: 30rpx;
        margin-right: 30rpx;
        background-color: #999999;
    }

    .notice-item {
        padding: 24rpx 30rpx;
        box-sizing: border-box;

        .item-title-box {
            display: flex;
            align-items: center;
            justify-content: space-between;

            .image-box {
                display: flex;
                align-items: center;
                position: relative;

                .icon-point {
                    width: 16rpx;
                    height: 16rpx;
                    position: absolute;
                    top: 0;
                    left: 50rpx;
                }

                .icon-box {
                    width: 48rpx;
                    height: 48rpx;
                }

                .title {
                    font-size: 32rpx;
                    font-family: PingFangSC-Regular, PingFang SC;
                    font-weight: 400;
                    color: #333333;
                    margin-left: 20rpx;
                }
            }

            .tiem {
                font-family: PingFangSC-Regular, PingFang SC;
                font-weight: 400;
                color: #999999;
            }
        }

        .notice-content {
            font-size: 24rpx;
            font-family: PingFangSC-Regular, PingFang SC;
            font-weight: 400;
            color: #999999;
            margin-left: 70rpx;
        }
    }
}
</style>