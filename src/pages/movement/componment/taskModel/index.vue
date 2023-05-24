<template>
    <view class="model-mian" v-if="isShow">
        <view class="model-content">
            <view class="model-headers">
                <view class="model-close" @click="$emit('handleShow', false)">×</view>
                <view class="model-title">天天做任务赚翻租币</view>
                <view class="model-text">已获得<text class="num">3321</text> 个租币，租币可兑换商品</view>
            </view>
            <view class="task-title">新人专享</view>
            <view class="task-list">
                <view class="task-card" v-for="item, index in taskList" :key="index"
                    :class="index == 0 ? '' : 'margin-top'" >
                    <view class="task-clock">
                        <view class="icon-block"></view>
                        <view class="task-text">{{ item.title }}</view>
                    </view>
                    <view class="task-btn" :class="item.received ? '' : 'task-btn-active'" @click="item.received?'':handleNotice(1,index,item)">{{ item.received ?
                        '已领取' : `+${item.coin}租币` }}</view>
                </view>
            </view>
            <view class="task-title">每天逛逛</view>
            <view class="task-list">
                <view class="task-card" v-for="item, index in todaytaskList" :key="index"
                    :class="index == 0 ? '' : 'margin-top'" >
                    <view class="task-clock">
                        <view class="icon-block"></view>
                        <view class="task-text">{{ item.title }}</view>
                    </view>
                    <view class="task-btn" :class="item.received ? '' : 'task-btn-active'" @click="item.received?'':handleNotice(0,index,item)">{{ item.received ?
                        '已领取' : `+${item.coin}租币` }}</view>
                </view>
            </view>
        </view>
        <ModelNotice :isShow="hasNotice" :cion="currentCion"></ModelNotice>
    </view>
</template>
<script setup lang="ts">
import ModelNotice from '../tasknotice/index.vue'
import { ref,reactive } from 'vue'
type taskList ={
    title: string,
    received: boolean,
    coin: string

}
const taskList = reactive([{
    title: '收藏人人租机小程序',
    received: false,
    coin: '30'

}, {
    title: '进行实名认证',
    received: false,
    coin: '30'
}
])
const todaytaskList = reactive([{
    title: '逛一逛活动页',
    received: false,
    coin: '30'

}, {
    title: '逛一逛生活号首页',
    received: false,
    coin: '30'
}
])
const hasNotice=ref(false)
const currentCion =ref('20')
const handleClose=()=>{
    hasNotice.value=false
} 
const handleNotice=(type:number,index:number,item:taskList)=>{

    updateList(type,index)
    currentCion.value=item.coin
    hasNotice.value=true
    setTimeout(()=>{
        handleClose()
    },1000) 
}
const updateList=(type:number,index:number)=>{
    if(type){
        taskList[index].received=true
    }else{
        todaytaskList[index].received=true
    }
} 
defineProps({
    isShow: {
        type: Boolean,
        default: false
    },
})

</script>

<style scoped >
.model-mian {
    width: 100vw;
    height: 100vh;
    background-color: #33333390;
    /* opacity: 0.5; */
    position: fixed;
    top: 0;
    z-index: 20;
}

.model-content {
    width: 750rpx;
    height: 1431rpx;
    background: #E9FAF4;
    border-radius: 48rpx 48rpx 0rpx 0rpx;
    position: absolute;
    bottom: 0;
}

.model-headers {
    width: 750rpx;
    height: 158rpx;
    border-radius: 48rpx 48rpx 0rpx 0rpx;
    background: linear-gradient(147deg, #7AD38C 0%, #40CBBE 100%);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.model-title {
    font-size: 42rpx;
    font-family: PingFangSC-Medium, PingFang SC;
    font-weight: 500;
    color: #FFFFFF;
}

.model-text {
    font-size: 28rpx;
    font-family: PingFangSC-Regular, PingFang SC;
    font-weight: 400;
    color: #FFFFFF;
    margin-top: 20rpx;
}

.model-close {
    width: 54rpx;
    height: 54rpx;
    border: 2rpx solid #FFFFFF;
    border-radius: 54rpx;
    display: flex;
    font-size: 35rpx;
    justify-content: center;
    align-items: center;
    color: #FFFFFF;
    position: absolute;
    top: 30rpx;
    right: 30rpx;
}

.num {
    color: #e2ee91;
}

.task-title {
    font-size: 34rpx;
    font-family: PingFangSC-Medium, PingFang SC;
    font-weight: 500;
    color: #133C37;
    margin-left: 46rpx;
    margin-top: 20rpx;

}

.task-list {
    width: 100%;
    box-sizing: border-box;
    padding: 20rpx 26rpx;
}

.task-card {
    width: 100%;
    height: 158rpx;
    background: #FFFFFF;
    box-shadow: 0rpx 4rpx 11rpx 0rpx rgba(44, 93, 88, 0.06);
    border-radius: 12rpx;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 30rpx;
    box-sizing: border-box;
}

.icon-block {
    width: 98rpx;
    height: 98rpx;
    background: #72D0A0;
    opacity: 0.1787;
    border-radius: 98rpx;
}

.task-clock {
    display: flex;
    justify-content: center;
    align-items: center;
}

.task-text {
    margin-left: 20rpx;
}

.task-btn {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 28rpx;
    font-family: PingFangSC-Medium, PingFang SC;
    font-weight: 500;
    color: #999999;
    width: 153rpx;
    height: 56rpx;
    border-radius: 28rpx;
    border: 2rpx solid #999999;
}

.task-btn-active {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 28rpx;
    font-family: PingFangSC-Medium, PingFang SC;
    font-weight: 500;
    color: #FF7F00;
    width: 153rpx;
    height: 56rpx;
    border-radius: 28rpx;
    border: 2rpx solid #FF7F00;
}

.margin-top {
    margin-top: 20rpx;
}

</style>